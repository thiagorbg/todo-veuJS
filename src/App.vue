
<script setup>
import { ref, computed } from "vue";

const campoA = ref(0);
const campoB = ref(0);
const operacao = ref("multiplicar");

// Computed calcula automaticamente sempre que algum valor muda
const resultado = computed(() => {
const a = parseFloat(campoA.value);
const b = parseFloat(campoB.value);

switch (operacao.value) {
    case "multiplicar":
      return a * b;
    case "divisao":
    return b !== 0 ? a / b : "Erro: divisão por zero";
    case "adicao":
    return a + b;
    case "subtracao":
    return a - b;
    default:
    return "";
}
});
</script>

<template>
<div class="container text-center">
    <div class="border--">
        <header class="mt-5 bg-light text-center mb-5 p-4 " >
        <h1 class="">Calculadora Aritimetrica</h1>
        <p>resultado {{ resultado }}</p>
    </header>
    <div class="d-flex justify-content-center mt-3">
    <input v-model="campoA" type="number" placeholder="Número 1" class="form-control w-25 me-2" />
    <select v-model="operacao" class="form-control w-25 me-2">
        <option value="multiplicar">Multiplicar</option>
        <option value="divisao">Divisão</option>
        <option value="adicao">Adição</option>
        <option value="subtracao">Subtração</option>
    </select>
    <input v-model="campoB" type="number" placeholder="Número 2" class="form-control w-25 me-2" />
    </div>
    
    <h3 class="mt-3">Seu resultado é: {{ resultado }}</h3>
    </div>
</div>
</template>

<style scoped>
.border-- {
    border-bottom: 2px solid black;
    padding-bottom: 20px;
}
.container {
    margin-top: 30px;
}
</style>
