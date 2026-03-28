<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Varnei Vargas — Landing Dinámica</title>
  <meta name="description" content="Lo que sabes hacer merece ser visto. Convierte tus intereses en clientes.">
  <link href="https://fonts.googleapis.com/css?family=Montserrat:400,600,700&display=swap" rel="stylesheet">
  <style>
    :root {
      --orange: #ff6700;
      --orange-hover: #e55a00;
      --black: #0a0a0a;
      --dark-grey: #1a1a1a;
      --darker-grey: #0f0f0f;
      --white: #fff;
      --secondary: #b8b8b8;
      --border: #333;
      --green-ws: #25d366;
      --green-ws-hover: #1bd741;
    }
    html, body {
      margin: 0;
      padding: 0;
      background: var(--black);
      color: var(--white);
      font-family: 'Montserrat', Arial, sans-serif;
      box-sizing: border-box;
      scroll-behavior: smooth;
      overflow-x: hidden;
    }
    *,
    *:before,
    *:after {
      box-sizing: inherit;
    }
    /* ANIMACIONES GLOBALES */
    @keyframes fadeUpIn {
      from {
        opacity: 0;
        transform: translateY(50px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    @keyframes slideInLeft {
      from {
        opacity: 0;
        transform: translateX(-60px);
      }
      to {
        opacity: 1;
        transform: translateX(0);
      }
    }
    @keyframes slideInRight {
      from {
        opacity: 0;
        transform: translateX(60px);
      }
      to {
        opacity: 1;
        transform: translateX(0);
      }
    }
    @keyframes scaleUpIn {
      from {
        opacity: 0;
        transform: scale(0.8);
      }
      to {
        opacity: 1;
        transform: scale(1);
      }
    }
    @keyframes pulse {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.7; }
    }
    @keyframes float {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-15px); }
    }
    .fade-in {
      opacity: 0;
      transform: translateY(40px);
    }
    .fade-in.visible {
      animation: fadeUpIn 0.85s cubic-bezier(0.33, 0.86, 0, 1) forwards;
    }
    .slide-left {
      opacity: 0;
    }
    .slide-left.visible {
      animation: slideInLeft 0.9s cubic-bezier(0.33, 0.86, 0, 1) forwards;
    }
    .slide-right {
      opacity: 0;
    }
    .slide-right.visible {
      animation: slideInRight 0.9s cubic-bezier(0.33, 0.86, 0, 1) forwards;
    }
    .scale-in {
      opacity: 0;
    }
    .scale-in.visible {
      animation: scaleUpIn 0.8s cubic-bezier(0.33, 0.86, 0, 1) forwards;
    }
    /* HEADER */
    header {
      position: sticky;
      top: 0;
      z-index: 30;
      width: 100%;
      background: rgba(10, 10, 10, 0.95);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid var(--border);
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1.2rem 2rem;
      animation: slideInDown 0.6s ease-out;
    }
    @keyframes slideInDown {
      from {
        opacity: 0;
        transform: translateY(-20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    header .brand {
      font-weight: 700;
      font-size: 1.3rem;
      letter-spacing: 1.5px;
      color: var(--white);
    }
    /* BOTONES */
    .btn-whatsapp {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      background: var(--green-ws);
      color: var(--white);
      border: 0;
      font-weight: 700;
      font-family: inherit;
      border-radius: 100px;
      padding: 0.8em 1.8em;
      cursor: pointer;
      font-size: 1rem;
      transition: background 0.2s cubic-bezier(0.42, 0, 0.58, 1), 
                  transform 0.2s cubic-bezier(0.23, 1, 0.32, 1),
                  box-shadow 0.2s;
      box-shadow: 0 4px 16px rgba(37, 211, 102, 0.25);
      outline: none;
      text-decoration: none;
      gap: 0.5em;
    }
    .btn-whatsapp:hover,
    .btn-whatsapp:focus {
      background: var(--green-ws-hover);
      transform: translateY(-4px) scale(1.08);
      box-shadow: 0 8px 28px rgba(37, 211, 102, 0.35);
    }
    .btn-whatsapp:active {
      transform: translateY(-2px) scale(1.05);
    }
    .btn-whatsapp svg {
      width: 1.4em;
      height: 1.4em;
      fill: currentColor;
      flex-shrink: 0;
    }
    .btn-orange {
      background: var(--orange);
      color: var(--black);
      box-shadow: 0 4px 16px rgba(255, 103, 0, 0.25);
    }
    .btn-orange:hover,
    .btn-orange:focus {
      background: var(--orange-hover);
      box-shadow: 0 8px 28px rgba(255, 103, 0, 0.35);
    }
    /* HERO */
    .hero {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 5rem 2rem 3rem;
      text-align: center;
      background: linear-gradient(135deg, var(--black) 0%, var(--darker-grey) 100%);
      min-height: 70vh;
      position: relative;
      overflow: hidden;
    }
    .hero::before {
      content: '';
      position: absolute;
      width: 400px;
      height: 400px;
      background: radial-gradient(circle, rgba(255, 103, 0, 0.08) 0%, transparent 70%);
      border-radius: 50%;
      top: -200px;
      right: -100px;
      animation: float 6s ease-in-out infinite;
      z-index: 0;
    }
    .hero > * {
      position: relative;
      z-index: 1;
    }
    .hero h1 {
      font-size: 2.6rem;
      font-weight: 700;
      margin: 0 0 1.3rem;
      letter-spacing: -1px;
      line-height: 1.2;
      animation: slideInLeft 0.8s cubic-bezier(0.33, 0.86, 0, 1) 0.1s both;
    }
    .hero p {
      color: var(--secondary);
      font-size: 1.2rem;
      font-weight: 400;
      margin: 0 0 2.5rem;
      line-height: 1.65;
      max-width: 600px;
      animation: slideInRight 0.8s cubic-bezier(0.33, 0.86, 0, 1) 0.2s both;
    }
    .hero .btn-whatsapp {
      animation: scaleUpIn 0.8s cubic-bezier(0.33, 0.86, 0, 1) 0.4s both;
    }
    /* VIDEOS SECTION */
    .videos-container {
      width: 100%;
      padding: 4rem 2rem;
      background: var(--black);
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    .videos-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 2.5rem;
      width: 100%;
      max-width: 1200px;
      margin-bottom: 2rem;
    }
    .video-item {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 1.2rem;
    }
    .video-item video {
      width: 100%;
      height: auto;
      max-width: 350px;
      border-radius: 16px;
      background: #222;
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.5);
      border: 1px solid var(--border);
      transition: transform 0.3s cubic-bezier(0.23, 1, 0.32, 1),
                  box-shadow 0.3s;
      cursor: pointer;
    }
    .video-item video:hover {
      transform: scale(1.05) translateY(-8px);
      box-shadow: 0 12px 48px rgba(255, 103, 0, 0.2);
    }
    .video-title {
      font-size: 1.15rem;
      font-weight: 600;
      color: var(--orange);
      letter-spacing: 0.5px;
      text-transform: uppercase;
    }
    /* PROPUESTAS */
    .propuestas-section {
      width: 100%;
      background: var(--black);
      padding: 4rem 2rem;
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    .section-title {
      font-size: 2rem;
      font-weight: 700;
      margin-bottom: 3rem;
      color: var(--white);
      text-align: center;
      position: relative;
    }
    .section-title::after {
      content: '';
      display: block;
      width: 60px;
      height: 4px;
      background: var(--orange);
      border-radius: 2px;
      margin: 1rem auto 0;
    }
    .propuestas-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 2.5rem;
      width: 100%;
      max-width: 1000px;
    }
    .card {
      background: var(--dark-grey);
      color: var(--white);
      border: 1.5px solid var(--border);
      border-radius: 16px;
      padding: 2.2rem 1.8rem 2.5rem;
      display: flex;
      flex-direction: column;
      gap: 1.5rem;
      align-items: flex-start;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.5);
      transition: all 0.3s cubic-bezier(0.23, 1, 0.32, 1);
      will-change: transform;
      position: relative;
      overflow: hidden;
    }
    .card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: linear-gradient(135deg, rgba(255, 103, 0, 0.1) 0%, transparent 100%);
      opacity: 0;
      transition: opacity 0.3s;
      pointer-events: none;
    }
    .card:hover {
      transform: translateY(-12px) scale(1.03);
      box-shadow: 0 12px 40px rgba(255, 103, 0, 0.15);
      border-color: var(--orange);
    }
    .card:hover::before {
      opacity: 1;
    }
    .card.destacado {
      border: 2.5px solid var(--orange);
      background: linear-gradient(135deg, #1a1a1a 0%, #2d1200 100%);
      grid-column: 1 / -1;
      max-width: 100%;
    }
    .card.destacado::after {
      content: 'DESTACADO';
      position: absolute;
      top: 1.2rem;
      right: 1.5rem;
      background: var(--orange);
      color: var(--black);
      font-size: 0.85rem;
      font-weight: 700;
      padding: 0.4em 1.2em;
      border-radius: 100px;
      letter-spacing: 1px;
      z-index: 2;
      box-shadow: 0 4px 12px rgba(255, 103, 0, 0.3);
      animation: pulse 2s ease-in-out infinite;
    }
    .card-content {
      position: relative;
      z-index: 1;
      width: 100%;
    }
    .card-title {
      font-size: 1.3rem;
      font-weight: 700;
      color: var(--orange);
      margin-bottom: 0.5rem;
      letter-spacing: 0.5px;
    }
    .card-price {
      color: var(--white);
      font-size: 2.4rem;
      font-weight: 900;
      margin-bottom: 1rem;
      background: linear-gradient(135deg, var(--orange), #ff8c00);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    .card-details {
      font-size: 1.05rem;
      color: var(--secondary);
      margin-bottom: 1rem;
      min-height: 60px;
      line-height: 1.6;
    }
    .card-list {
      list-style: none;
      padding: 0;
      margin: 0;
      color: var(--secondary);
      font-size: 1rem;
    }
    .card-list li {
      padding: 0.4rem 0;
      padding-left: 1.5rem;
      position: relative;
    }
    .card-list li::before {
      content: '✓';
      position: absolute;
      left: 0;
      color: var(--orange);
      font-weight: bold;
    }
    .btn-card {
      margin-top: auto;
      width: 100%;
      position: relative;
      z-index: 2;
    }
    /* PORTAFOLIO TIKTOK */
    .portafolio-section {
      width: 100%;
      background: linear-gradient(135deg, var(--darker-grey) 0%, var(--black) 100%);
      padding: 4rem 2rem;
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
    }
    .portafolio-content {
      max-width: 800px;
    }
    .portafolio-title {
      font-size: 2.2rem;
      font-weight: 700;
      margin-bottom: 2rem;
      color: var(--white);
    }
    .tiktok-link {
      display: inline-flex;
      align-items: center;
      gap: 0.8rem;
      padding: 1rem 2.5rem;
      background: var(--dark-grey);
      border: 2px solid var(--orange);
      border-radius: 100px;
      color: var(--orange);
      font-weight: 700;
      font-size: 1.3rem;
      text-decoration: none;
      transition: all 0.3s cubic-bezier(0.23, 1, 0.32, 1);
      cursor: pointer;
      margin-bottom: 2rem;
    }
    .tiktok-link:hover,
    .tiktok-link:focus {
      background: var(--orange);
      color: var(--white);
      transform: scale(1.1) translateY(-3px);
      box-shadow: 0 12px 32px rgba(255, 103, 0, 0.3);
    }
    .tiktok-link svg {
      width: 1.8em;
      height: 1.8em;
      fill: currentColor;
    }
    .portafolio-desc {
      font-size: 1.15rem;
      color: var(--secondary);
      line-height: 1.8;
      margin-bottom: 2rem;
    }
    /* SOCIAL PROOF */
    .proof-section {
      padding: 4rem 2rem;
      display: flex;
      flex-direction: column;
      align-items: center;
      background: var(--black);
      text-align: center;
    }
    .proof-img {
      width: 140px;
      height: 140px;
      border-radius: 50%;
      object-fit: cover;
      margin-bottom: 1.5rem;
      border: 4px solid var(--orange);
      background: #181818;
      box-shadow: 0 8px 32px rgba(255, 103, 0, 0.2);
      animation: scaleUpIn 0.8s cubic-bezier(0.33, 0.86, 0, 1);
    }
    .proof-title {
      font-weight: 700;
      font-size: 1.3rem;
      color: var(--orange);
      margin-bottom: 1rem;
      letter-spacing: 0.5px;
    }
    .proof-desc {
      font-size: 1.15rem;
      color: var(--secondary);
      max-width: 500px;
      line-height: 1.8;
    }
    /* FOOTER */
    footer {
      background: var(--darker-grey);
      border-top: 1px solid var(--border);
      padding: 3rem 2rem 1.5rem;
      text-align: center;
    }
    .footer-links {
      display: flex;
      justify-content: center;
      gap: 2.5rem;
      margin-bottom: 1.5rem;
    }
    .footer-link {
      color: var(--orange);
      font-weight: 600;
      text-decoration: none;
      transition: all 0.2s;
      font-size: 1.1rem;
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
    }
    .footer-link:hover,
    .footer-link:focus {
      color: var(--green-ws);
      transform: translateY(-3px);
    }
    .footer-link svg {
      width: 1.4em;
      height: 1.4em;
      fill: currentColor;
    }
    .footer-copyright {
      color: var(--secondary);
      font-size: 0.95rem;
      letter-spacing: 0.3px;
    }
    /* RESPONSIVE */
    @media (max-width: 1024px) {
      .propuestas-grid {
        grid-template-columns: 1fr;
      }
      .card.destacado {
        grid-column: 1;
      }
    }
    @media (max-width: 900px) {
      .videos-grid {
        grid-template-columns: 1fr;
        max-width: 400px;
      }
      .propuestas-grid {
        max-width: 420px;
      }
      .hero h1 {
        font-size: 2rem;
      }
    }
    @media (max-width: 640px) {
      header {
        padding: 1rem 1rem;
      }
      .hero {
        padding: 3rem 1rem 2rem;
      }
      .hero h1 {
        font-size: 1.4rem;
      }
      .hero p {
        font-size: 1rem;
      }
      .videos-container,
      .propuestas-section,
      .portafolio-section,
      .proof-section,
      footer {
        padding: 3rem 1rem;
      }
      .section-title {
        font-size: 1.6rem;
      }
    }
    ::-webkit-scrollbar {
      width: 8px;
    }
    ::-webkit-scrollbar-track {
      background: var(--darker-grey);
    }
    ::-webkit-scrollbar-thumb {
      background: var(--orange);
      border-radius: 4px;
    }
    ::-webkit-scrollbar-thumb:hover {
      background: var(--orange-hover);
    }
  </style>
</head>
<body>
  <!-- HEADER -->
  <header>
    <div class="brand">Varnei Vargas</div>
    <a href="https://wa.me/584120497923?text=Hola%20Varnei%2C%20quiero%20saber%20m%C3%A1s" class="btn-whatsapp" target="_blank" rel="noopener">
      <svg viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.67-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.076 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421-7.403h-.004a9.87 9.87 0 00-5.031 1.378c-3.055 2.2-5.002 5.888-5.002 9.72 0 1.584.325 3.124.948 4.55L2.05 23.5l4.752-1.428c1.297.774 2.798 1.218 4.38 1.218h4.002c5.231 0 9.5-4.268 9.5-9.5 0-2.529-.977-4.9-2.75-6.694A9.478 9.478 0 0016.5 2.5c-5.23 0-9.5 4.269-9.5 9.5m9.5-8.5c4.136 0 7.5 3.364 7.5 7.5 0 4.137-3.364 7.5-7.5 7.5h-4c-1.203 0-2.357-.311-3.355-.9l-.241-.144-2.494.75.764-2.491-.158-.251a7.498 7.498 0 01-1.116-4.064c0-4.136 3.364-7.5 7.5-7.5" fill="currentColor"/></svg>
      WhatsApp
    </a>
  </header>

  <!-- HERO -->
  <section class="hero fade-in">
    <h1>Lo que sabes hacer merece ser visto. Convierte tus intereses en clientes.</h1>
    <p>Estructuramos tu marca. Planificamos contenido basado en identidad y audiencia. Edición incluida.</p>
    <a class="btn-whatsapp" href="https://wa.me/584120497923?text=Hola%20Varnei%2C%20quiero%20saber%20m%C3%A1s" target="_blank" rel="noopener">
      <svg viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.67-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.076 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421-7.403h-.004a9.87 9.87 0 00-5.031 1.378c-3.055 2.2-5.002 5.888-5.002 9.72 0 1.584.325 3.124.948 4.55L2.05 23.5l4.752-1.428c1.297.774 2.798 1.218 4.38 1.218h4.002c5.231 0 9.5-4.268 9.5-9.5 0-2.529-.977-4.9-2.75-6.694A9.478 9.478 0 0016.5 2.5c-5.23 0-9.5 4.269-9.5 9.5m9.5-8.5c4.136 0 7.5 3.364 7.5 7.5 0 4.137-3.364 7.5-7.5 7.5h-4c-1.203 0-2.357-.311-3.355-.9l-.241-.144-2.494.75.764-2.491-.158-.251a7.498 7.498 0 01-1.116-4.064c0-4.136 3.364-7.5 7.5-7.5" fill="currentColor"/></svg>
      WhatsApp
    </a>
  </section>

  <!-- VIDEOS -->
  <section class="videos-container fade-in">
    <h2 class="section-title">Ejemplos de mi trabajo</h2>
    <div class="videos-grid">
      <div class="video-item scale-in">
        <video controls poster="https://via.placeholder.com/350x500?text=Crecimiento">
          <source src="https://commondatastorage.googleapis.com/gtv-videos-library/sample/BigBuckBunny.mp4" type="video/mp4">
          Tu navegador no soporta el tag de video
        </video>
        <div class="video-title">Crecimiento</div>
      </div>
      <div class="video-item scale-in" style="animation-delay: 0.1s;">
        <video controls poster="https://via.placeholder.com/350x500?text=Posicionamiento">
          <source src="https://commondatastorage.googleapis.com/gtv-videos-library/sample/ElephantsDream.mp4" type="video/mp4">
          Tu navegador no soporta el tag de video
        </video>
        <div class="video-title">Posicionamiento</div>
      </div>
      <div class="video-item scale-in" style="animation-delay: 0.2s;">
        <video controls poster="https://via.placeholder.com/350x500?text=Conexión">
          <source src="https://commondatastorage.googleapis.com/gtv-videos-library/sample/ForBiggerBlazes.mp4" type="video/mp4">
          Tu navegador no soporta el tag de video
        </video>
        <div class="video-title">Conexión</div>
      </div>
    </div>
  </section>

  <!-- PROPUESTAS -->
  <section class="propuestas-section fade-in">
    <h2 class="section-title">Mis Propuestas</h2>
    <div class="propuestas-grid">
      <div class="card destacado scale-in">
        <div class="card-content">
          <div class="card-title">Sprint Estructural</div>
          <div class="card-price">$800*</div>
          <div class="card-details">Estructura completa tu presencia digital en 30 días</div>
          <ul class="card-list">
            <li>15 guiones de contenido</li>
            <li>Edición profesional</li>
            <li>Asesoría de marca</li>
            <li>30 días de seguimiento</li>
          </ul>
        </div>
        <a class="btn-whatsapp" href="https://wa.me/584120497923?text=Hola%20Varnei%2C%20me%20interesa%20el%20Sprint%20Estructural%20%24800" target="_blank" rel="noopener">
          <svg viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.67-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.076 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421-7.403h-.004a9.87 9.87 0 00-5.031 1.378c-3.055 2.2-5.002 5.888-5.002 9.72 0 1.584.325 3.124.948 4.55L2.05 23.5l4.752-1.428c1.297.774 2.798 1.218 4.38 1.218h4.002c5.231 0 9.5-4.268 9.5-9.5 0-2.529-.977-4.9-2.75-6.694A9.478 9.478 0 0016.5 2.5c-5.23 0-9.5 4.269-9.5 9.5m9.5-8.5c4.136 0 7.5 3.364 7.5 7.5 0 4.137-3.364 7.5-7.5 7.5h-4c-1.203 0-2.357-.311-3.355-.9l-.241-.144-2.494.75.764-2.491-.158-.251a7.498 7.498 0 01-1.116-4.064c0-4.136 3.364-7.5 7.5-7.5" fill="currentColor"/></svg>
          Solicitar ahora
        </a>
      </div>
      <div class="card scale-in">
        <div class="card-content">
          <div class="card-title">Edición de Videos</div>
          <div class="card-price">$10<span style="font-size: 1rem;">/clip</span></div>
          <div class="card-details">Edición profesional para tus clips</div>
          <ul class="card-list">
            <li>CapCut de última generación</li>
            <li>Color grading profesional</li>
            <li>Diseño de audio avanzado</li>
            <li>Subtítulos optimizados</li>
          </ul>
        </div>
        <a class="btn-whatsapp" href="https://wa.me/584120497923?text=Hola%20Varnei%2C%20quiero%20editar%20mis%20videos%20%2410%2Fclip" target="_blank" rel="noopener">
          <svg viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.67-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.076 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421-7.403h-.004a9.87 9.87 0 00-5.031 1.378c-3.055 2.2-5.002 5.888-5.002 9.72 0 1.584.325 3.124.948 4.55L2.05 23.5l4.752-1.428c1.297.774 2.798 1.218 4.38 1.218h4.002c5.231 0 9.5-4.268 9.5-9.5 0-2.529-.977-4.9-2.75-6.694A9.478 9.478 0 0016.5 2.5c-5.23 0-9.5 4.269-9.5 9.5m9.5-8.5c4.136 0 7.5 3.364 7.5 7.5 0 4.137-3.364 7.5-7.5 7.5h-4c-1.203 0-2.357-.311-3.355-.9l-.241-.144-2.494.75.764-2.491-.158-.251a7.498 7.498 0 01-1.116-4.064c0-4.136 3.364-7.5 7.5-7.5" fill="currentColor"/></svg>
          Solicitar ahora
        </a>
      </div>
      <div class="card scale-in">
        <div class="card-content">
          <div class="card-title">Asesoría Digital</div>
          <div class="card-price">$682</div>
          <div class="card-details">Plan estratégico personalizado de 90 días</div>
          <ul class="card-list">
            <li>Diagnóstico profundo</li>
            <li>Estrategia 90 días</li>
            <li>4 sesiones asesoría</li>
            <li>Seguimiento continuo</li>
          </ul>
        </div>
        <a class="btn-whatsapp" href="https://wa.me/584120497923?text=Hola%20Varnei%2C%20me%20interesa%20la%20Asesor%C3%ADa%20Digital%20%24682" target="_blank" rel="noopener">
          <svg viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.67-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.076 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421-7.403h-.004a9.87 9.87 0 00-5.031 1.378c-3.055 2.2-5.002 5.888-5.002 9.72 0 1.584.325 3.124.948 4.55L2.05 23.5l4.752-1.428c1.297.774 2.798 1.218 4.38 1.218h4.002c5.231 0 9.5-4.268 9.5-9.5 0-2.529-.977-4.9-2.75-6.694A9.478 9.478 0 0016.5 2.5c-5.23 0-9.5 4.269-9.5 9.5m9.5-8.5c4.136 0 7.5 3.364 7.5 7.5 0 4.137-3.364 7.5-7.5 7.5h-4c-1.203 0-2.357-.311-3.355-.9l-.241-.144-2.494.75.764-2.491-.158-.251a7.498 7.498 0 01-1.116-4.064c0-4.136 3.364-7.5 7.5-7.5" fill="currentColor"/></svg>
          Solicitar ahora
        </a>
      </div>
      <div class="card scale-in">
        <div class="card-content">
          <div class="card-title">Combo Total</div>
          <div class="card-price">$1000</div>
          <div class="card-details">Paquete completo de 30 días</div>
          <ul class="card-list">
            <li>8 clips editados</li>
            <li>15 guiones</li>
            <li>Branding completo</li>
            <li>Seguimiento 1 mes</li>
          </ul>
        </div>
        <a class="btn-whatsapp" href="https://wa.me/584120497923?text=Hola%20Varnei%2C%20me%20interesa%20el%20Combo%20Total%20%241000" target="_blank" rel="noopener">
          <svg viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.67-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.076 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421-7.403h-.004a9.87 9.87 0 00-5.031 1.378c-3.055 2.2-5.002 5.888-5.002 9.72 0 1.584.325 3.124.948 4.55L2.05 23.5l4.752-1.428c1.297.774 2.798 1.218 4.38 1.218h4.002c5.231 0 9.5-4.268 9.5-9.5 0-2.529-.977-4.9-2.75-6.694A9.478 9.478 0 0016.5 2.5c-5.23 0-9.5 4.269-9.5 9.5m9.5-8.5c4.136 0 7.5 3.364 7.5 7.5 0 4.137-3.364 7.5-7.5 7.5h-4c-1.203 0-2.357-.311-3.355-.9l-.241-.144-2.494.75.764-2.491-.158-.251a7.498 7.498 0 01-1.116-4.064c0-4.136 3.364-7.5 7.5-7.5" fill="currentColor"/></svg>
          Solicitar ahora
        </a>
      </div>
    </div>
  </section>

  <!-- PORTAFOLIO TIKTOK -->
  <section class="portafolio-section fade-in">
    <div class="portafolio-content">
      <h2 class="portafolio-title">Mi Portafolio en TikTok</h2>
      <p class="portafolio-desc">
        Descubre los proyectos que he desarrollado y los resultados que he logrado con mis clientes. Cada video representa estrategia, creatividad y ejecución de alto nivel.
      </p>
      <a href="https://tiktok.com/@varneivargas" target="_blank" rel="noopener" class="tiktok-link">
        <svg viewBox="0 0 24 24"><path d="M19.59 6.69a4.83 4.83 0 0 1-3.77-4.25V2h-3.45v13.67a2.89 2.89 0 0 1-5.1 1.75 2.9 2.9 0 0 1 2.31-4.64 2.93 2.93 0 0 1 .88.13V9.4a6.84 6.84 0 0 0-1-.06A6.33 6.33 0 0 0 5 20.1a6.34 6.34 0 0 0 10.86-4.43h-2.54a3.83 3.83 0 0 1-3.8-3.83V8.63a6.37 6.37 0 0 0 9.59-5.84v-3.1zm4.41 7.15h3V2h-3z" fill="currentColor"/></svg>
        @varneivargas
      </a>
    </div>
  </section>

  <!-- SOCIAL PROOF -->
  <section class="proof-section fade-in">
    <img src="https://pbs.twimg.com/profile_images/1585639988256567298/v8I5zTiS_400x400.jpg" alt="Varnei Vargas" class="proof-img" />
    <div class="proof-title">Sé cómo darle orden a marca</div>
    <p class="proof-desc">Optimizo branding para generar audiencias que conviertan clientes. Transformo intereses en estrategias, y estrategias en resultados medibles.</p>
  </section>

  <!-- FOOTER -->
  <footer>
    <div class="footer-links">
      <a class="footer-link" href="https://wa.me/584120497923?text=Hola%20Varnei%2C%20quiero%20saber%20m%C3%A1s" target="_blank" rel="noopener">
        <svg viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.67-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.076 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421-7.403h-.004a9.87 9.87 0 00-5.031 1.378c-3.055 2.2-5.002 5.888-5.002 9.72 0 1.584.325 3.124.948 4.55L2.05 23.5l4.752-1.428c1.297.774 2.798 1.218 4.38 1.218h4.002c5.231 0 9.5-4.268 9.5-9.5 0-2.529-.977-4.9-2.75-6.694A9.478 9.478 0 0016.5 2.5c-5.23 0-9.5 4.269-9.5 9.5m9.5-8.5c4.136 0 7.5 3.364 7.5 7.5 0 4.137-3.364 7.5-7.5 7.5h-4c-1.203 0-2.357-.311-3.355-.9l-.241-.144-2.494.75.764-2.491-.158-.251a7.498 7.498 0 01-1.116-4.064c0-4.136 3.364-7.5 7.5-7.5" fill="currentColor"/></svg>
        WhatsApp
      </a>
      <a class="footer-link" href="https://tiktok.com/@varneivargas" target="_blank" rel="noopener">
        <svg viewBox="0 0 24 24"><path d="M19.59 6.69a4.83 4.83 0 0 1-3.77-4.25V2h-3.45v13.67a2.89 2.89 0 0 1-5.1 1.75 2.9 2.9 0 0 1 2.31-4.64 2.93 2.93 0 0 1 .88.13V9.4a6.84 6.84 0 0 0-1-.06A6.33 6.33 0 0 0 5 20.1a6.34 6.34 0 0 0 10.86-4.43h-2.54a3.83 3.83 0 0 1-3.8-3.83V8.63a6.37 6.37 0 0 0 9.59-5.84v-3.1zm4.41 7.15h3V2h-3z" fill="currentColor"/></svg>
        TikTok
      </a>
    </div>
    <div class="footer-copyright">
      © 2026 Varnei Vargas. Contenido que conecta.
    </div>
  </footer>

  <!-- SCRIPT ANIMACIONES -->
  <script>
    // Fade-in on scroll
    function observeElements() {
      const elements = document.querySelectorAll('.fade-in, .slide-left, .slide-right, .scale-in');
      const windowHeight = window.innerHeight;

      elements.forEach(element => {
        const elementTop = element.getBoundingClientRect().top;
        if (elementTop < windowHeight - 60) {
          element.classList.add('visible');
        }
      });
    }

    // Observer para animaciones suaves
    const observer = new IntersectionObserver(entries => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
          observer.unobserve(entry.target);
        }
      });
    }, { threshold: 0.1 });

    document.querySelectorAll('.fade-in, .scale-in, .slide-left, .slide-right').forEach(el => {
      observer.observe(el);
    });

    window.addEventListener('DOMContentLoaded', observeElements);
    window.addEventListener('scroll', observeElements);

    // Parallax efecto suave
    window.addEventListener('scroll', () => {
      const scrolled = window.pageYOffset;
      const parallaxElements = document.querySelectorAll('.parallax');
      parallaxElements.forEach(el => {
        el.style.transform = `translateY(${scrolled * 0.5}px)`;
      });
    });
  </script>
</body>
</html>