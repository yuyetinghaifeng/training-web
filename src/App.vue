<template>
  <div id="app">
  <!-- 头部导航 -->
  <header class="header">
  <el-row>
   <el-col :span="24">
    <el-menu default-active="5" class="el-menu-demo" mode="horizontal" @select="handleSelect">
    <!-- <el-menu-item>
      <a href="/" target="_self" title="图片"><img title="搞事情" src=".\assets\welcome.gif"></a>
    </el-menu-item> -->
    <el-menu-item index="1">免费课程</el-menu-item>
    <el-menu-item index="2">需求中心</el-menu-item>
    <el-menu-item index="3">课程中心</el-menu-item>
    <el-menu-item index="4">我的社区</el-menu-item>
    <el-menu-item index="5">我的笔记</el-menu-item>
    <el-menu-item index="6">
      <el-input v-model="input" size="small" placeholder="请输入内容"></el-input>
      <el-button type="primary" size="small" icon="el-icon-search">搜索</el-button>
    </el-menu-item>
    <el-menu-item index="7" style="margin-left:200px;">我的中心</el-menu-item>
    </el-menu>
   </el-col>
  </el-row>
  </header>
  <div style="position: relative;height: 30px;width: 100%;"></div>
  <main>
    <!-- 左侧导航 -->
   <div class="main-left">
    <el-menu default-active="/activeFront" class="el-menu-vertical-demo" :router="true">
    <el-menu-item index="/activeFront" :class="{'isActive': active}">前端</el-menu-item>
    <el-menu-item index="/activeback" :class="{'isActive': !active}">后端</el-menu-item>
    <el-menu-item index="/activeKuangjia" :class="{'isActive': !active}">框架</el-menu-item>
    </el-menu>
   </div>
    <!-- 右侧主内容区 -->
    <div class="main-right" >
    </div>
  </main>
  </div>
 </template>
<script>
 import Vue from 'vue'
 import Element from 'element-ui'
 import 'element-ui/lib/theme-chalk/index.css'
 Vue.use(Element)
 export default {
  name: 'app',
  data: function (){
  return {
   active:true
  }
  }
 }
 </script>
 <style>
  body{margin: 0;}
 #app {
  min-width: 1200px;
  margin: 0 auto;
  font-family: "Helvetica Neue","PingFang SC",Arial,sans-serif;
 }
 /* 头部导航 */
 header{z-index: 1000;min-width: 1200px;transition: all 0.5s ease; border-top: solid 4px #3091F2; background-color: #909399; box-shadow: 0 2px 4px 0 rgba(0,0,0,.12),0 0 6px 0 rgba(0,0,0,.04); }
 header.header-fixed{position: fixed;top: 0;left: 0;right: 0;}
 header .el-menu-demo{padding-left: 200px!important;}
 /* 主内容区 */
  main{ display: -webkit-box; display: -ms-flexbox; display: flex; min-height: 800px; border: solid 40px #E9ECF1; background-color: #FCFCFC; }
  main .main-left{text-align: center;width: 200px;float: left;}
  main .main-right{-webkit-box-flex: 1; -ms-flex: 1; flex: 1; background-color: #fff; padding: 50px 70px; }
  main .el-menu{background-color: transparent!important;}
 </style>