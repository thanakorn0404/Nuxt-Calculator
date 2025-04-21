<script setup>
import '../public/app.scss'

const CalValue = ref('')

function Display(A){
    CalValue.value += A
}
function Clear(){
    CalValue.value = ''
}
function Sum(){
    CalValue.value = eval(CalValue.value)
}

</script>

<template>
    <div class="container">
        <div class="display">
            <input type="text" :value="CalValue" disabled/>
        </div>
        <div class="buttons">
            <div class="Numbers">
            <button @click="Display('(')">(</button>
            <button @click="Display(')')">)</button>
            <button @click="Clear()">C</button>
            <button @click="Display('7')">7</button>
            <button @click="Display('8')">8</button>
            <button @click="Display('9')">9</button>
            <button @click="Display('4')">4</button>
            <button @click="Display('5')">5</button>
            <button @click="Display('6')">6</button>
            <button @click="Display('1')">1</button>
            <button @click="Display('2')">2</button>
            <button @click="Display('3')">3</button>
            <button @click="Display('0')">0</button>
            <button @click="Display('.')">.</button>
            </div>
            <div class="symbols">
            <button @click="Display('+')">+</button>
            <button @click="Display('-')">-</button>
            <button @click="Display('*')">*</button>
            <button @click="Display('/')">/</button>
            <button @click="Sum()">=</button> 
            </div>
        </div>
    </div>  
    

</template>

<style scoped>
.container {
    display: grid;
    justify-content: center;
    width: 400px;
    height: 500px;
    background-color: #191870ed;
    border-radius: 10px;
}
.header {
    text-align: center;
    margin: 20px;
    font-size: 24px;
    color: #ff0000;
}
.Numbers {
    display: grid;
    grid-template-columns: repeat(3 , 1fr);
    gap: 10px;
    margin-right: 10px;
}
.symbols {
    display: grid;
    gap: 10px;
}
.buttons {
    display: flex;
}
</style>