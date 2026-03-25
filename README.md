index.html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Architecture Portfolio</title>

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600&display=swap" rel="stylesheet">

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Inter', sans-serif;
}

body {
  background: #000;
  color: #fff;
  overflow-x: hidden;
}

/* NAV */
nav {
  position: fixed;
  width: 100%;
  display: flex;
  justify-content: space-between;
  padding: 20px 50px;
  z-index: 1000;
  background: rgba(0,0,0,0.4);
  backdrop-filter: blur(10px);
}

nav h1 {
  font-weight: 400;
  letter-spacing: 2px;
}

nav a {
  margin-left: 25px;
  text-decoration: none;
  color: #aaa;
}

/* HERO */
.hero {
  height: 100vh;
  display: flex;
  align-items: center;
  padding: 80px;
}

.hero h2 {
  font-size: 70px;
  font-weight: 300;
  line-height: 1.1;
}

/* SECTION */
.section {
  padding: 120px 80px;
  max-width: 900px;
}

.section h2 {
  font-size: 48px;
  margin-bottom: 20px;
}

.section p {
  color: #bbb;
  line-height: 1.7;
}

/* PROJECTS */
.projects {
  padding: 100px 80px;
}

.project {
  display: flex;
  gap: 40px;
  margin-bottom: 100px;
  align-items: center;
}

.project img {
  width: 500px;
  height: 320px;
  object-fit: cover;
  transition: 0.4s;
}

.project img:hover {
  transform: scale(1.05);
}

.project h3 {
  font-size: 26px;
}

/* CONTACT */
.contact {
  padding: 100px 80px;
  max-width: 600px;
}

input, textarea {
  width: 100%;
  margin: 10px 0;
  padding: 12px;
  background: transparent;
  border: 1px solid #333;
  color: white;
}

button {
  padding: 12px 30px;
  background: white;
  color: black;
  border: none;
  cursor: pointer;
}

/* FOOTER */
footer {
  text-align: center;
  padding: 40px;
  color: #666;
}

/* ANIMATION */
.fade {
  opacity: 0;
  transform: translateY(50px);
  transition: 1s;
}

.show {
  opacity: 1;
  transform: translateY(0);
}

/* RESPONSIVE */
@media(max-width:768px) {
  .hero h2 { font-size: 40px; }
  .project { flex-direction: column; }
  .project img { width: 100%; }
}
</style>
</head>

<body>

<!-- NAV -->
<nav>
  <h1>YOUR NAME</h1>
  <div>
    <a href="#work">Work</a>
    <a href="#about">Studio</a>
    <a href="#contact">Contact</a>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <h2>
    Designing <br> Beyond Architecture
  </h2>
</section>

<!-- IDEA -->
<section class="section fade">
  <h2>We create spatial experiences</h2>
  <p>
    Architecture is more than buildings. It is a system of relationships between form,
    function, and human interaction.
  </p>
</section>

<!-- PROJECTS -->
<section id="work" class="projects">

  <div class="project fade">
    <img src="https://images.unsplash.com/photo-1600585154340-be6161a56a0c">
    <div>
      <h3>Private Villa — Cairo</h3>
      <p>Modern luxury living designed with precision and clarity.</p>
    </div>
  </div>

  <div class="project fade">
    <img src="https://images.unsplash.com/photo-1494526585095-c41746248156">
    <div>
      <h3>Mixed-Use Tower — Riyadh</h3>
      <p>Combining urban density with human-centered design.</p>
    </div>
  </div>

</section>

<!-- ABOUT -->
<section id="about" class="section fade">
  <h2>Studio</h2>
  <p>
    I am an architecture engineer focused on delivering refined, modern, and functional
    spaces. Each project is driven by innovation, sustainability, and user experience.
  </p>
</section>

<!-- CONTACT -->
<section id="contact" class="contact fade">
  <h2>Start a Project</h2>

  <form onsubmit="sendMessage(event)">
    <input type="text" placeholder="Name" required>
    <input type="email" placeholder="Email" required>
    <textarea rows="5" placeholder="Project details" required></textarea>
    <button>Send</button>
  </form>
</section>

<footer>
  © 2026 YOUR NAME — Architecture Portfolio
</footer>

<script>
const elements = document.querySelectorAll('.fade');

const observer = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('show');
    }
  });
});

elements.forEach(el => observer.observe(el));

function sendMessage(e) {
  e.preventDefault();
  alert("Message sent (connect backend later)");
}
</script>

</body>
</html>
