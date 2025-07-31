<template>
<h1>Simple Form</h1>
<!-- <p>{{ this.form }}</p> -->
 <ul>
    <li v-for="item in error" v-bind:key ="item">
        {{ item }} is not valid
    </li>
 </ul>
<form action="">
    <label for="email">Email:</label>
    <input type="text" id="email" v-model="form.email" placeholder="Enter Email...">
    <br><br>
    <label for="pass">Password:</label>
    <input type="password" id="pass" v-model="form.password" placeholder="Enter Password ">
    <br><br>
    <h3>Country:</h3>
    <select name="Country" id="country" v-model="form.country">
        <option >Pakistan</option>
         <option >India</option>
          <option >China</option>
           <option >USA</option>
    </select>
    
    <br><br>
    <h3>Gender:</h3>
    <input type="radio" value="Male" name="gender" v-model="form.gender" >
    <label >Male</label>
    <br><br>
    <input type="radio" value="Female" name="gender"  v-model="form.gender" >
    <label >Female</label>
    <br><br>
  
    <h3>Technology:</h3>
    <input type="checkbox" value="JAVA" v-model="form.technology" >
    <label >Java</label>
    <br><br>
    <input type="checkbox" value="PYTHON"  v-model="form.technology" >
    <label >Python</label>
    <br><br>
    <input type="checkbox" value="JS" v-model="form.technology" >
    <label >JavaScript</label>
      <br><br>
    <button v-on:click="logIn" type="button">login</button>

</form>
</template>

<script>
export default {
    name: 'formComponent',
    data() {
        return {
            form: {
                email: '',
                password: '',
                country: '',
                technology: [],
                gender: '',
            },
            error:[]
        }
    },
    methods: {
        logIn() {
            this.error = [];
           for(let item in this.form ){
            if(this.form[item] === '' || this.form[item].length ===0){
                this.error.push(item);
            }
           }
           if(this.error === 0){
            alert('there is no error!')
           }
           console.log(this.form,this.error);
        }

    }
}
</script>
