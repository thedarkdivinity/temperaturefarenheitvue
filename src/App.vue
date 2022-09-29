<template>
  
    <div class="mainDiv">
      <div :class="[far>0?'positive':'negative','subDiv']">
      <label>Enter Celsius Temperature</label>
      <input v-model.number="celsius" type="number" class="convertInput" />
      <div class="convertText">{{ celsius }}c is {{ far}}f</div>
    </div>
    </div>
   

 
</template>
<script>
export default {
  name: "App",
  data() {
    return {
      celsius: 0,
      
    };
  },
 computed:{
  far(){
    return (this.celsius*(9/5)+32).toFixed(2)
  }
 }
 
};
</script>
<style>
  .mainDiv{
   height: 100vh;
   width: 100%;
   display: grid;
   place-content: center;
   background-color: bisque;
  }
  .subDiv{
    width: 300px;
    height: 300px;
   
    color:white;
    display:grid;
    place-content:center;
    border-radius:30px
  }
  .positive{
    background-color: lightcoral;
  }
  .negative{
    background-color: rebeccapurple;
  }
  .convertText{
    margin-top: 20px;
  }
  .convertInput{
    margin-top: 20px;
    margin-bottom: 10px;
  }
</style>