# Vcard-Hoff
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Đoàn Trần Hùng – Lukas Hoff</title>
<meta name="description" content="Giảng Viên & Chuyên Viên Tư Vấn Du Học CHLB Đức – Khoa Tiếng Đức, Trường Trung Cấp Bách Khoa Hải Phòng">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --ink: #1a1a1a;
    --paper: #f5f0e8;
    --accent: #8b1a1a;
    --muted: #6b6458;
    --rule: #d4c9b0;
    --gold: #b8922a;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--paper);
    color: var(--ink);
    font-family: 'DM Sans', sans-serif;
    font-weight: 300;
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 2rem 1rem;
  }

  /* subtle paper texture via repeating lines */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 27px,
      rgba(180,160,120,0.08) 28px
    );
    pointer-events: none;
    z-index: 0;
  }

  .card {
    position: relative;
    z-index: 1;
    max-width: 420px;
    width: 100%;
    background: #fdfaf4;
    border: 1px solid var(--rule);
    padding: 3rem 2.5rem 2.5rem;
    animation: rise 0.7s ease both;
  }

  @keyframes rise {
    from { opacity: 0; transform: translateY(18px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* corner ornaments */
  .card::before, .card::after {
    content: '';
    position: absolute;
    width: 18px; height: 18px;
    border-color: var(--gold);
    border-style: solid;
  }
  .card::before { top: 10px; left: 10px; border-width: 1px 0 0 1px; }
  .card::after  { bottom: 10px; right: 10px; border-width: 0 1px 1px 0; }

  .corner-br, .corner-tl {
    position: absolute;
    width: 18px; height: 18px;
    border-color: var(--gold);
    border-style: solid;
  }
  .corner-tl { top: 10px; right: 10px; border-width: 1px 1px 0 0; }
  .corner-br { bottom: 10px; left: 10px; border-width: 0 0 1px 1px; }

  .flag-stripe {
    position: absolute;
    top: 0; left: 2.5rem; right: 2.5rem;
    height: 3px;
    display: flex;
  }
  .flag-stripe span {
    flex: 1;
  }
  .flag-stripe span:nth-child(1) { background: #1a1a1a; }
  .flag-stripe span:nth-child(2) { background: var(--accent); }
  .flag-stripe span:nth-child(3) { background: var(--gold); }

  .name-block {
    margin-bottom: 1.5rem;
    padding-bottom: 1.25rem;
    border-bottom: 0.5px solid var(--rule);
    animation: rise 0.7s 0.1s ease both;
  }

  .name-vi {
    font-family: 'Playfair Display', serif;
    font-size: 1.55rem;
    font-weight: 600;
    letter-spacing: -0.01em;
    line-height: 1.15;
    color: var(--ink);
  }

  .name-de {
    font-family: 'DM Sans', sans-serif;
    font-size: 0.85rem;
    font-weight: 400;
    color: var(--muted);
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-top: 4px;
  }

  .role-block {
    margin-bottom: 1.75rem;
    animation: rise 0.7s 0.18s ease both;
  }

  .role-title {
    font-family: 'Playfair Display', serif;
    font-size: 0.95rem;
    font-weight: 400;
    color: var(--accent);
    font-style: italic;
    margin-bottom: 4px;
  }

  .role-org {
    font-size: 0.8rem;
    color: var(--muted);
    line-height: 1.5;
  }

  .divider {
    border: none;
    border-top: 0.5px solid var(--rule);
    margin: 1.25rem 0;
  }

  .contacts {
    display: flex;
    flex-direction: column;
    gap: 0.65rem;
    animation: rise 0.7s 0.26s ease both;
  }

  .contact-row {
    display: flex;
    align-items: flex-start;
    gap: 0.75rem;
    font-size: 0.85rem;
    color: var(--ink);
    text-decoration: none;
  }

  a.contact-row:hover .contact-val { color: var(--accent); }

  .contact-icon {
    width: 16px;
    flex-shrink: 0;
    margin-top: 1px;
    color: var(--gold);
  }

  .contact-val {
    transition: color 0.2s;
    line-height: 1.4;
  }

  .contact-val small {
    display: block;
    font-size: 0.72rem;
    color: var(--muted);
    margin-top: 1px;
  }

  .footer {
    margin-top: 2rem;
    padding-top: 1.25rem;
    border-top: 0.5px solid var(--rule);
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 1rem;
    animation: rise 0.7s 0.34s ease both;
  }

  .footer-text {
    font-size: 0.7rem;
    color: var(--muted);
    line-height: 1.6;
  }

  .de-badge {
    font-size: 0.65rem;
    font-weight: 500;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--muted);
    border: 0.5px solid var(--rule);
    padding: 3px 8px;
    flex-shrink: 0;
  }

  .save-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
    width: 100%;
    margin-top: 1.25rem;
    padding: 0.9rem;
    background: var(--ink);
    color: var(--paper);
    font-family: 'DM Sans', sans-serif;
    font-size: 0.85rem;
    font-weight: 500;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    border: none;
    cursor: pointer;
    text-align: center;
    text-decoration: none;
    transition: background 0.2s;
    animation: rise 0.7s 0.4s ease both;
  }

  .save-btn:hover { background: var(--accent); }

  .save-hint {
    margin-top: 0.6rem;
    font-size: 0.7rem;
    color: var(--muted);
    text-align: center;
    line-height: 1.6;
    animation: rise 0.7s 0.46s ease both;
  }
</style>
</head>
<body>
<article class="card">
  <span class="corner-tl"></span>
  <span class="corner-br"></span>
  <div class="flag-stripe"><span></span><span></span><span></span></div>

  <div class="name-block">
    <h1 class="name-vi">Đoàn Trần Hùng</h1>
    <p class="name-de">Lukas Hoff</p>
  </div>

  <div class="role-block">
    <p class="role-title">Giảng Viên &amp; Chuyên Viên Tư Vấn Du Học</p>
    <p class="role-org">Khoa Tiếng Đức<br>Trường Trung Cấp Bách Khoa Hải Phòng</p>
  </div>

  <div class="contacts">
    <a class="contact-row" href="tel:+84961679869">
      <svg class="contact-icon" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.4">
        <path d="M3 2h3l1.5 3.5L6 7a9 9 0 003 3l1.5-1.5L14 10v3a1 1 0 01-1 1C6 14 2 8.5 2 3a1 1 0 011-1z"/>
      </svg>
      <span class="contact-val">0961 679 869</span>
    </a>

    <a class="contact-row" href="http://lila-deutsch.com" target="_blank" rel="noopener">
      <svg class="contact-icon" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.4">
        <circle cx="8" cy="8" r="6"/>
        <path d="M8 2c0 0-3 2-3 6s3 6 3 6M8 2c0 0 3 2 3 6s-3 6-3 6M2 8h12"/>
      </svg>
      <span class="contact-val">lila-deutsch.com</span>
    </a>

    <div class="contact-row">
      <svg class="contact-icon" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.4">
        <path d="M8 1.5C5.5 1.5 3.5 3.5 3.5 6c0 3.5 4.5 8.5 4.5 8.5S12.5 9.5 12.5 6c0-2.5-2-4.5-4.5-4.5z"/>
        <circle cx="8" cy="6" r="1.5"/>
      </svg>
      <span class="contact-val">2a/251 Phương Lưu 2<small>Đông Hải 1, Hải An, Hải Phòng</small></span>
    </div>
  </div>

  <hr class="divider">

  <div class="footer">
    <p class="footer-text">Tư vấn du học<br>CHLB Đức</p>
    <span class="de-badge">🇩🇪 Deutschland</span>
  </div>

  <a class="save-btn" id="save-btn" href="#" onclick="saveContact(event)">
    <svg width="16" height="16" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5">
      <path d="M8 1v9M5 7l3 3 3-3"/><path d="M2 11v2a1 1 0 001 1h10a1 1 0 001-1v-2"/>
    </svg>
    Lưu vào danh bạ
  </a>
  <p class="save-hint">Nhấn để mở ứng dụng Danh bạ &amp; lưu tự động — iOS và Android đều được</p>
</article>

<script>
function saveContact(e) {
  e.preventDefault();
  var vcard = [
    'BEGIN:VCARD',
    'VERSION:3.0',
    'N:Hùng;Đoàn Trần;;;',
    'FN:Đoàn Trần Hùng (Lukas Hoff)',
    'TITLE:Giảng Viên – Chuyên Viên Tư Vấn Du Học CHLB Đức',
    'ORG:Khoa Tiếng Đức\\, Trường Trung Cấp Bách Khoa Hải Phòng',
    'TEL;TYPE=CELL:+84961679869',
    'URL:http://lila-deutsch.com',
    'ADR;TYPE=WORK:;;2a/251 Phương Lưu 2\\, Đông Hải 1\\, Hải An;Hải Phòng;;;Việt Nam',
    'NOTE:Du học CHLB Đức – Lila Deutsch',
    'END:VCARD'
  ].join('\r\n');

  var blob = new Blob([vcard], { type: 'text/vcard;charset=utf-8' });
  var url = URL.createObjectURL(blob);
  var a = document.createElement('a');
  a.href = url;
  a.download = 'Lukas-Hoff.vcf';
  document.body.appendChild(a);
  a.click();
  setTimeout(function() {
    document.body.removeChild(a);
    URL.revokeObjectURL(url);
  }, 1000);
}
</script>
</body>
</html>
