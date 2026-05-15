# PAGINA-WEB-PRUEBA
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Mi Primer Proyecto</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet" />
  <style>
    :root {
      --bg: #0d0f14;
      --surface: #13161e;
      --accent: #c8f060;
      --accent2: #60d4f0;
      --text: #e8eaf0;
      --muted: #6b7280;
      --border: rgba(200, 240, 96, 0.15);
    }

    *, *::before, *::after {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background-color: var(--bg);
      color: var(--text);
      font-family: 'DM Sans', sans-serif;
      font-weight: 300;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      overflow-x: hidden;
    }

    /* Animated background grid */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(var(--border) 1px, transparent 1px),
        linear-gradient(90deg, var(--border) 1px, transparent 1px);
      background-size: 60px 60px;
      z-index: 0;
      animation: gridPulse 8s ease-in-out infinite;
    }

    @keyframes gridPulse {
      0%, 100% { opacity: 0.4; }
      50% { opacity: 0.8; }
    }

    /* Glow orbs */
    body::after {
      content: '';
      position: fixed;
      width: 600px;
      height: 600px;
      background: radial-gradient(circle, rgba(200,240,96,0.07) 0%, transparent 70%);
      top: -100px;
      right: -100px;
      z-index: 0;
      animation: float 10s ease-in-out infinite;
    }

    @keyframes float {
      0%, 100% { transform: translate(0, 0); }
      50% { transform: translate(-40px, 40px); }
    }

    .container {
      position: relative;
      z-index: 1;
      text-align: center;
      padding: 60px 40px;
      max-width: 760px;
      width: 100%;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: rgba(200, 240, 96, 0.08);
      border: 1px solid rgba(200, 240, 96, 0.3);
      color: var(--accent);
      font-size: 0.75rem;
      font-weight: 500;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      padding: 6px 16px;
      border-radius: 100px;
      margin-bottom: 36px;
      animation: fadeSlideDown 0.8s ease both;
    }

    .badge::before {
      content: '';
      width: 6px;
      height: 6px;
      background: var(--accent);
      border-radius: 50%;
      animation: blink 1.5s ease-in-out infinite;
    }

    @keyframes blink {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.2; }
    }

    h1 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(3rem, 8vw, 5.5rem);
      font-weight: 900;
      line-height: 1.05;
      letter-spacing: -0.02em;
      color: var(--text);
      margin-bottom: 12px;
      animation: fadeSlideDown 0.9s ease 0.1s both;
    }

    h1 span {
      color: var(--accent);
      position: relative;
      display: inline-block;
    }

    h1 span::after {
      content: '';
      position: absolute;
      bottom: 4px;
      left: 0;
      width: 100%;
      height: 3px;
      background: var(--accent);
      border-radius: 2px;
      transform: scaleX(0);
      transform-origin: left;
      animation: underlineExpand 0.8s ease 1s both;
    }

    @keyframes underlineExpand {
      to { transform: scaleX(1); }
    }

    .subtitle {
      font-family: 'Playfair Display', serif;
      font-size: clamp(1.5rem, 4vw, 2.2rem);
      font-weight: 700;
      color: var(--accent2);
      margin-bottom: 40px;
      animation: fadeSlideDown 0.9s ease 0.2s both;
    }

    .divider {
      width: 60px;
      height: 1px;
      background: linear-gradient(90deg, transparent, var(--accent), transparent);
      margin: 0 auto 40px;
      animation: fadeSlideDown 0.9s ease 0.3s both;
    }

    p {
      font-size: 1.1rem;
      line-height: 1.85;
      color: rgba(232, 234, 240, 0.75);
      max-width: 560px;
      margin: 0 auto 48px;
      animation: fadeSlideDown 0.9s ease 0.4s both;
    }

    p strong {
      color: var(--text);
      font-weight: 500;
    }

    .card-row {
      display: flex;
      gap: 16px;
      justify-content: center;
      flex-wrap: wrap;
      animation: fadeSlideDown 0.9s ease 0.5s both;
    }

    .card {
      background: var(--surface);
      border: 1px solid rgba(255,255,255,0.06);
      border-radius: 16px;
      padding: 20px 24px;
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      gap: 8px;
      width: 180px;
      transition: border-color 0.3s, transform 0.3s;
      cursor: default;
    }

    .card:hover {
      border-color: rgba(200, 240, 96, 0.3);
      transform: translateY(-4px);
    }

    .card-icon {
      font-size: 1.5rem;
    }

    .card-label {
      font-size: 0.7rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--muted);
      font-weight: 500;
    }

    .card-value {
      font-size: 0.95rem;
      color: var(--text);
      font-weight: 400;
    }

    footer {
      position: relative;
      z-index: 1;
      margin-top: 60px;
      font-size: 0.75rem;
      color: var(--muted);
      letter-spacing: 0.05em;
      animation: fadeSlideDown 0.9s ease 0.6s both;
    }

    @keyframes fadeSlideDown {
      from {
        opacity: 0;
        transform: translateY(-18px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @media (max-width: 500px) {
      .container { padding: 40px 24px; }
      .card-row { flex-direction: column; align-items: center; }
      .card { width: 100%; max-width: 300px; }
    }
  </style>
</head>
<body>

  <div class="container">
    <div class="badge">En línea &amp; listo</div>

    <h1>Mi <span>Primer</span></h1>
    <div class="subtitle">Proyecto Web ✦</div>

    <div class="divider"></div>

    <p>
      Este es mi primer proyecto creado con ayuda de <strong>Inteligencia Artificial</strong>.
      Desde la estructura hasta el diseño, cada línea de código fue generada junto a Claude,
      marcando el inicio de un nuevo camino en el desarrollo web.
    </p>

    <div class="card-row">
      <div class="card">
        <span class="card-icon">🤖</span>
        <span class="card-label">Creado con</span>
        <span class="card-value">Claude AI</span>
      </div>
      <div class="card">
        <span class="card-icon">🚀</span>
        <span class="card-label">Estado</span>
        <span class="card-value">Activo</span>
      </div>
      <div class="card">
        <span class="card-icon">💡</span>
        <span class="card-label">Versión</span>
        <span class="card-value">1.0.0</span>
      </div>
    </div>
  </div>

  <footer>
    © 2026 · Mi Primer Proyecto · Hecho con IA &amp; entusiasmo
  </footer>

</body>
</html>
