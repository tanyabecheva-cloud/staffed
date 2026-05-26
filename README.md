# Khaya 🏠

**Trust, brought home.** — South Africa's vetted home & care workforce platform.

> `khaya` = "home" (isiZulu/isiXhosa). Nannies, domestic workers, gardeners, elderly care,
> drivers, maintenance, pets — every person background-checked, ID-verified, reference-called.

## What's in this repo
| File | What it is |
|---|---|
| `index.html` | **LIVE site** — the fun consumer-marketplace version (Poppins, coral/mint, flat icons). Single file, no build step. |
| `index-premium.html` | Alternative "premium/trust" version (Fraunces serif, teal/clay) — kept for reference. |
| `BRAND.md` | Brand guide — name, colours, type, voice, logo. |
| `MARKETING.md` | Go-to-market strategy. |
| `README.md` | This file — what it is + how to deploy free. |

## Phases (the "app")
- **Phase 1 — NOW (this repo):** marketing site + waitlist on free GitHub Pages.
  Capture employer + worker signups, validate demand, seed worker supply.
- **Phase 2 — the real marketplace:** worker profiles, matching, ratings, in-app messaging,
  auto BCEA contracts, vetting workflow. Stack: **Next.js + Vercel + Supabase (DB/auth)**.
  WhatsApp-first worker intake. Build only after the waitlist proves demand.

## Deploy free on GitHub Pages (10 min)
Run these from this folder (`/Users/tanyabecheva/themba`). Replace `YOUR_GH_USERNAME`.

```bash
git init
git add .
git commit -m "Khaya — initial site"
git branch -M main
# Create an empty repo named "khaya" on github.com first, then:
git remote add origin https://github.com/YOUR_GH_USERNAME/khaya.git
git push -u origin main
```

Then on GitHub: **Settings → Pages → Source: Deploy from a branch → `main` / `(root)` → Save.**
Live in ~1 min at: `https://YOUR_GH_USERNAME.github.io/khaya/`

### Custom domain (khaya.co.za / getkhaya.com)
1. Buy the domain (domains.co.za for `.co.za` ~R75/yr; Porkbun/Namecheap for `.com`).
2. GitHub → Settings → Pages → **Custom domain** → enter your domain → Save.
3. At your registrar add a `CNAME` record pointing to `YOUR_GH_USERNAME.github.io`
   (or 4 A-records to GitHub's IPs for an apex domain — GitHub shows them).
4. Tick **Enforce HTTPS**.

## Connect the forms (so signups actually arrive)
The Find Talent / Find Work forms are currently front-end only. Wire them to
**Web3Forms** (free): create a key at web3forms.com, then set each `<form>` to
`action="https://api.web3forms.com/submit"` with a hidden
`<input type="hidden" name="access_key" value="YOUR_KEY">`. Submissions email you — no backend needed.
