<template>
  <button v-if="!connected" class="myButtonConnect" @click="toggle">Connect</button>
  <button v-if="connected" class="myButtonDisconnect" @click="toggle">Disconnect</button>
  <div v-if="connected" class="main">
    <Top></Top>
    <div style="display: flex; height: 50%;">
      <Left></Left>
      <Right></Right>
    </div>
    <Bottom></Bottom>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import Bottom from './components/Bottom.vue'
import Left from './components/Left.vue';
import Right from './components/Right.vue';
import Top from './components/Top.vue';

export default defineComponent({
  name: 'App',
  components: {
    Top,
    Left,
    Right,
    Bottom
  },
  setup () {
    let connected = ref(false)
    function toggle () {
      connected.value = !connected.value

    }
    return{
      toggle,
      connected
    }
  }
});
</script>

<style>
.main {
  height: 80vh;
  /*border-style: solid;*/
}
.myButtonConnect {
  width: 80vw;
  height: 10vh;
  background-color: burlywood;
  margin-left: 10vw;
  margin-bottom: 1%;
  font-size: 4vw;
}
.myButtonDisconnect {
  width: 80vw;
  height: 10vh;
  background-color: orange;
  margin-left: 10vw;
  margin-bottom: 1%;
  font-size: 4vw;
}

</style>
