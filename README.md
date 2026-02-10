<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>IoT Smart City Dashboard</title>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, sans-serif;
      background: #0f172a;
      color: #e5e7eb;
    }
    header {
      background: linear-gradient(90deg, #2563eb, #0ea5e9);
      padding: 20px;
      text-align: center;
    }
    header h1 { margin: 0; }
    header p { margin: 4px 0 0; }.container {
  padding: 20px;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
}

.card {
  background: #020617;
  border-radius: 16px;
  padding: 20px;
  box-shadow: 0 10px 25px rgba(0,0,0,0.4);
}

.card h3 {
  margin-top: 0;
  font-size: 1.1rem;
  color: #38bdf8;
}

.value {
  font-size: 2.2rem;
  font-weight: bold;
}

.status {
  margin-top: 8px;
  font-size: 0.9rem;
}

.status.good { color: #22c55e; }
.status.warn { color: #facc15; }
.status.bad { color: #ef4444; }

.chart-card {
  grid-column: span 2;
}

footer {
  text-align: center;
  padding: 16px;
  font-size: 0.85rem;
  color: #94a3b8;
}

@media (max-width: 768px) {
  .chart-card { grid-column: span 1; }
}

  </style>
</head>
<body><header>
  <h1>IoT-Based Smart City Dashboard</h1>
  <p>INNOVATORS SQUAD | ZAYATHON 2026 | Sona College of Technology</p>
</header><section class="container">
  <!-- Temperature -->
  <div class="card">
    <h3>Temperature</h3>
    <div class="value">32°C</div>
    <div class="status warn">Above Normal</div>
  </div>  <!-- Humidity -->  <div class="card">
    <h3>Humidity</h3>
    <div class="value">68%</div>
    <div class="status good">Optimal</div>
  </div>  <!-- Air Quality -->  <div class="card">
    <h3>Air Quality (MQ135)</h3>
    <div class="value">AQI 145</div>
    <div class="status bad">Poor – Alert Sent</div>
  </div>  <!-- System Status -->  <div class="card">
    <h3>System Status</h3>
    <div class="value">Online</div>
    <div class="status good">All IoT Nodes Connected</div>
  </div>  <!-- Temperature Chart -->  <div class="card chart-card">
    <h3>Temperature Trend</h3>
    <canvas id="tempChart"></canvas>
  </div>  <!-- Air Quality Chart -->  <div class="card chart-card">
    <h3>Air Quality Trend</h3>
    <canvas id="airChart"></canvas>
  </div>
</section><footer>
  © 2026 INNOVATORS SQUAD – Smart City Prototype Dashboard
</footer><script>
  const tempCtx = document.getElementById('tempChart');
  new Chart(tempCtx, {
    type: 'line',
    data: {
      labels: ['10AM','11AM','12PM','1PM','2PM','3PM'],
      datasets: [{
        label: 'Temperature (°C)',
        data: [29, 30, 31, 32, 33, 32],
        tension: 0.4
      }]
    }
  });

  const airCtx = document.getElementById('airChart');
  new Chart(airCtx, {
    type: 'bar',
    data: {
      labels: ['Zone A','Zone B','Zone C','Zone D'],
      datasets: [{
        label: 'AQI Levels',
        data: [90, 120, 145, 110]
      }]
    }
  });
</script></body>
</html>
