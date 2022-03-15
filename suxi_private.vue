<template>
  <el-container class="home_container">
    <!-- 头部区域 -->
    <el-header style="height: 80px">
      <div>
        <span>基于数据分析的专业学习策略</span>
      </div>
      <span class="admin"
        ><i class="el-icon-user"></i>当前用户:admin |
        <el-button type="text" class="color" @click="login_out"
          >退出系统</el-button
        >
      </span>
    </el-header>
    <!-- 页面主体区域 -->
    <el-container>
      <!-- 侧边栏 -->
      <el-aside width="165px">
        <!-- 侧边栏菜单区域 -->
        <el-menu
          class="menu"
          default-active="1"
          text-color="black"
          active-text-color="green"
          router
        >
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-s-home"></i>
              <span>项目背景</span>
            </template>
            <el-menu-item index="1-1">不同省份大学数量</el-menu-item>
            <el-menu-item index="1-2">各个年份大学毕业生数量</el-menu-item>
            <el-menu-item index="1-3">背景介绍</el-menu-item>
          </el-submenu>
          <el-submenu index="2">
            <template slot="title">
              <i class="el-icon-s-home"></i>
              <span>我爱IT竞赛</span>
            </template>
            <el-menu-item index="2-1">竞赛信息</el-menu-item>
            <el-menu-item index="2-2">竞赛视频</el-menu-item>
            <el-menu-item index="2-3">词云快看</el-menu-item>
            <el-menu-item index="2-4">竞赛数据详情</el-menu-item>
          </el-submenu>
          <el-submenu index="3">
            <template slot="title">
              <i class="el-icon-s-home"></i>
              <span>信息安全</span>
            </template>
            <el-menu-item index="3-1">调研数据</el-menu-item>
            <el-menu-item index="3-2">信息安全详情</el-menu-item>
          </el-submenu>
          <el-submenu index="4">
            <template slot="title">
              <i class="el-icon-s-home"></i>
              <span>岗位信息</span>
            </template>
            <el-menu-item index="4-1">网络安全工程师</el-menu-item>
            <el-menu-item index="4-2">go开发工程师</el-menu-item>
          </el-submenu>
          <el-submenu index="5">
            <template slot="title">
              <i class="el-icon-s-home"></i>
              <span>职位数据可视化</span>
            </template>
            <el-menu-item index="5-1">岗位数据可视化</el-menu-item>
            <el-menu-item index="5-2">echarts</el-menu-item>
          </el-submenu>
          <el-menu-item index="6">
            <i class="el-icon-document"></i>
            <span slot="title">说明</span>
          </el-menu-item>
        </el-menu>
      </el-aside>
      <el-container>
        <!-- 右侧内容主体 -->
        <el-main>
          <!-- 路由占位符 -->
          <router-view></router-view>
        </el-main>
        <!-- 底部区域 -->
        <el-footer style="height: 30px"
          >基于数据分析的专业学习策略 版权所有：Su Xi | 2021 09-30</el-footer
        >
      </el-container>
    </el-container>
  </el-container>
</template>

<script>
export default {
  created() {
    this.getMenuList();
  },

  methods: {
    login_out() {
      window.sessionStorage.clear(); //清空token
      this.$router.push("/login");
    },
    // 获取所有的菜单
    getMenuList() {},
  },
};
</script>

<style lang="less" scoped>
.home_container {
  height: 100%;
}
.el-header {
  background: -webkit-linear-gradient(
    bottom,
    rgb(121, 166, 216),
    rgb(82, 192, 219),
    rgb(106, 218, 247)
  );
  display: flex;
  justify-content: space-between;
  align-items: center;
  > div {
    display: flex;
    align-items: center;
  }
  text-align: left;
  line-height: 80px;
  font-size: 32px;
  font-weight: bold;
  font-family: "楷体";
  color: #e9eef3;
  // color: rgb(155, 82, 214);
}
.el-aside {
  background: -webkit-linear-gradient(
    bottom,
    rgb(227, 230, 235),
    rgb(82, 192, 219),
    rgb(98, 188, 211)
  );
  width: 150px;
}
// .el-main {
//   // background-color: #E9EEF3;
// }
.el-footer {
  background-color: transparent;
  text-align: center;
  line-height: 30px;
  color: #040e1a;
  // color: #62a0e7;
}
.menu {
  background: -webkit-linear-gradient(rgb(82, 192, 219), rgb(98, 188, 211));
}
.color {
  color: aliceblue;
}
.admin {
  font-size: 14px;
  font-family: "宋体";
}
</style>