<template>
  <div class="hello">
    <ul v-for="i in arr">
      <!--<li>{{i.id}}</li>-->
      <li>{{i.tit}}<button>删除</button></li>
      <li>{{i.con}}</li>
    </ul>
  </div>
</template>
<!--import Gin from 'vue-resource'-->
<script>

export default {
  created(){
   this.$http.get("http://localhost:8000/").then((e)=>this.arr=e.body)
  },
  data(){
    return {
      arr:[]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul {
  width: 50%;
  list-style-type: none;
  padding: 0;
}
ul>li{
  border: 1px solid #cccccc;
  box-sizing: border-box;
  padding: 10px;
}
ul>li:nth-child(odd){
  width: 100%;
  display: inline-block;
  text-align: left;
}
ul>li:nth-child(even){
  width: 100%;
  display: inline-block;
  text-align: center;
}
  li>button{
    float: right;
  }
</style>
