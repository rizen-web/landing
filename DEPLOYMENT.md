# Rizen Landing Page Deployment

## 1. Prepare The Site

The landing page is a static site:

- `index.html`
- `styles.css`
- `assets/hero-dashboard.svg`

You can deploy this folder directly to Vercel.

## 2. Put The Site On GitHub

1. Create a new GitHub repository, for example `rizen-landing`.
2. Upload the contents of this `landing-page` folder.
3. Make sure `index.html` is in the repository root if you upload only this folder.

## 3. Connect Vercel

1. Go to Vercel.
2. Click `Add New` > `Project`.
3. Import the GitHub repository.
4. Framework preset: `Other`.
5. Build command: leave empty.
6. Output directory: leave empty.
7. Deploy.

Vercel will give you a temporary domain like `rizen-landing.vercel.app`.

## 4. Point Namecheap To Cloudflare

1. Add your domain to Cloudflare.
2. Cloudflare will give you two nameservers.
3. In Namecheap, open your domain.
4. Go to `Nameservers`.
5. Choose `Custom DNS`.
6. Paste the two Cloudflare nameservers.
7. Save.

Nameserver changes can take a few minutes to 24 hours.

## 5. Connect Domain In Vercel

1. Open your Vercel project.
2. Go to `Settings` > `Domains`.
3. Add your domain, for example `rizen.sr` or `yourdomain.com`.
4. Add both:
   - `yourdomain.com`
   - `www.yourdomain.com`

## 6. Add DNS Records In Cloudflare

Use the exact values Vercel shows in the Domains screen. Usually:

| Type  | Name | Value |
| ----- | ---- | ----- |
| A     | `@`  | `76.76.21.21` |
| CNAME | `www` | `cname.vercel-dns.com` |

Set Cloudflare proxy to DNS only while connecting the domain. After Vercel verifies SSL, you can keep it DNS only or enable proxy if everything works.

## 7. SSL Settings

In Cloudflare:

1. Go to `SSL/TLS`.
2. Set mode to `Full`.
3. Turn on `Always Use HTTPS`.

In Vercel, wait until the domain shows valid SSL.

## 8. Final Check

Open:

- `https://yourdomain.com`
- `https://www.yourdomain.com`

Check:

- Page loads on mobile and desktop.
- WhatsApp buttons open your chat.
- The floating WhatsApp button stays visible.
- Vercel domain redirects correctly if you choose a primary domain.
