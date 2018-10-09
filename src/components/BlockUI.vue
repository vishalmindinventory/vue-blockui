<template>
    <div class="loading-container">
        <div class="loading-backdrop"></div>
        <div class="loading">
            <div class="loading-icon">
                <img v-if="url" :src="url"/>
                <div v-if="!url && html" v-html="html"></div>
                <slot></slot>
            </div>
            <div v-if="message" class="loading-label">{{message}}</div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'BlockUI',
  props: ['message', 'url', 'html'],
}
</script>

<style lang="scss" scoped>
.loading-container {

    position: absolute;
    top: 0px;
    left: 0px;
    right: 0px;
    bottom: 0px;
    text-align: center;

  .loading-backdrop {
    position: fixed;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    background-color: #FFFFFF;
    opacity: 0.8;
    z-index: 9998;
  }

  .loading {
      z-index: 9999;
      position: fixed;
      display: inline-block;
      padding: 20px 50px;
      border-radius: 0;
      left: 50%;
      top: 50%;
      -ms-transform: translate(-50%,-50%);
      -moz-transform: translate(-50%,-50%);
      -webkit-transform: translate(-50%,-50%);
      transform: translate(-50%,-50%);
      .loading-icon {
            margin-bottom: 8px;
      }
  }
}
</style>