# kaarigai-isai
website
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kaarigai Isai | Tamil Music Creator</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=Cinzel+Decorative:wght@400;700&family=Cinzel:wght@400;600;700&family=Lato:wght@300;400;700&display=swap" rel="stylesheet">
<style>
  :root {
    --gold: #c9a84c;
    --gold-light: #f0d080;
    --gold-dark: #8a6a1e;
    --bg-black: #0a0806;
    --bg-dark: #110e08;
    --bg-card: #1a1508;
    --text-light: #f5ead8;
    --text-muted: #a89070;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }
  body { background: var(--bg-black); color: var(--text-light); font-family: 'Lato', sans-serif; overflow-x: hidden; }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.2rem 5vw;
    background: rgba(10,8,6,0.95); border-bottom: 1px solid rgba(201,168,76,0.15);
    backdrop-filter: blur(8px);
  }
  .nav-logo { font-family: 'Cinzel Decorative', serif; font-size: 1.2rem; color: var(--gold); text-decoration: none; letter-spacing: 0.05em; display: flex; flex-direction: column; line-height: 1.2; }
  .nav-logo span { font-family: 'Lato', sans-serif; font-size: 0.62rem; color: var(--text-muted); letter-spacing: 0.25em; text-transform: uppercase; }
  .nav-links { display: flex; gap: 2.5rem; list-style: none; }
  .nav-links a { color: var(--text-muted); text-decoration: none; font-size: 0.8rem; letter-spacing: 0.15em; text-transform: uppercase; transition: color 0.3s; }
  .nav-links a:hover { color: var(--gold); }
  .nav-cta { background: transparent; border: 1px solid var(--gold); color: var(--gold); padding: 0.55rem 1.4rem; font-size: 0.75rem; letter-spacing: 0.12em; text-transform: uppercase; cursor: pointer; transition: all 0.3s; text-decoration: none; }
  .nav-cta:hover { background: var(--gold); color: var(--bg-black); }

  /* HERO */
  .hero { min-height: 100vh; display: flex; align-items: center; justify-content: center; position: relative; overflow: hidden; background: radial-gradient(ellipse at 60% 40%, #1e1505 0%, var(--bg-black) 70%); }
  .hero-bg { position: absolute; inset: 0; background-image: radial-gradient(circle at 20% 80%, rgba(201,168,76,0.06) 0%, transparent 50%), radial-gradient(circle at 80% 20%, rgba(201,168,76,0.04) 0%, transparent 50%); }
  .staff-lines { position: absolute; inset: 0; pointer-events: none; opacity: 0.06; }
  .staff-lines::before { content: ''; position: absolute; inset: 0; background: repeating-linear-gradient(0deg, transparent, transparent 38px, rgba(201,168,76,0.9) 38px, rgba(201,168,76,0.9) 39px); transform: rotate(-5deg) scaleX(1.4); }
  .note { position: absolute; color: var(--gold); opacity: 0; animation: floatNote 6s ease-in-out infinite; }
  .note:nth-child(1){left:10%;top:20%;font-size:1.5rem;animation-delay:0s}
  .note:nth-child(2){left:75%;top:15%;font-size:2.5rem;animation-delay:1.5s}
  .note:nth-child(3){left:85%;top:60%;font-size:1.8rem;animation-delay:3s}
  .note:nth-child(4){left:5%;top:70%;font-size:2rem;animation-delay:4.5s}
  .note:nth-child(5){left:50%;top:85%;font-size:1.2rem;animation-delay:2s}
  @keyframes floatNote { 0%{opacity:0;transform:translateY(0) rotate(0deg)} 20%{opacity:0.35} 80%{opacity:0.2} 100%{opacity:0;transform:translateY(-80px) rotate(15deg)} }

  .hero-content { position: relative; text-align: center; max-width: 820px; padding: 2rem; }
  .hero-label { display: inline-block; font-size: 0.72rem; letter-spacing: 0.35em; text-transform: uppercase; color: var(--gold); border: 1px solid rgba(201,168,76,0.4); padding: 0.4rem 1.2rem; margin-bottom: 2rem; animation: fadeUp 0.8s ease both; }
  .hero-title { font-family: 'Cinzel Decorative', serif; font-size: clamp(2.5rem, 7vw, 5.5rem); font-weight: 700; line-height: 1.1; background: linear-gradient(135deg, var(--gold-light) 0%, var(--gold) 50%, var(--gold-dark) 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; margin-bottom: 0.5rem; animation: fadeUp 0.9s 0.1s ease both; }
  .hero-sub { font-family: 'Cinzel', serif; font-size: clamp(0.85rem, 2vw, 1.1rem); color: var(--text-muted); letter-spacing: 0.3em; text-transform: uppercase; margin-bottom: 2rem; animation: fadeUp 0.9s 0.2s ease both; }
  .hero-desc { font-size: clamp(1rem, 2vw, 1.15rem); color: var(--text-muted); line-height: 1.9; margin-bottom: 3rem; animation: fadeUp 0.9s 0.3s ease both; }
  .hero-buttons { display: flex; gap: 1.2rem; justify-content: center; flex-wrap: wrap; animation: fadeUp 0.9s 0.4s ease both; }
  .btn-primary { background: linear-gradient(135deg, var(--gold-dark), var(--gold)); color: var(--bg-black); border: none; padding: 1rem 2.5rem; font-size: 0.85rem; letter-spacing: 0.12em; text-transform: uppercase; cursor: pointer; font-weight: 700; transition: all 0.3s; text-decoration: none; display: inline-block; }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 30px rgba(201,168,76,0.35); }
  .btn-secondary { background: transparent; border: 1px solid rgba(201,168,76,0.5); color: var(--gold); padding: 1rem 2.5rem; font-size: 0.85rem; letter-spacing: 0.12em; text-transform: uppercase; cursor: pointer; transition: all 0.3s; text-decoration: none; display: inline-block; }
  .btn-secondary:hover { border-color: var(--gold); background: rgba(201,168,76,0.08); }
  .scroll-hint { position: absolute; bottom: 2.5rem; left: 50%; transform: translateX(-50%); display: flex; flex-direction: column; align-items: center; gap: 0.5rem; color: var(--text-muted); font-size: 0.68rem; letter-spacing: 0.25em; text-transform: uppercase; animation: bounce 2s ease infinite; }
  .scroll-hint::after { content: ''; width: 1px; height: 40px; background: linear-gradient(to bottom, var(--gold), transparent); }
  @keyframes bounce { 0%,100%{transform:translateX(-50%) translateY(0)} 50%{transform:translateX(-50%) translateY(8px)} }
  @keyframes fadeUp { from{opacity:0;transform:translateY(30px)} to{opacity:1;transform:translateY(0)} }

  /* SECTION */
  section { padding: 6rem 5vw; }
  .section-tag { font-size: 0.68rem; letter-spacing: 0.4em; text-transform: uppercase; color: var(--gold); margin-bottom: 1rem; display: block; }
  .section-title { font-family: 'Playfair Display', serif; font-size: clamp(1.8rem, 4vw, 3rem); font-weight: 700; color: var(--text-light); line-height: 1.2; margin-bottom: 1.5rem; }
  .section-title .gold { color: var(--gold); }
  .section-subtitle { color: var(--text-muted); max-width: 560px; line-height: 1.9; font-size: 1.05rem; }

  /* ABOUT */
  .about { background: var(--bg-dark); }
  .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: center; }
  .about-visual { position: relative; width: 100%; aspect-ratio: 1; max-width: 400px; }
  .about-circle { width: 100%; height: 100%; border-radius: 50%; border: 1px solid rgba(201,168,76,0.2); display: flex; align-items: center; justify-content: center; position: relative; }
  .about-circle::before { content: ''; position: absolute; inset: 12px; border-radius: 50%; border: 1px solid rgba(201,168,76,0.1); }
  .about-circle::after { content: ''; position: absolute; inset: 28px; border-radius: 50%; background: radial-gradient(ellipse, rgba(201,168,76,0.08) 0%, transparent 70%); }
  .orbit { position: absolute; inset: -15px; border-radius: 50%; animation: spin 20s linear infinite; }
  .orbit-dot { position: absolute; top: 0; left: 50%; transform: translateX(-50%); width: 8px; height: 8px; background: var(--gold); border-radius: 50%; opacity: 0.6; }
  @keyframes spin { from{transform:rotate(0deg)} to{transform:rotate(360deg)} }
  .about-inner { display: flex; flex-direction: column; align-items: center; gap: 0.6rem; z-index: 1; }
  .about-icon { font-size: 5rem; animation: pulse 3s ease infinite; }
  @keyframes pulse { 0%,100%{transform:scale(1)} 50%{transform:scale(1.06)} }
  .about-badge { font-family: 'Cinzel', serif; font-size: 0.75rem; letter-spacing: 0.2em; color: var(--gold); border: 1px solid rgba(201,168,76,0.3); padding: 0.3rem 0.8rem; }
  .about-stats { display: flex; gap: 2.5rem; margin-top: 2.5rem; flex-wrap: wrap; }
  .stat { border-left: 2px solid var(--gold); padding-left: 1rem; }
  .stat-num { font-family: 'Playfair Display', serif; font-size: 2.2rem; color: var(--gold); font-weight: 700; line-height: 1; }
  .stat-label { font-size: 0.72rem; color: var(--text-muted); letter-spacing: 0.1em; margin-top: 0.2rem; text-transform: uppercase; }

  /* SERVICES */
  .services-header { text-align: center; margin-bottom: 4rem; }
  .services-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1.5rem; }
  .service-card { background: var(--bg-card); border: 1px solid rgba(201,168,76,0.12); padding: 2.5rem 2rem; position: relative; overflow: hidden; transition: all 0.4s; }
  .service-card::before { content: ''; position: absolute; bottom: 0; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, transparent, var(--gold), transparent); transform: scaleX(0); transition: transform 0.4s; }
  .service-card:hover { transform: translateY(-4px); border-color: rgba(201,168,76,0.3); }
  .service-card:hover::before { transform: scaleX(1); }
  .service-icon { font-size: 2.5rem; margin-bottom: 1.2rem; display: block; }
  .service-card h3 { font-family: 'Playfair Display', serif; font-size: 1.2rem; color: var(--text-light); margin-bottom: 0.8rem; }
  .service-card p { color: var(--text-muted); font-size: 0.9rem; line-height: 1.75; }
  .service-num { position: absolute; top: 1.5rem; right: 1.5rem; font-family: 'Cinzel Decorative', serif; font-size: 2.5rem; color: rgba(201,168,76,0.07); font-weight: 700; line-height: 1; }

  /* PORTFOLIO */
  .portfolio { background: var(--bg-dark); }
  .portfolio-header { margin-bottom: 4rem; }
  .portfolio-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1rem; }
  .portfolio-item { background: var(--bg-card); border: 1px solid rgba(201,168,76,0.1); position: relative; overflow: hidden; cursor: pointer; transition: all 0.4s; aspect-ratio: 4/3; display: flex; align-items: flex-end; }
  .portfolio-item:first-child { grid-column: span 2; aspect-ratio: 16/7; }
  .portfolio-item:hover { border-color: rgba(201,168,76,0.4); }
  .item-bg { position: absolute; inset: 0; display: flex; align-items: center; justify-content: center; font-size: 5rem; opacity: 0.12; transition: all 0.4s; }
  .portfolio-item:hover .item-bg { opacity: 0.22; transform: scale(1.06); }
  .portfolio-overlay { position: absolute; inset: 0; background: linear-gradient(to top, rgba(10,8,6,0.95) 0%, transparent 60%); }
  .portfolio-info { position: relative; z-index: 1; padding: 1.5rem; width: 100%; }
  .portfolio-genre { font-size: 0.62rem; letter-spacing: 0.3em; color: var(--gold); text-transform: uppercase; margin-bottom: 0.4rem; }
  .portfolio-title { font-family: 'Playfair Display', serif; font-size: 1.1rem; color: var(--text-light); }
  .pi-1 .item-bg{color:#c9a84c} .pi-2 .item-bg{color:#e85d2f} .pi-3 .item-bg{color:#4ca8c9} .pi-4 .item-bg{color:#c94ca8} .pi-5 .item-bg{color:#4cc98a}

  /* PROCESS */
  .process-header { text-align: center; margin-bottom: 4rem; }
  .process-steps { display: flex; position: relative; }
  .process-steps::before { content: ''; position: absolute; top: 2.2rem; left: 2.5rem; right: 2.5rem; height: 1px; background: linear-gradient(90deg, transparent, var(--gold-dark), transparent); }
  .step { flex: 1; text-align: center; padding: 0 1rem; }
  .step-num { width: 4.5rem; height: 4.5rem; border-radius: 50%; border: 1px solid var(--gold); background: var(--bg-black); display: flex; align-items: center; justify-content: center; margin: 0 auto 1.5rem; font-family: 'Cinzel', serif; font-size: 1rem; color: var(--gold); letter-spacing: 0.1em; }
  .step h4 { font-family: 'Playfair Display', serif; font-size: 1rem; color: var(--text-light); margin-bottom: 0.5rem; }
  .step p { color: var(--text-muted); font-size: 0.82rem; line-height: 1.65; }

  /* TESTIMONIALS */
  .testimonials { background: var(--bg-dark); }
  .testimonials-header { text-align: center; margin-bottom: 4rem; }
  .testimonials-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; }
  .testimonial { background: var(--bg-card); border: 1px solid rgba(201,168,76,0.1); padding: 2rem; position: relative; }
  .testimonial::before { content: '"'; position: absolute; top: 1rem; right: 1.5rem; font-family: 'Playfair Display', serif; font-size: 5rem; color: rgba(201,168,76,0.1); line-height: 1; }
  .stars { color: var(--gold); font-size: 0.85rem; margin-bottom: 1rem; }
  .testimonial p { color: var(--text-muted); line-height: 1.8; margin-bottom: 1.5rem; font-style: italic; font-size: 0.95rem; }
  .testi-author { display: flex; align-items: center; gap: 1rem; }
  .testi-avatar { width: 42px; height: 42px; border-radius: 50%; background: linear-gradient(135deg, var(--gold-dark), var(--gold)); display: flex; align-items: center; justify-content: center; font-family: 'Playfair Display', serif; font-weight: 700; font-size: 1.1rem; color: var(--bg-black); }
  .testi-name { font-weight: 700; font-size: 0.9rem; }
  .testi-role { font-size: 0.75rem; color: var(--text-muted); }

  /* CONTACT */
  .contact-wrap { display: grid; grid-template-columns: 1fr 1.2fr; gap: 5rem; align-items: start; }
  .contact-info-block { margin-bottom: 2rem; }
  .contact-info-block h4 { color: var(--gold); font-size: 0.72rem; letter-spacing: 0.2em; text-transform: uppercase; margin-bottom: 0.4rem; }
  .contact-info-block p { color: var(--text-muted); line-height: 1.6; }
  .contact-form { display: flex; flex-direction: column; gap: 1rem; }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  .form-field { display: flex; flex-direction: column; gap: 0.4rem; }
  .form-field label { font-size: 0.7rem; letter-spacing: 0.15em; color: var(--text-muted); text-transform: uppercase; }
  .form-field input, .form-field textarea, .form-field select { background: rgba(201,168,76,0.04); border: 1px solid rgba(201,168,76,0.2); color: var(--text-light); padding: 0.9rem 1.1rem; font-size: 0.9rem; font-family: 'Lato', sans-serif; outline: none; transition: border-color 0.3s; width: 100%; }
  .form-field input:focus, .form-field textarea:focus, .form-field select:focus { border-color: var(--gold); }
  .form-field select option { background: var(--bg-dark); }
  .form-field textarea { resize: vertical; min-height: 120px; }
  .submit-btn { background: linear-gradient(135deg, var(--gold-dark), var(--gold)); color: var(--bg-black); border: none; padding: 1.1rem; font-size: 0.88rem; letter-spacing: 0.12em; text-transform: uppercase; cursor: pointer; font-weight: 700; transition: all 0.3s; margin-top: 0.5rem; font-family: 'Lato', sans-serif; }
  .submit-btn:hover { box-shadow: 0 8px 30px rgba(201,168,76,0.35); transform: translateY(-2px); }

  /* FOOTER */
  footer { background: #060504; border-top: 1px solid rgba(201,168,76,0.15); padding: 4rem 5vw 2rem; }
  .footer-top { display: grid; grid-template-columns: 1.5fr 1fr 1fr; gap: 3rem; margin-bottom: 3rem; }
  .footer-brand .logo { font-family: 'Cinzel Decorative', serif; font-size: 1.1rem; color: var(--gold); margin-bottom: 0.3rem; }
  .footer-brand .tagline { font-size: 0.68rem; color: var(--text-muted); letter-spacing: 0.2em; text-transform: uppercase; margin-bottom: 1rem; }
  .footer-brand p { color: var(--text-muted); font-size: 0.85rem; line-height: 1.75; max-width: 280px; }
  .footer-col h5 { font-size: 0.68rem; letter-spacing: 0.25em; text-transform: uppercase; color: var(--gold); margin-bottom: 1.2rem; }
  .footer-col ul { list-style: none; }
  .footer-col ul li { margin-bottom: 0.6rem; }
  .footer-col ul li a { color: var(--text-muted); text-decoration: none; font-size: 0.88rem; transition: color 0.3s; }
  .footer-col ul li a:hover { color: var(--gold); }
  .footer-bottom { border-top: 1px solid rgba(201,168,76,0.1); padding-top: 1.5rem; display: flex; justify-content: space-between; align-items: center; }
  .footer-bottom p { color: var(--text-muted); font-size: 0.78rem; }
  .social-links { display: flex; gap: 1rem; }
  .social-links a { width: 36px; height: 36px; border: 1px solid rgba(201,168,76,0.25); display: flex; align-items: center; justify-content: center; color: var(--text-muted); text-decoration: none; font-size: 1rem; transition: all 0.3s; }
  .social-links a:hover { border-color: var(--gold); color: var(--gold); }

  /* PLAY BARS */
  .play-wave { display: flex; align-items: center; gap: 3px; height: 24px; }
  .bar { width: 3px; background: var(--gold); border-radius: 2px; animation: wave 1.2s ease-in-out infinite; }
  .bar:nth-child(1){height:8px;animation-delay:0s} .bar:nth-child(2){height:16px;animation-delay:0.1s} .bar:nth-child(3){height:24px;animation-delay:0.2s} .bar:nth-child(4){height:16px;animation-delay:0.3s} .bar:nth-child(5){height:8px;animation-delay:0.4s}
  @keyframes wave { 0%,100%{transform:scaleY(0.4);opacity:0.5} 50%{transform:scaleY(1);opacity:1} }

  /* NOW PLAYING */
  .now-playing { position: fixed; bottom: 1.5rem; right: 1.5rem; z-index: 90; background: var(--bg-card); border: 1px solid rgba(201,168,76,0.3); padding: 0.8rem 1.2rem; display: flex; align-items: center; gap: 0.8rem; box-shadow: 0 4px 30px rgba(0,0,0,0.5); transform: translateY(100px); opacity: 0; animation: slideUp 0.5s 1.5s ease forwards; }
  @keyframes slideUp { to{transform:translateY(0);opacity:1} }
  .np-text { font-size: 0.78rem; }
  .np-text span { color: var(--gold); display: block; font-size: 0.65rem; letter-spacing: 0.12em; text-transform: uppercase; }
  .np-text strong { color: var(--text-light); }
  .np-close { position: absolute; top: 0.3rem; right: 0.5rem; background: none; border: none; color: var(--text-muted); cursor: pointer; font-size: 0.8rem; }

  /* RESPONSIVE */
  @media (max-width:900px) {
    .about-grid { grid-template-columns: 1fr; }
    .about-visual { max-width: 260px; margin: 0 auto; }
    .portfolio-grid { grid-template-columns: 1fr 1fr; }
    .portfolio-item:first-child { grid-column: 1 / -1; }
    .process-steps { flex-direction: column; gap: 2rem; }
    .process-steps::before { display: none; }
    .contact-wrap { grid-template-columns: 1fr; }
    .footer-top { grid-template-columns: 1fr; }
    .nav-links { display: none; }
  }
  @media (max-width:600px) {
    .portfolio-grid { grid-template-columns: 1fr; }
    .form-row { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-logo" href="#">
    Kaarigai Isai
    <span>Tamil Music Creator</span>
  </a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#portfolio">Portfolio</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="#contact" class="nav-cta">Book a Session</a>
</nav>

<!-- NOW PLAYING -->
<div class="now-playing" id="nowPlaying">
  <button class="np-close" onclick="document.getElementById('nowPlaying').style.display='none'">✕</button>
  <div class="play-wave">
    <div class="bar"></div><div class="bar"></div><div class="bar"></div>
    <div class="bar"></div><div class="bar"></div>
  </div>
  <div class="np-text">
    <span>Now Playing</span>
    <strong>Ragam — Vasantha</strong>
  </div>
</div>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-bg"></div>
  <div class="staff-lines"></div>
  <div class="note">♩</div>
  <div class="note">♫</div>
  <div class="note">♪</div>
  <div class="note">𝄞</div>
  <div class="note">♬</div>
  <div class="hero-content">
    <div class="hero-label">✦ Tamil Classical & Folk Music ✦</div>
    <h1 class="hero-title">Kaarigai Isai</h1>
    <p class="hero-sub">Where Tradition Meets Sound</p>
    <p class="hero-desc">
      We craft soulful Tamil music that bridges centuries of heritage<br>
      with the pulse of modern creativity — one note at a time.
    </p>
    <div class="hero-buttons">
      <a href="#portfolio" class="btn-primary">Explore Our Work →</a>
      <a href="#contact" class="btn-secondary">Book a Session</a>
    </div>
  </div>
  <div class="scroll-hint">Scroll</div>
</section>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="about-grid">
    <div class="about-visual">
      <div class="about-circle">
        <div class="orbit"><div class="orbit-dot"></div></div>
        <div class="about-inner">
          <span class="about-icon">🎵</span>
          <span class="about-badge">Est. 2015</span>
        </div>
      </div>
    </div>
    <div>
      <span class="section-tag">✦ About Us</span>
      <h2 class="section-title">Music is an Art —<br><span class="gold">We Bring It to Life</span></h2>
      <p class="section-subtitle">
        Kaarigai Isai is a Tamil music creation studio blending the richness of Carnatic tradition
        with contemporary production techniques. From folk melodies to film scores, we bring your
        musical vision to life with passion and precision.
      </p>
      <div class="about-stats">
        <div class="stat"><div class="stat-num">500+</div><div class="stat-label">Songs Composed</div></div>
        <div class="stat"><div class="stat-num">150+</div><div class="stat-label">Artists Worked With</div></div>
        <div class="stat"><div class="stat-num">10+</div><div class="stat-label">Years Experience</div></div>
        <div class="stat"><div class="stat-num">50+</div><div class="stat-label">Awards Won</div></div>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section id="services">
  <div class="services-header">
    <span class="section-tag">✦ What We Offer</span>
    <h2 class="section-title">Our <span class="gold">Services</span></h2>
  </div>
  <div class="services-grid">
    <div class="service-card"><span class="service-num">01</span><span class="service-icon">🎼</span><h3>Music Composition</h3><p>Original compositions across Carnatic, Folk, and Film genres — crafted to evoke emotion and tell your story.</p></div>
    <div class="service-card"><span class="service-num">02</span><span class="service-icon">🎤</span><h3>Vocal Recording</h3><p>Professional studio recording sessions delivering crystal-clear sound quality for every voice and style.</p></div>
    <div class="service-card"><span class="service-num">03</span><span class="service-icon">🥁</span><h3>Beat Production</h3><p>From traditional Mridangam to modern beats — we create the perfect rhythmic foundation for your track.</p></div>
    <div class="service-card"><span class="service-num">04</span><span class="service-icon">🎹</span><h3>Music Arrangement</h3><p>Full orchestral arrangements that transform your melody into a grand, immersive sonic experience.</p></div>
    <div class="service-card"><span class="service-num">05</span><span class="service-icon">🎧</span><h3>Mixing & Mastering</h3><p>Industry-standard mixing and mastering to ensure your track sounds polished and release-ready.</p></div>
    <div class="service-card"><span class="service-num">06</span><span class="service-icon">🎻</span><h3>Live Performance</h3><p>Full live performance arrangements for events, weddings, concerts, and corporate functions.</p></div>
  </div>
</section>

<!-- PORTFOLIO -->
<section class="portfolio" id="portfolio">
  <div class="portfolio-header">
    <span class="section-tag">✦ Our Work</span>
    <h2 class="section-title">Featured <span class="gold">Creations</span></h2>
  </div>
  <div class="portfolio-grid">
    <div class="portfolio-item pi-1"><div class="item-bg">𝄞</div><div class="portfolio-overlay"></div><div class="portfolio-info"><div class="portfolio-genre">Carnatic Classical</div><div class="portfolio-title">Vasantha Panchamam — Ragam Vasantha</div></div></div>
    <div class="portfolio-item pi-2"><div class="item-bg">🥁</div><div class="portfolio-overlay"></div><div class="portfolio-info"><div class="portfolio-genre">Folk Music</div><div class="portfolio-title">The Cuckoo's Call</div></div></div>
    <div class="portfolio-item pi-3"><div class="item-bg">🎸</div><div class="portfolio-overlay"></div><div class="portfolio-info"><div class="portfolio-genre">Tamil Fusion</div><div class="portfolio-title">City Sounds — Urban Fusion</div></div></div>
    <div class="portfolio-item pi-4"><div class="item-bg">🎹</div><div class="portfolio-overlay"></div><div class="portfolio-info"><div class="portfolio-genre">Film Score</div><div class="portfolio-title">Rainbow — Background Score</div></div></div>
    <div class="portfolio-item pi-5"><div class="item-bg">♬</div><div class="portfolio-overlay"></div><div class="portfolio-info"><div class="portfolio-genre">Devotional</div><div class="portfolio-title">Murugan Bhajan Collection</div></div></div>
  </div>
</section>

<!-- PROCESS -->
<section id="process">
  <div class="process-header">
    <span class="section-tag">✦ How We Work</span>
    <h2 class="section-title">The <span class="gold">Creative Journey</span></h2>
  </div>
  <div class="process-steps">
    <div class="step"><div class="step-num">I</div><h4>Consultation</h4><p>We understand your vision and finalize the concept together</p></div>
    <div class="step"><div class="step-num">II</div><h4>Composition</h4><p>Melody and lyrics crafted, a sample track is prepared</p></div>
    <div class="step"><div class="step-num">III</div><h4>Recording</h4><p>Vocals and instruments recorded in our professional studio</p></div>
    <div class="step"><div class="step-num">IV</div><h4>Production</h4><p>Arrangement, mixing & mastering bring the track to life</p></div>
    <div class="step"><div class="step-num">V</div><h4>Delivery</h4><p>Your final track delivered in your preferred format</p></div>
  </div>
</section>

<!-- TESTIMONIALS -->
<section class="testimonials">
  <div class="testimonials-header">
    <span class="section-tag">✦ Client Stories</span>
    <h2 class="section-title">What They <span class="gold">Say</span></h2>
  </div>
  <div class="testimonials-grid">
    <div class="testimonial"><div class="stars">★★★★★</div><p>"We had our wedding song composed by Kaarigai Isai — it was a truly magical experience. The team's dedication and quality of work is unmatched."</p><div class="testi-author"><div class="testi-avatar">M</div><div><div class="testi-name">Manimegalai</div><div class="testi-role">Wedding Client, Coimbatore</div></div></div></div>
    <div class="testimonial"><div class="stars">★★★★★</div><p>"I came in needing a background score for my short film and walked away with a masterpiece. I recommend Kaarigai Isai to every director I know."</p><div class="testi-author"><div class="testi-avatar">K</div><div><div class="testi-name">Karthik Raj</div><div class="testi-role">Film Director, Chennai</div></div></div></div>
    <div class="testimonial"><div class="stars">★★★★★</div><p>"Their ability to blend traditional folk music with modern sound is truly unique. My album's success owes a great deal to this talented team."</p><div class="testi-author"><div class="testi-avatar">V</div><div><div class="testi-name">Valarmathi</div><div class="testi-role">Folk Singer, Madurai</div></div></div></div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-wrap">
    <div>
      <span class="section-tag">✦ Get In Touch</span>
      <h2 class="section-title">Let's Create Your <span class="gold">Musical Vision</span></h2>
      <p class="section-subtitle">Book a session today and let your music journey begin with us.</p>
      <br><br>
      <div class="contact-info-block"><h4>📍 Location</h4><p>Coimbatore, Tamil Nadu — 641001</p></div>
      <div class="contact-info-block"><h4>📞 Phone</h4><p>+91 98765 43210</p></div>
      <div class="contact-info-block"><h4>✉️ Email</h4><p>studio@kaarigaiisai.com</p></div>
      <div class="contact-info-block"><h4>⏰ Studio Hours</h4><p>Monday – Saturday: 9 AM – 9 PM</p></div>
    </div>
    <div>
      <div class="contact-form">
        <div class="form-row">
          <div class="form-field"><label>Your Name</label><input type="text" placeholder="Full Name"></div>
          <div class="form-field"><label>Phone Number</label><input type="tel" placeholder="+91 XXXXX XXXXX"></div>
        </div>
        <div class="form-field"><label>Email Address</label><input type="email" placeholder="you@example.com"></div>
        <div class="form-field"><label>Service Type</label>
          <select>
            <option>Music Composition</option>
            <option>Vocal Recording</option>
            <option>Beat Production</option>
            <option>Film Score / BGM</option>
            <option>Music Arrangement</option>
            <option>Live Performance</option>
            <option>Other</option>
          </select>
        </div>
        <div class="form-field"><label>Tell Us About Your Project</label><textarea placeholder="Describe your project, timeline, and any specific requirements..."></textarea></div>
        <button class="submit-btn" onclick="alert('✅ Message sent! We will contact you within 24 hours.')">Book Your Session →</button>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-top">
    <div class="footer-brand">
      <div class="logo">Kaarigai Isai</div>
      <div class="tagline">Tamil Music Creator Studio</div>
      <p>Bringing the heritage of Tamil music to the modern world — every note tells a story worth hearing.</p>
    </div>
    <div class="footer-col">
      <h5>Quick Links</h5>
      <ul>
        <li><a href="#about">About Us</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#portfolio">Portfolio</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h5>Services</h5>
      <ul>
        <li><a href="#">Composition</a></li>
        <li><a href="#">Recording Studio</a></li>
        <li><a href="#">Film BGM</a></li>
        <li><a href="#">Live Events</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <p>© 2025 Kaarigai Isai. All rights reserved. | Made with ♥ in Coimbatore</p>
    <div class="social-links">
      <a href="#" title="YouTube">▶</a>
      <a href="#" title="Instagram">◈</a>
      <a href="#" title="Facebook">ƒ</a>
      <a href="#" title="Spotify">♫</a>
    </div>
  </div>
</footer>

</body>
</html>
