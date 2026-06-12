<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ZIMS Security — Protection You Can Trust</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --charcoal: #0D0F12;
    --navy: #0E1E30;
    --steel: #1A3A5C;
    --cyan: #00B4D8;
    --cyan-dim: #0096B7;
    --light: #F0F4F8;
    --muted: #8A99A8;
    --card-bg: #131820;
    --border: rgba(0,180,216,0.18);
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Inter', sans-serif;
    background: var(--charcoal);
    color: var(--light);
    overflow-x: hidden;
  }

  /* ── TOP BAR ── */
  .topbar {
    background: var(--navy);
    border-bottom: 1px solid var(--border);
    padding: 8px 40px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 12px;
    color: var(--muted);
    letter-spacing: 0.04em;
  }
  .topbar a { color: var(--muted); text-decoration: none; transition: color .2s; }
  .topbar a:hover { color: var(--cyan); }
  .topbar-contact { display: flex; gap: 28px; }
  .topbar-contact span { display: flex; align-items: center; gap: 6px; }
  .topbar-contact svg { color: var(--cyan); flex-shrink: 0; }
  .topbar-social { display: flex; gap: 14px; }
  .topbar-social a {
    width: 26px; height: 26px; border-radius: 4px;
    background: rgba(0,180,216,0.1);
    border: 1px solid var(--border);
    display: flex; align-items: center; justify-content: center;
    transition: background .2s, border-color .2s;
  }
  .topbar-social a:hover { background: var(--cyan); border-color: var(--cyan); }
  .topbar-social a:hover svg { color: #fff; }
  .topbar-social svg { color: var(--muted); transition: color .2s; }

  /* ── NAV ── */
  nav {
    position: sticky; top: 0; z-index: 100;
    background: rgba(13,15,18,0.95);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
    padding: 0 40px;
    display: flex; justify-content: space-between; align-items: center;
    height: 68px;
  }
  .logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 32px;
    letter-spacing: 0.12em;
    color: var(--light);
    text-decoration: none;
  }
  .logo span { color: var(--cyan); }
  .nav-links { display: flex; gap: 6px; list-style: none; }
  .nav-links a {
    font-size: 13px; font-weight: 500; letter-spacing: 0.08em;
    text-transform: uppercase; color: var(--muted);
    text-decoration: none; padding: 8px 14px; border-radius: 4px;
    transition: color .2s, background .2s;
    position: relative;
  }
  .nav-links a:hover, .nav-links a.active { color: var(--light); background: rgba(0,180,216,0.08); }
  .nav-links a.active::after {
    content: ''; position: absolute; bottom: -1px; left: 14px; right: 14px;
    height: 2px; background: var(--cyan); border-radius: 2px;
  }
  .nav-cta {
    background: var(--cyan); color: #fff !important;
    padding: 8px 18px !important; border-radius: 4px !important;
    font-weight: 600 !important;
  }
  .nav-cta:hover { background: var(--cyan-dim) !important; color: #fff !important; }

  /* ── HERO ── */
  .hero {
    position: relative; min-height: 92vh;
    display: flex; align-items: center;
    overflow: hidden;
    background: var(--charcoal);
  }
  .hero-grid {
    position: absolute; inset: 0;
    background-image:
      linear-gradient(rgba(0,180,216,0.05) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,180,216,0.05) 1px, transparent 1px);
    background-size: 60px 60px;
    animation: gridPulse 8s ease-in-out infinite;
  }
  @keyframes gridPulse {
    0%, 100% { opacity: 0.6; }
    50% { opacity: 1; }
  }
  .hero-slash {
    position: absolute; right: 0; top: 0; bottom: 0; width: 52%;
    background: linear-gradient(135deg, transparent 0%, transparent 38%, var(--navy) 38%);
    pointer-events: none;
  }
  .hero-slash-inner {
    position: absolute; right: 0; top: 0; bottom: 0; width: 46%;
    background: linear-gradient(135deg, transparent 0%, transparent 45%, rgba(0,180,216,0.06) 45%);
  }
  .scanline {
    position: absolute; inset: 0;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 3px,
      rgba(0,0,0,0.08) 3px,
      rgba(0,0,0,0.08) 4px
    );
    pointer-events: none;
  }
  .hero-content {
    position: relative; z-index: 2;
    padding: 0 40px; max-width: 720px;
  }
  .hero-eyebrow {
    display: inline-flex; align-items: center; gap: 10px;
    font-size: 11px; font-weight: 600; letter-spacing: 0.2em;
    text-transform: uppercase; color: var(--cyan);
    margin-bottom: 24px;
  }
  .hero-eyebrow::before {
    content: ''; width: 28px; height: 2px; background: var(--cyan);
  }
  .hero h1 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(64px, 9vw, 120px);
    line-height: 0.92;
    letter-spacing: 0.04em;
    color: var(--light);
    margin-bottom: 28px;
  }
  .hero h1 em {
    font-style: normal; color: var(--cyan);
    display: block;
  }
  .hero-sub {
    font-size: 16px; line-height: 1.7; color: var(--muted);
    max-width: 480px; margin-bottom: 40px;
  }
  .hero-actions { display: flex; gap: 14px; flex-wrap: wrap; }
  .btn-primary {
    background: var(--cyan); color: #fff;
    padding: 14px 32px; border-radius: 4px;
    font-size: 13px; font-weight: 700; letter-spacing: 0.1em;
    text-transform: uppercase; text-decoration: none;
    border: none; cursor: pointer;
    transition: background .2s, transform .15s;
    display: inline-block;
  }
  .btn-primary:hover { background: var(--cyan-dim); transform: translateY(-1px); }
  .btn-outline {
    background: transparent; color: var(--light);
    padding: 13px 30px; border-radius: 4px;
    font-size: 13px; font-weight: 600; letter-spacing: 0.1em;
    text-transform: uppercase; text-decoration: none;
    border: 1px solid rgba(255,255,255,0.25);
    transition: border-color .2s, color .2s;
    display: inline-block;
  }
  .btn-outline:hover { border-color: var(--cyan); color: var(--cyan); }
  .hero-badge {
    position: absolute; right: 60px; top: 50%;
    transform: translateY(-50%) rotate(-2deg);
    z-index: 2;
    display: flex; flex-direction: column; align-items: center;
    gap: 4px;
  }
  .badge-ring {
    width: 160px; height: 160px; border-radius: 50%;
    border: 2px solid var(--border);
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    background: rgba(14,30,48,0.8);
    backdrop-filter: blur(8px);
    text-align: center;
    animation: rotateBadge 30s linear infinite;
    position: relative;
  }
  .badge-ring::before {
    content: '';
    position: absolute; inset: 6px; border-radius: 50%;
    border: 1px solid rgba(0,180,216,0.3);
    animation: rotateBadge 20s linear infinite reverse;
  }
  @keyframes rotateBadge {
    from { box-shadow: 0 0 0 0 rgba(0,180,216,0); }
    50% { box-shadow: 0 0 40px 4px rgba(0,180,216,0.15); }
    to { box-shadow: 0 0 0 0 rgba(0,180,216,0); }
  }
  .badge-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 52px; line-height: 1; color: var(--cyan);
  }
  .badge-label {
    font-size: 10px; font-weight: 600; letter-spacing: 0.12em;
    text-transform: uppercase; color: var(--muted);
    padding: 0 20px; text-align: center;
  }

  /* ── STATS BAR ── */
  .stats-bar {
    background: var(--navy);
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    padding: 0 40px;
    display: flex;
    overflow: hidden;
  }
  .stat {
    flex: 1; display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    padding: 28px 20px;
    border-right: 1px solid var(--border);
    transition: background .2s;
  }
  .stat:last-child { border-right: none; }
  .stat:hover { background: rgba(0,180,216,0.04); }
  .stat-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 48px; line-height: 1; color: var(--cyan);
    letter-spacing: 0.04em;
  }
  .stat-label {
    font-size: 11px; font-weight: 500; letter-spacing: 0.14em;
    text-transform: uppercase; color: var(--muted); margin-top: 4px;
  }

  /* ── SECTION SHARED ── */
  section { padding: 100px 40px; }
  .section-eyebrow {
    display: inline-flex; align-items: center; gap: 10px;
    font-size: 11px; font-weight: 600; letter-spacing: 0.2em;
    text-transform: uppercase; color: var(--cyan);
    margin-bottom: 16px;
  }
  .section-eyebrow::before { content: ''; width: 24px; height: 2px; background: var(--cyan); }
  h2.section-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(40px, 5vw, 64px);
    line-height: 1; letter-spacing: 0.04em;
    color: var(--light); margin-bottom: 20px;
  }
  .section-desc {
    font-size: 16px; line-height: 1.75; color: var(--muted);
    max-width: 560px;
  }

  /* ── SERVICES ── */
  .services-bg { background: var(--charcoal); }
  .services-header { display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: 56px; flex-wrap: wrap; gap: 24px; }
  .services-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 8px;
    overflow: hidden;
  }
  .service-card {
    background: var(--card-bg);
    padding: 40px 32px;
    position: relative;
    overflow: hidden;
    transition: background .3s;
    text-decoration: none;
    display: block;
    cursor: pointer;
  }
  .service-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0; height: 3px;
    background: var(--cyan);
    transform: scaleX(0); transform-origin: left;
    transition: transform .35s ease;
  }
  .service-card:hover { background: #181e28; }
  .service-card:hover::before { transform: scaleX(1); }
  .service-card:hover .service-icon { color: var(--cyan); }
  .service-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 64px; line-height: 1;
    color: rgba(0,180,216,0.08);
    position: absolute; top: 24px; right: 28px;
    letter-spacing: 0.04em;
    transition: color .3s;
  }
  .service-card:hover .service-num { color: rgba(0,180,216,0.14); }
  .service-icon { color: var(--steel); margin-bottom: 20px; transition: color .3s; }
  .service-icon svg { width: 36px; height: 36px; }
  .service-card h3 {
    font-size: 16px; font-weight: 700; letter-spacing: 0.04em;
    color: var(--light); margin-bottom: 12px; line-height: 1.3;
  }
  .service-card p { font-size: 14px; line-height: 1.6; color: var(--muted); }
  .service-arrow {
    display: inline-flex; align-items: center; gap: 6px;
    font-size: 12px; font-weight: 600; letter-spacing: 0.1em;
    text-transform: uppercase; color: var(--cyan);
    margin-top: 20px; opacity: 0;
    transform: translateX(-6px);
    transition: opacity .25s, transform .25s;
  }
  .service-card:hover .service-arrow { opacity: 1; transform: translateX(0); }

  /* ── ABOUT ── */
  .about-section { background: var(--navy); }
  .about-inner { display: grid; grid-template-columns: 1fr 1fr; gap: 80px; align-items: center; max-width: 1200px; margin: 0 auto; }
  .about-visual { position: relative; }
  .about-img-wrap {
    aspect-ratio: 4/3; background: var(--steel);
    border-radius: 6px; overflow: hidden;
    border: 1px solid var(--border);
    position: relative;
  }
  .about-img-wrap::after {
    content: '';
    position: absolute; inset: 0;
    background: linear-gradient(135deg, transparent 60%, rgba(0,180,216,0.15));
  }
  .about-img-placeholder {
    width: 100%; height: 100%;
    display: flex; align-items: center; justify-content: center;
    background: linear-gradient(135deg, #0E1E30 0%, #1A3A5C 100%);
  }
  .about-img-placeholder svg { width: 80px; height: 80px; color: rgba(0,180,216,0.3); }
  .about-accent {
    position: absolute; bottom: -20px; right: -20px;
    width: 140px; height: 140px;
    background: var(--charcoal);
    border: 1px solid var(--border);
    border-radius: 6px;
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    text-align: center; padding: 16px;
  }
  .about-accent-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 44px; color: var(--cyan); line-height: 1;
  }
  .about-accent-label { font-size: 10px; font-weight: 600; letter-spacing: 0.12em; text-transform: uppercase; color: var(--muted); margin-top: 4px; }
  .about-qualities { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-top: 40px; }
  .quality-item {
    display: flex; align-items: flex-start; gap: 12px;
    padding: 16px; border: 1px solid var(--border);
    border-radius: 6px; background: rgba(0,0,0,0.2);
    transition: border-color .2s, background .2s;
  }
  .quality-item:hover { border-color: var(--cyan); background: rgba(0,180,216,0.04); }
  .quality-dot { width: 8px; height: 8px; border-radius: 50%; background: var(--cyan); margin-top: 5px; flex-shrink: 0; }
  .quality-text h4 { font-size: 13px; font-weight: 700; color: var(--light); margin-bottom: 4px; }
  .quality-text p { font-size: 12px; color: var(--muted); line-height: 1.5; }

  /* ── PHILOSOPHY ── */
  .philosophy-section { background: var(--charcoal); }
  .philosophy-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 24px; margin-top: 56px; }
  .pillar-card {
    padding: 32px 24px;
    border: 1px solid var(--border);
    border-radius: 6px;
    background: var(--card-bg);
    position: relative; overflow: hidden;
    transition: border-color .3s, transform .3s;
  }
  .pillar-card::after {
    content: '';
    position: absolute; bottom: 0; left: 0; right: 0; height: 3px;
    background: linear-gradient(90deg, var(--cyan), transparent);
    transform: scaleX(0); transform-origin: left;
    transition: transform .4s;
  }
  .pillar-card:hover { border-color: rgba(0,180,216,0.4); transform: translateY(-3px); }
  .pillar-card:hover::after { transform: scaleX(1); }
  .pillar-icon { margin-bottom: 20px; color: var(--cyan); }
  .pillar-icon svg { width: 28px; height: 28px; }
  .pillar-card h3 { font-size: 15px; font-weight: 700; color: var(--light); margin-bottom: 10px; }
  .pillar-card p { font-size: 13px; line-height: 1.65; color: var(--muted); }

  /* ── CTA BAND ── */
  .cta-band {
    background: var(--steel);
    padding: 60px 40px;
    position: relative; overflow: hidden;
  }
  .cta-band::before {
    content: '';
    position: absolute; inset: 0;
    background: linear-gradient(135deg, var(--navy) 0%, transparent 60%);
  }
  .cta-band-inner {
    position: relative; z-index: 1;
    display: flex; align-items: center; justify-content: space-between;
    gap: 40px; flex-wrap: wrap; max-width: 1200px; margin: 0 auto;
  }
  .cta-band h2 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 48px; letter-spacing: 0.04em;
    color: var(--light); line-height: 1;
  }
  .cta-phone { display: flex; align-items: center; gap: 12px; }
  .cta-phone-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 36px; color: var(--cyan); letter-spacing: 0.06em;
  }

  /* ── CONTACT ── */
  .contact-section { background: var(--navy); }
  .contact-inner { display: grid; grid-template-columns: 1fr 1fr; gap: 80px; max-width: 1200px; margin: 0 auto; }
  .contact-cards { display: flex; flex-direction: column; gap: 16px; margin-top: 40px; }
  .contact-card {
    display: flex; align-items: flex-start; gap: 16px;
    padding: 20px 24px;
    border: 1px solid var(--border);
    border-radius: 6px; background: var(--card-bg);
    transition: border-color .2s;
  }
  .contact-card:hover { border-color: rgba(0,180,216,0.4); }
  .contact-card-icon {
    width: 40px; height: 40px; flex-shrink: 0;
    border-radius: 6px; background: rgba(0,180,216,0.1);
    border: 1px solid var(--border);
    display: flex; align-items: center; justify-content: center;
    color: var(--cyan);
  }
  .contact-card-icon svg { width: 18px; height: 18px; }
  .contact-card-label { font-size: 10px; font-weight: 600; letter-spacing: 0.14em; text-transform: uppercase; color: var(--muted); margin-bottom: 4px; }
  .contact-card-value { font-size: 14px; font-weight: 500; color: var(--light); }
  .contact-form { display: flex; flex-direction: column; gap: 16px; margin-top: 40px; }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  .field { display: flex; flex-direction: column; gap: 6px; }
  .field label { font-size: 11px; font-weight: 600; letter-spacing: 0.1em; text-transform: uppercase; color: var(--muted); }
  .field input, .field textarea, .field select {
    background: var(--card-bg);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 12px 14px;
    font-size: 14px; color: var(--light);
    font-family: 'Inter', sans-serif;
    outline: none;
    transition: border-color .2s;
  }
  .field input:focus, .field textarea:focus, .field select:focus { border-color: var(--cyan); }
  .field textarea { resize: vertical; min-height: 110px; }
  .field select option { background: var(--card-bg); }
  .field input::placeholder, .field textarea::placeholder { color: rgba(138,153,168,0.5); }

  /* ── FOOTER ── */
  footer {
    background: var(--charcoal);
    border-top: 1px solid var(--border);
    padding: 60px 40px 32px;
  }
  .footer-inner { display: grid; grid-template-columns: 2fr 1fr 1fr 1fr; gap: 48px; max-width: 1200px; margin: 0 auto; }
  .footer-brand p { font-size: 13px; line-height: 1.7; color: var(--muted); margin-top: 16px; max-width: 260px; }
  .footer-social { display: flex; gap: 10px; margin-top: 20px; }
  .footer-social a {
    width: 32px; height: 32px; border-radius: 4px;
    background: rgba(0,180,216,0.08);
    border: 1px solid var(--border);
    display: flex; align-items: center; justify-content: center;
    color: var(--muted); text-decoration: none;
    transition: background .2s, color .2s, border-color .2s;
  }
  .footer-social a:hover { background: var(--cyan); border-color: var(--cyan); color: #fff; }
  .footer-social svg { width: 14px; height: 14px; }
  .footer-col h4 { font-size: 11px; font-weight: 700; letter-spacing: 0.16em; text-transform: uppercase; color: var(--light); margin-bottom: 20px; }
  .footer-col ul { list-style: none; display: flex; flex-direction: column; gap: 10px; }
  .footer-col a { font-size: 13px; color: var(--muted); text-decoration: none; transition: color .2s; }
  .footer-col a:hover { color: var(--cyan); }
  .footer-bottom {
    max-width: 1200px; margin: 48px auto 0;
    padding-top: 24px; border-top: 1px solid var(--border);
    display: flex; justify-content: space-between; align-items: center;
    font-size: 12px; color: var(--muted);
    flex-wrap: wrap; gap: 12px;
  }
  .footer-bottom a { color: var(--cyan); text-decoration: none; }

  /* ── RESPONSIVE ── */
  @media (max-width: 1024px) {
    .services-grid { grid-template-columns: repeat(2, 1fr); }
    .philosophy-grid { grid-template-columns: repeat(2, 1fr); }
    .hero-badge { display: none; }
    .about-inner, .contact-inner { grid-template-columns: 1fr; gap: 48px; }
    .footer-inner { grid-template-columns: 1fr 1fr; }
  }
  @media (max-width: 768px) {
    section { padding: 64px 24px; }
    nav, .topbar { padding-left: 24px; padding-right: 24px; }
    .nav-links { display: none; }
    .services-grid { grid-template-columns: 1fr; }
    .philosophy-grid { grid-template-columns: 1fr 1fr; }
    .stats-bar { flex-wrap: wrap; }
    .stat { min-width: 50%; }
    .hero { min-height: 80vh; }
    .hero-content { padding: 40px 24px; }
    .form-row { grid-template-columns: 1fr; }
    .footer-inner { grid-template-columns: 1fr; gap: 32px; }
    footer { padding: 48px 24px 28px; }
    .about-accent { display: none; }
    .cta-band-inner { flex-direction: column; text-align: center; }
    .topbar-contact { flex-direction: column; gap: 4px; }
  }
  @media (max-width: 480px) {
    .philosophy-grid { grid-template-columns: 1fr; }
    .about-qualities { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<!-- TOP BAR -->
<div class="topbar">
  <div class="topbar-contact">
    <span>
      <svg width="13" height="13" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/></svg>
      <a href="mailto:info@zims.com.pk">info@zims.com.pk</a>
    </span>
    <span>
      <svg width="13" height="13" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/></svg>
      <a href="tel:111-111-946">111-111-946</a>
    </span>
    <span>
      <svg width="13" height="13" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/></svg>
      SMCHS, Karachi
    </span>
  </div>
  <div class="topbar-social">
    <a href="https://www.facebook.com/zimsofficial/" target="_blank" title="Facebook">
      <svg width="12" height="12" fill="currentColor" viewBox="0 0 24 24"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>
    </a>
    <a href="https://www.linkedin.com/company/zimssecurity/" target="_blank" title="LinkedIn">
      <svg width="12" height="12" fill="currentColor" viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
    </a>
    <a href="https://www.instagram.com/zims1security/" target="_blank" title="Instagram">
      <svg width="12" height="12" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
    </a>
  </div>
</div>

<!-- NAV -->
<nav>
  <a class="logo" href="#"><span>ZIMS</span> Security</a>
  <ul class="nav-links">
    <li><a href="#" class="active">Home</a></li>
    <li><a href="#about">About Us</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#philosophy">Philosophy</a></li>
    <li><a href="#contact" class="nav-cta">Contact Us</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-grid"></div>
  <div class="hero-slash"></div>
  <div class="hero-slash-inner"></div>
  <div class="scanline"></div>
  <div class="hero-content">
    <div class="hero-eyebrow">Licensed Security Provider — Pakistan</div>
    <h1>Protection<br>You Can<br><em>Trust.</em></h1>
    <p class="hero-sub">ZIMS delivers elite security services across Karachi and beyond — from executive protection to full-site surveillance — built on discipline, technology, and unwavering professionalism.</p>
    <div class="hero-actions">
      <a href="#services" class="btn-primary">Explore Services</a>
      <a href="#contact" class="btn-outline">Request a Quote</a>
    </div>
  </div>
  <div class="hero-badge">
    <div class="badge-ring">
      <div class="badge-num">10+</div>
      <div class="badge-label">Years Protecting Karachi</div>
    </div>
  </div>
</section>

<!-- STATS BAR -->
<div class="stats-bar">
  <div class="stat">
    <div class="stat-num">500+</div>
    <div class="stat-label">Clients Served</div>
  </div>
  <div class="stat">
    <div class="stat-num">24/7</div>
    <div class="stat-label">CCTV Monitoring</div>
  </div>
  <div class="stat">
    <div class="stat-num">6</div>
    <div class="stat-label">Core Services</div>
  </div>
  <div class="stat">
    <div class="stat-num">10+</div>
    <div class="stat-label">Years Experience</div>
  </div>
  <div class="stat">
    <div class="stat-num">100%</div>
    <div class="stat-label">Certified Personnel</div>
  </div>
</div>

<!-- SERVICES -->
<section class="services-bg" id="services">
  <div class="services-header">
    <div>
      <div class="section-eyebrow">What We Offer</div>
      <h2 class="section-title">Our Security<br>Services</h2>
    </div>
    <a href="#contact" class="btn-outline">Request a Service</a>
  </div>
  <div class="services-grid">

    <a class="service-card" href="#">
      <div class="service-num">01</div>
      <div class="service-icon">
        <svg fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0z"/></svg>
      </div>
      <h3>Events Security</h3>
      <p>Professional crowd control, access management, and threat assessment for corporate events, concerts, and private gatherings of all scales.</p>
      <div class="service-arrow">Learn More →</div>
    </a>

    <a class="service-card" href="#">
      <div class="service-num">02</div>
      <div class="service-icon">
        <svg fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4"/></svg>
      </div>
      <h3>On-Site Security</h3>
      <p>Trained guards and supervisors for commercial properties, factories, banks, hospitals, and residential communities — round the clock.</p>
      <div class="service-arrow">Learn More →</div>
    </a>

    <a class="service-card" href="#">
      <div class="service-num">03</div>
      <div class="service-icon">
        <svg fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"/></svg>
      </div>
      <h3>Executive Close Protection</h3>
      <p>Discrete, highly trained protection officers for executives, VIPs, and high-profile individuals — threat assessment included.</p>
      <div class="service-arrow">Learn More →</div>
    </a>

    <a class="service-card" href="#">
      <div class="service-num">04</div>
      <div class="service-icon">
        <svg fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M8 7h12m0 0l-4-4m4 4l-4 4m0 6H4m0 0l4 4m-4-4l4-4"/></svg>
      </div>
      <h3>Bullet-Proof Vehicles</h3>
      <p>Provision and logistics of armored transport vehicles for secure movement of personnel and assets across high-risk environments.</p>
      <div class="service-arrow">Learn More →</div>
    </a>

    <a class="service-card" href="#">
      <div class="service-num">05</div>
      <div class="service-icon">
        <svg fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"/></svg>
      </div>
      <h3>Intruder Alarm Systems</h3>
      <p>End-to-end design, installation, and monitoring of advanced intrusion detection systems tailored to your property's vulnerabilities.</p>
      <div class="service-arrow">Learn More →</div>
    </a>

    <a class="service-card" href="#">
      <div class="service-num">06</div>
      <div class="service-icon">
        <svg fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M15 10l4.553-2.069A1 1 0 0121 8.87v6.26a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z"/></svg>
      </div>
      <h3>CCTV Solutions</h3>
      <p>State-of-the-art surveillance camera systems with remote monitoring, AI analytics, and 24/7 ZIMS control room support.</p>
      <div class="service-arrow">Learn More →</div>
    </a>

  </div>
</section>

<!-- ABOUT -->
<section class="about-section" id="about">
  <div class="about-inner">
    <div class="about-visual">
      <div class="about-img-wrap">
        <div class="about-img-placeholder">
          <svg fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1"><path stroke-linecap="round" stroke-linejoin="round" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"/></svg>
        </div>
      </div>
      <div class="about-accent">
        <div class="about-accent-num">10+</div>
        <div class="about-accent-label">Years of Excellence</div>
      </div>
    </div>
    <div class="about-text">
      <div class="section-eyebrow">Who We Are</div>
      <h2 class="section-title">About ZIMS<br>Security</h2>
      <p class="section-desc">ZIMS prioritizes the utmost comfort and security of its clients. We combine exceptionally skilled personnel with cutting-edge technology and rigorous ethical standards — ensuring every client receives service that surpasses their expectations.</p>
      <div class="about-qualities">
        <div class="quality-item">
          <div class="quality-dot"></div>
          <div class="quality-text">
            <h4>Skilled Personnel</h4>
            <p>Rigorously trained and certified security professionals.</p>
          </div>
        </div>
        <div class="quality-item">
          <div class="quality-dot"></div>
          <div class="quality-text">
            <h4>Advanced Technology</h4>
            <p>Cutting-edge tools and methodology at every layer.</p>
          </div>
        </div>
        <div class="quality-item">
          <div class="quality-dot"></div>
          <div class="quality-text">
            <h4>Client-First Service</h4>
            <p>Responsive support and customized security plans.</p>
          </div>
        </div>
        <div class="quality-item">
          <div class="quality-dot"></div>
          <div class="quality-text">
            <h4>Ethical Standards</h4>
            <p>Strict codes of conduct in every engagement.</p>
          </div>
        </div>
      </div>
      <div style="margin-top: 36px;">
        <a href="#contact" class="btn-primary">Learn More About Us</a>
      </div>
    </div>
  </div>
</section>

<!-- PHILOSOPHY -->
<section class="philosophy-section" id="philosophy">
  <div style="max-width: 800px;">
    <div class="section-eyebrow">Our Core Values</div>
    <h2 class="section-title">How We Operate</h2>
    <p class="section-desc">Our philosophy centers on providing top-notch security services and equipping our personnel with the skills, resources, and support to execute flawlessly — every time.</p>
  </div>
  <div class="philosophy-grid">
    <div class="pillar-card">
      <div class="pillar-icon">
        <svg fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"/></svg>
      </div>
      <h3>Customer-Focused</h3>
      <p>Every security plan is built around our client's unique environment, risk profile, and operational requirements — not a template.</p>
    </div>
    <div class="pillar-card">
      <div class="pillar-icon">
        <svg fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"/></svg>
      </div>
      <h3>Resilient</h3>
      <p>We train our teams for high-pressure scenarios, adapting rapidly to threats and maintaining operational continuity under any condition.</p>
    </div>
    <div class="pillar-card">
      <div class="pillar-icon">
        <svg fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M13 10V3L4 14h7v7l9-11h-7z"/></svg>
      </div>
      <h3>Efficient</h3>
      <p>ZIMS is mission-driven — maximizing protective output with minimal footprint, always operating with precision and purpose.</p>
    </div>
    <div class="pillar-card">
      <div class="pillar-icon">
        <svg fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M11.049 2.927c.3-.921 1.603-.921 1.902 0l1.519 4.674a1 1 0 00.95.69h4.915c.969 0 1.371 1.24.588 1.81l-3.976 2.888a1 1 0 00-.363 1.118l1.518 4.674c.3.922-.755 1.688-1.538 1.118l-3.976-2.888a1 1 0 00-1.176 0l-3.976 2.888c-.783.57-1.838-.197-1.538-1.118l1.518-4.674a1 1 0 00-.363-1.118l-3.976-2.888c-.784-.57-.38-1.81.588-1.81h4.914a1 1 0 00.951-.69l1.519-4.674z"/></svg>
      </div>
      <h3>Effective</h3>
      <p>Results speak louder than promises. Our track record across hundreds of clients reflects a consistent standard of protection excellence.</p>
    </div>
  </div>
</section>

<!-- CTA BAND -->
<div class="cta-band">
  <div class="cta-band-inner">
    <div>
      <h2>Ready to Secure<br>Your Assets?</h2>
      <p style="color: var(--muted); margin-top: 8px; font-size: 14px;">Our team is ready to assess your requirements and propose a tailored security plan.</p>
    </div>
    <div class="cta-phone">
      <svg width="32" height="32" fill="none" viewBox="0 0 24 24" stroke="var(--cyan)" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/></svg>
      <div>
        <div style="font-size:11px;letter-spacing:0.14em;text-transform:uppercase;color:var(--muted);font-weight:600;">Call Now</div>
        <div class="cta-phone-num">111-111-946</div>
      </div>
    </div>
    <a href="#contact" class="btn-primary">Get a Free Assessment</a>
  </div>
</div>

<!-- CONTACT -->
<section class="contact-section" id="contact">
  <div class="contact-inner">
    <div>
      <div class="section-eyebrow">Get In Touch</div>
      <h2 class="section-title">Contact<br>ZIMS</h2>
      <p class="section-desc">Our experienced team will respond within 24 hours and provide you with a customized security solution.</p>
      <div class="contact-cards">
        <div class="contact-card">
          <div class="contact-card-icon">
            <svg fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/><path stroke-linecap="round" stroke-linejoin="round" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/></svg>
          </div>
          <div>
            <div class="contact-card-label">Office Address</div>
            <div class="contact-card-value">Amber Palace, Suite No 3, Mezzanine Floor, Block B, Shahrah-e-Faisal, SMCHS, Karachi</div>
          </div>
        </div>
        <div class="contact-card">
          <div class="contact-card-icon">
            <svg fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/></svg>
          </div>
          <div>
            <div class="contact-card-label">Phone</div>
            <div class="contact-card-value">111-111-946</div>
          </div>
        </div>
        <div class="contact-card">
          <div class="contact-card-icon">
            <svg fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/></svg>
          </div>
          <div>
            <div class="contact-card-label">Email</div>
            <div class="contact-card-value">info@zims.com.pk</div>
          </div>
        </div>
        <div class="contact-card">
          <div class="contact-card-icon">
            <svg fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
          </div>
          <div>
            <div class="contact-card-label">Open Hours</div>
            <div class="contact-card-value">Monday – Saturday: 9:00 AM – 7:00 PM</div>
          </div>
        </div>
      </div>
    </div>
    <div>
      <div style="height: 40px;"></div>
      <h3 style="font-size:15px;font-weight:700;color:var(--light);margin-bottom:8px;">Send Us a Message</h3>
      <p style="font-size:13px;color:var(--muted);margin-bottom:24px;">Fill out the form and a ZIMS specialist will be in touch shortly.</p>
      <div class="contact-form">
        <div class="form-row">
          <div class="field">
            <label>Full Name</label>
            <input type="text" placeholder="Ahmad Khan">
          </div>
          <div class="field">
            <label>Phone Number</label>
            <input type="tel" placeholder="+92 300 0000000">
          </div>
        </div>
        <div class="field">
          <label>Email Address</label>
          <input type="email" placeholder="you@company.com">
        </div>
        <div class="field">
          <label>Service Required</label>
          <select>
            <option value="">Select a service…</option>
            <option>Events Security</option>
            <option>On-Site Security</option>
            <option>Executive Close Protection</option>
            <option>Bullet-Proof Vehicles</option>
            <option>Intruder Alarm System</option>
            <option>CCTV Solutions</option>
            <option>General Inquiry</option>
          </select>
        </div>
        <div class="field">
          <label>Message</label>
          <textarea placeholder="Briefly describe your security requirements…"></textarea>
        </div>
        <button class="btn-primary" style="width:100%;padding:16px;font-size:14px;">Send Message</button>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-inner">
    <div class="footer-brand">
      <div class="logo" style="font-size:28px;"><span>ZIMS</span> Security</div>
      <p>Protecting businesses, executives, and properties across Pakistan with integrity, expertise, and round-the-clock vigilance.</p>
      <div class="footer-social">
        <a href="https://www.facebook.com/zimsofficial/" target="_blank">
          <svg fill="currentColor" viewBox="0 0 24 24"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>
        </a>
        <a href="https://www.linkedin.com/company/zimssecurity/" target="_blank">
          <svg fill="currentColor" viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        </a>
        <a href="https://www.instagram.com/zims1security/" target="_blank">
          <svg fill="currentColor" viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
        </a>
      </div>
    </div>
    <div class="footer-col">
      <h4>Navigation</h4>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#about">About Us</a></li>
        <li><a href="#services">Our Services</a></li>
        <li><a href="#philosophy">Philosophy</a></li>
        <li><a href="#contact">Contact Us</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Services</h4>
      <ul>
        <li><a href="#">Events Security</a></li>
        <li><a href="#">On-Site Security</a></li>
        <li><a href="#">Close Protection</a></li>
        <li><a href="#">Armored Vehicles</a></li>
        <li><a href="#">Intruder Alarms</a></li>
        <li><a href="#">CCTV Solutions</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Contact</h4>
      <ul>
        <li><a href="tel:111-111-946">111-111-946</a></li>
        <li><a href="mailto:info@zims.com.pk">info@zims.com.pk</a></li>
        <li style="color:var(--muted);font-size:13px;line-height:1.6;">Amber Palace, Suite 3, Block B, SMCHS, Karachi</li>
        <li style="color:var(--muted);font-size:13px;">Mon–Sat: 9AM – 7PM</li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <div>© 2025 ZIMS Security. All rights reserved.</div>
    <div>Licensed Security Provider — Karachi, Pakistan</div>
  </div>
</footer>

<script>
  // Smooth active nav on scroll
  const sections = document.querySelectorAll('section[id], div.cta-band');
  const navLinks = document.querySelectorAll('.nav-links a');
  const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        navLinks.forEach(link => {
          link.classList.remove('active');
          if (link.getAttribute('href') === '#' + entry.target.id) link.classList.add('active');
        });
      }
    });
  }, { threshold: 0.4 });
  sections.forEach(s => observer.observe(s));

  // Subtle card entrance
  const cards = document.querySelectorAll('.service-card, .pillar-card, .contact-card, .quality-item');
  const cardObserver = new IntersectionObserver(entries => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        entry.target.style.opacity = '1';
        entry.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.1 });
  cards.forEach((card, i) => {
    card.style.opacity = '0';
    card.style.transform = 'translateY(18px)';
    card.style.transition = `opacity 0.4s ease ${i * 0.06}s, transform 0.4s ease ${i * 0.06}s, background 0.3s, border-color 0.2s`;
    cardObserver.observe(card);
  });
</script>
</body>
</html>
