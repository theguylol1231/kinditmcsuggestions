# Kinds Crystal Optimizer Questions — Setup Guide

This project is a static website with Netlify Forms.

## Files in this project

- `index.html` — main poll page (Yes/No vote + mod recommendation typing box)
- `dashboard.html` — questions dashboard + extra mod recommendation form
- `thank-you.html` — confirmation page after submit
- `netlify.toml` — Netlify publish settings + redirects

## 1) Run locally

From the project folder:

```bash
python3 -m http.server 4173
```

Open:

- `http://localhost:4173/`
- `http://localhost:4173/dashboard.html`

> Note: Local Python server does **not** process Netlify redirects/forms. Redirects like `/dashboard` work after deploying to Netlify.

## 2) Deploy on Netlify (no CLI needed)

1. Go to https://app.netlify.com/
2. Click **Add new site** → **Deploy manually**
3. Drag-and-drop this project folder (or a zip of these files)
4. Wait for deploy to finish
5. Open your generated URL (example: `https://your-site-name.netlify.app`)

## 3) Enable forms (first-time Netlify form detection)

Netlify Forms are detected at build/deploy time because forms contain:

- `data-netlify="true"`
- `name="..."`
- hidden input `name="form-name"`

After deployment:

1. In Netlify dashboard, open your site
2. Go to **Forms**
3. You should see forms:
   - `crystal-optimizer-poll`
   - `mod-recommendations`

## 4) Change your `.netlify.app` subdomain name

1. Open your site in Netlify
2. Go to **Site configuration** → **Domain management**
3. Choose **Options** next to the Netlify subdomain
4. Click **Edit site name**
5. Save your preferred name

Your URLs then become:

- `https://<your-site-name>.netlify.app/`
- `https://<your-site-name>.netlify.app/dashboard`

## 5) Optional: custom domain

1. **Site configuration** → **Domain management** → **Add custom domain**
2. Follow DNS steps Netlify provides
3. Wait for DNS/SSL to provision

## 6) Redeploy after edits

If you edit HTML files:

- Re-upload via **Deploy manually**, or
- Connect a Git repository in Netlify and push commits for automatic deploys.
