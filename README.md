<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>MathematicsSam</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1>MathematicsSam</h1>
    <nav>
      <a href="#primaria">Primaria</a>
      <a href="#secundaria">Secundaria</a>
      <a href="#universidad">Universidad</a>
    </nav>
    <input type="text" id="searchInput" placeholder="Buscar problema..." onkeyup="searchProblems()">
  </header>

  <main>
    <section id="primaria">
      <h2>Primaria</h2>
      <div class="problem">¿Cuánto es 8 + 7? <span class="solution">15</span></div>
      <div class="problem">Resuelve: 12 - 4 <span class="solution">8</span></div>
    </section>

    <section id="secundaria">
      <h2>Secundaria</h2>
      <div class="problem">Factoriza: x² - 9 <span class="solution">(x - 3)(x + 3)</span></div>
      <div class="problem">Resuelve: 3x + 5 = 11 <span class="solution">x = 2</span></div>
    </section>

    <section id="universidad">
      <h2>Universidad</h2>
      <div class="problem">Deriva: f(x) = x³ <span class="solution">f'(x) = 3x²</span></div>
      <div class="problem">Integral de x dx <span class="solution">½x² + C</span></div>
    </section>
  </main>

  <script src="script.js"></script>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background: #f4f4f4;
}
header {
  background: #333;
  color: white;
  padding: 1em;
  text-align: center;
}
nav a {
  margin: 0 10px;
  color: #fff;
  text-decoration: none;
}
input[type="text"] {
  margin-top: 1em;
  padding: 0.5em;
  width: 80%;
  max-width: 400px;
}
main {
  padding: 20px;
}
.problem {
  background: white;
  padding: 10px;
  margin: 10px 0;
  border-left: 4px solid #007BFF;
}
.solution {
  display: block;
  color: #555;
  margin-top: 5px;
}
function searchProblems() {
  const input = document.getElementById("searchInput").value.toLowerCase();
  const problems = document.querySelectorAll(".problem");

  problems.forEach(problem => {
    const text = problem.textContent.toLowerCase();
    problem.style.display = text.includes(input) ? "" : "none";
  });
}
