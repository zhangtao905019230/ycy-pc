<template>
  <div class="app-header-inner">
    <img src="./../../assets/logo.png" style="height: 30px" alt="" class="logo">
    <div class="right">
      <el-dropdown trigger="click" @command="handleCommand">
        <span class="el-dropdown-link">
          <img style="width: 30px;height: 30px;cursor: pointer" src="./../../assets/touxiang.jpeg" alt="">
        </span>
        <el-dropdown-menu slot="dropdown">
          <el-dropdown-item>我的主页</el-dropdown-item>
          <el-dropdown-item>创作者中心</el-dropdown-item>
          <el-dropdown-item>设置</el-dropdown-item>
          <el-dropdown-item command="logout">退出</el-dropdown-item>
        </el-dropdown-menu>
      </el-dropdown>
    </div>
  </div>
</template>
<script>
  import {mapActions} from 'vuex'
  export default {
    methods:{
      ...mapActions(['clearUser']),
      handleCommand(command){
        if (command == 'logout'){
          this.clearUser();
          this.$router.push({path:'/signup'})
          this.$message({
            message: '退出登录成功！',
            type: 'success'
          });
        }
      }
    }
  }
</script>
<style>
  .app-header-inner{
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 52px;
  }
</style>
