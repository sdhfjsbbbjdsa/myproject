<template>
    <AppTopnav />
    <AppHeader/>
    <header>头部</header>
    <main>
      <!-- 二级路由 -->
      <router-view></router-view>
      <AppFooter/>
    </main>
    <footer>底部</footer>
  </template>
<script>
import AppTopnav from '@/components/app-topnav'
import AppHeader from '@/components/app-header.vue'
import AppFooter from '@/components/app-footer'
import { useStore } from 'vuex'
export default {
  name: 'Layout',
  components: { AppTopnav, AppHeader, AppFooter },
  // 获取下分类数据
  setup () {
    const store = useStore()
    store.dispatch('category/getList')
  }
}
</script>
<style scoped lang='less'></style>
