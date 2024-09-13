<template>
  <input type="text" ref="name">
  <!-- <button @click="handleClick">click me</button> -->
   <Teleport to=".modals" v-if="showModal"> 
    <!-- <AppModal :header='header' :text='text' @close="toggleModal"/> -->
    <AppModal @close="toggleModal">
      <h1>This is heading 1</h1>
      <p>This is paragraph</p>
    </AppModal>
  </Teleport>
  <button @click="toggleModal">Show/hide Modal</button>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

import AppModal from './components/AppModal.vue';

export default {
  name: 'App',
  data(){
    return {
      header: 'Signup',
      text: 'Trial purpose',
      showModal: false
    }
  },
  components:{
    AppModal
  },
  methods:{
    handleClick(){
        console.log(this.$refs.name)
        this.$refs.name.classList.add("active")
        this.$refs.name.focus()
    },
    toggleModal(){
      this.showModal = !this.showModal
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  display: inline-block;
  padding-bottom: 10px;
  border-bottom: 1px solid #ddd;
}
</style>
