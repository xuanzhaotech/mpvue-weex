<template>
  <x-page :pageInfo="pageInfo" v-if="pageInfo"></x-page>
</template>

<script>
  export default {
    data () {
      return {
        pageInfo: {}
      }
    },
    mounted () {
      this.init()
    },
    methods: {
      async init () {
        this.pageInfo = await this.$themeApi.pageInfo(this.$client, this.$route.path)
        // console.info(this.$route.path, this.pageInfo)
      }
    }
  }
</script>