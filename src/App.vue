<template>
  <div id="app">
    <h1>Mail list</h1>
    <p>{{ListaMail}}</p>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'App',
  data: function(){
    return {
      ListaMail: []
    }

  },
  mounted(){
    let self = this;
    for(let i = 0 ; i < 10 ; i++){
    axios.get( 'https://flynn.boolean.careers/exercises/api/random/mail')

    .then (function(response){
    
    self.ListaMail.push(response.data.response)})

    }
    
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
