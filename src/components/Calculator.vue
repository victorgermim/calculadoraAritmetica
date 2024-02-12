<template>
  <div class="calculator">
    <h2>Calculadora Aritmética</h2>
    <input type="number" v-model.number="number1" />
    <input type="number" v-model.number="number2" />

    <select v-model="operation">
      <option value="add">+</option>
      <option value="subtract">-</option>
      <option value="multiply">*</option>
      <option value="divide">/</option>
    </select>

    <div class="result">Resultado: {{ result }}</div>
  </div>
</template>
  
  <script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: "add",
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case "add":
          return this.number1 + this.number2;
        case "subtract":
          return this.number1 - this.number2;
        case "multiply":
          return this.number1 * this.number2;
        case "divide":
          return this.number2 !== 0
            ? this.number1 / this.number2
            : "Divisão por zero!";
        default:
          return 0;
      }
    },
  },
};
</script>
  
<style scoped >
h2 {
  text-align: center;
}

.calculator {
  max-width: 400px;
  margin: 30px auto;
  padding: 20px;
  border: 1px solid #161616;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  background-color: #1e1e1e;
  color: aliceblue;
}

.calculator input[type="number"],
.calculator select {
  width: 100%;
  padding: 10px;
  margin-bottom: 20px;
  border: 1px solid #0a0a0a;
  border-radius: 4px;
  box-sizing: border-box;
}

.calculator .result {
  font-size: 20px;
  text-align: center;
  padding: 10px;
  border-radius: 4px;
  border: 1px solid #101010;
  background-color: #3a014f;
}

@media (max-width: 600px) {
  .calculator {
    width: 90%;
    padding: 10px;
  }
}
</style>

  