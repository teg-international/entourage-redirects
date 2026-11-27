# entourage-redirects

A tiny Netlify site that redirects the **bare domains** (without `www`) of all Entourage websites
to their `www` address, with HTTPS, keeping the full path and query string.

Why: the websites run on Cloudflare Pages, which can only serve a bare domain if the DNS moves to Cloudflare.
The DNS of the Entourage domains stays with LegalMatters, so the bare domain points here instead.

## Add a website
1. Add two lines to `public/_redirects` (copy the tonilocopizza block) and push to GitHub.
2. Netlify → site `entourage-redirects` → Domain management → **Add domain alias** → `example.com`.
3. Ask LegalMatters to set: **A `@` → `75.2.60.5`** (and `www` CNAME → `<project>.pages.dev` for the site itself).
   Never touch MX / SPF / autodiscover / other email records.
4. Netlify issues the HTTPS certificate automatically once the DNS points here.

## Websites
| Bare domain | Redirects to |
|---|---|
| tonilocopizza.com | https://www.tonilocopizza.com |
