<template>
<div id="app">
     <canvas id="canvas" height="175" width="175"></canvas>
  </div>
</template>
<script>
import Chart from 'chart.js';
import Rounded from './Rounded.js';
export default {
  methods: {
      
createChart(chartId, chartData) {
var ctx = document.getElementById("canvas").getContext("2d");

var chartColors = {
    red: 'rgb(255, 99, 132)',
    green: 'rgb(75, 192, 192)',
    blue: 'rgb(54, 162, 235)',
  };

  var randomScalingFactor = function() {
    return (Math.random() > 0.5 ? 1.0 : 1.0) * Math.round(Math.random() * 100);
  };
  
  var myBar = new Chart(ctx, {
    type: 'roundedBar',
    data: {
      labels: ["Car", "Bike", "Walking"],
      datasets: [{
        label: 'Students',
        backgroundColor: chartColors.blue,
        data: [
          randomScalingFactor(), 
          randomScalingFactor(), 
          randomScalingFactor(), 
        ]
      }, {
        label: 'Teachers',
        backgroundColor: chartColors.red,
        data: [
          randomScalingFactor(), 
          randomScalingFactor(), 
          randomScalingFactor(), 
        ]
      }, {
        label: 'Visitors',
        backgroundColor: chartColors.green,
        data: [
          randomScalingFactor(), 
          randomScalingFactor(), 
          randomScalingFactor(), 
        ]
      }]
    },
    options: {
      responsive: true,
      barRoundness: 1,
      title: {
        display: true,
        text: "Chart.js - Bar Chart with Rounded Tops (drawRoundedTopRectangle Method)"
      },
    }
  });
  }
},
  name: 'app',
  data () {
return {
    Rounded: Rounded,
  }
  },
  mounted() {
  this.createChart('guage-o-meter', this.Rounded);
}
}
</script>

<style>
#guage-container {
  background-color: red;
  height: 200px;
}

#guage-o-meter {
 margin-top: -300px;
}
</style>
