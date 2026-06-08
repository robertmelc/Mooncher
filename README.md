# 🌙 Mooncher

> **B2B Voucher Platform** — Sell vouchers. Grow faster.

Landing page for [mooncher.com](https://mooncher.com) — a B2B SaaS platform that lets any business create, sell and manage digital vouchers in minutes.

---

## 🚀 Stack

| Layer | Technology |
|-------|-----------|
| Hosting | GitHub Pages |
| Domain | GoDaddy → mooncher.com |
| Fonts | Bricolage Grotesque + DM Sans (Google Fonts) |
| Payments (planned) | Stripe |
| Analytics (planned) | Plausible / GA4 |

---

## 📁 Structure

```
mooncher/
├── index.html      # Main landing page (EN/CZ toggle)
├── CNAME           # Custom domain config for GitHub Pages
└── README.md       # This file
```

---

## 🌐 GitHub Pages Deploy

### 1. Create the repository

```bash
# Option A — GitHub CLI
gh repo create mooncher --public --source=. --push

# Option B — manual
# Go to github.com/new → name: mooncher → Public → Create
```

### 2. Push files

```bash
git init
git add .
git commit -m "🌙 Initial launch — Mooncher landing page"
git branch -M main
git remote add origin https://github.com/robertmelc/mooncher.git
git push -u origin main
```

### 3. Enable GitHub Pages

```
GitHub repo → Settings → Pages
Source: Deploy from a branch
Branch: main / (root)
→ Save
```

Live at: `https://robertmelc.github.io/mooncher` within ~2 minutes.

---

## 🌍 Custom Domain — GoDaddy DNS

Log in to GoDaddy → Domains → mooncher.com → DNS Management.

### A Records (delete existing A records first)

| Type | Name | Value | TTL |
|------|------|-------|-----|
| A | @ | 185.199.108.153 | 600 |
| A | @ | 185.199.109.153 | 600 |
| A | @ | 185.199.110.153 | 600 |
| A | @ | 185.199.111.153 | 600 |

### CNAME Record

| Type | Name | Value | TTL |
|------|------|-------|-----|
| CNAME | www | robertmelc.github.io | 600 |

> ⏱ DNS propagation takes 10–60 minutes. Full global propagation up to 24h.

### HTTPS (free via GitHub Pages)

```
GitHub repo → Settings → Pages → Custom domain → mooncher.com → Save
☑ Enforce HTTPS  ← enable after DNS propagates
```

---

## ✏️ Content Updates

All content is in `index.html`. Key sections:

| Section | Search for |
|---------|-----------|
| Hero headline | `class="line1"` / `class="line2"` |
| Hero subtext | `class="hero-sub"` |
| Pricing amounts | `class="price-amount"` |
| Team bios | `class="team-bio"` |
| FAQ answers | `class="faq-a"` |
| Contact email | `hello@mooncher.com` |

EN/CZ translations: every element has `data-en="..."` and `data-cz="..."` attributes.

---

## 📬 Waitlist Form

Currently the form shows a success message on submit. To connect a real backend:

**Option A — Mailchimp**
Replace `handleSubmit()` in the script with a Mailchimp embedded form POST.

**Option B — Resend + Supabase**
POST to a Supabase Edge Function that stores the email and sends a confirmation via Resend.

---

## 🏢 Operator

**ROOMS MANAGEMENT s.r.o.**
Operated by Robert & Patricie Rosenbergová
Legal advisor: Mgr. Jiří Oplt — GOLDEN BLOT Nadační fond

---

*© 2025 Mooncher · ROOMS MANAGEMENT s.r.o.*
