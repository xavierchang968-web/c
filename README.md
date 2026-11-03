# 🔔 Bell Schedule

A tiny, private **school bell-schedule app for your iPhone** — no App Store, no Mac, no account, no server. You add it to your Home Screen and it shows your current class, a live countdown to the next bell, and reminds you before each period.

Everything runs **on your phone**. Nothing is uploaded anywhere.

---

## What it does

- **Now screen** — your current class, a ring + countdown to the next bell, and today's periods at a glance.
- **Schedule screen** — add/edit your periods (name, start bell, end, and which days).
- **Reminders before each bell** — two ways:
  1. **📅 Add alerts to Calendar (.ics)** — the reliable one. Buzzes you *N* minutes before every bell, **even when the app is closed.**
  2. **🔔 In-app alerts** — a nudge while the app is open (handy, but iOS can't fire these when the app is shut — that's what the calendar option is for).
- Works **offline** after the first load.

---

## 📲 Put it on your iPhone (no Mac needed)

You need the app to live at a web address first. The easiest free way is **GitHub Pages** (steps below). Once it's live:

1. Open the app's link in **Safari** on your iPhone.
2. Tap the **Share** button (the square with an arrow).
3. Scroll down and tap **Add to Home Screen** → **Add**.
4. You now have a **Bells** icon. Open it — it runs full-screen like a real app.

Then, inside the app: go to **Schedule**, add your periods (or tap *Load a typical day* and edit it), pick how many minutes' warning you want, and tap **📅 Add alerts to Calendar** → choose **Add All** when your phone opens the file. Done — your phone will now remind you before every bell.

> Why the calendar step? Apple doesn't let a Home-Screen web app fire timed alerts while it's closed. The calendar file hands those reminders to iOS itself, which is rock-solid and works offline.

---

## 🚀 Make it live with GitHub Pages (free)

This repo auto-deploys via GitHub Actions. One-time setup:

1. Push this repo to GitHub (already done if you're reading this there).
2. On GitHub: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
3. Open the **Actions** tab and let the "Deploy to Pages" workflow finish.
4. Your app is now at **`https://<your-username>.github.io/<repo>/`** — open that in Safari and add it to your Home Screen (above).

Any time you push a change, it redeploys automatically.

### Prefer no GitHub Pages?
It's a plain static site — any static host works (Netlify drop, Cloudflare Pages, etc.), or just open `index.html` locally on a computer to try it. (Home-Screen install needs an `https://` address, which Pages gives you for free.)

---

## Files

| File | What it is |
|------|------------|
| `index.html` | The whole app (UI + logic, self-contained). |
| `manifest.webmanifest` | Makes it installable as a Home-Screen app. |
| `sw.js` | Service worker — offline caching. |
| `icons/` | App icons (the bell). |
| `.github/workflows/pages.yml` | Auto-deploy to GitHub Pages. |

## Privacy

Your schedule is stored only in your phone's browser storage (`localStorage`). There's no backend, no analytics, no network calls. The optional calendar reminders live in your own Calendar app. Back up or move your schedule anytime with **Export / Import** on the Schedule screen.
