# Restorix CMS

A free, open-source (GNU GPL v3) **single-file PHP CMS** built for restored and archived websites. Drop one file next to your static HTML, open it in a browser, set a password — and edit your whole site visually. No database to create: content lives in a built-in SQLite file the CMS manages by itself.

**[Restorix CMS — free single-file CMS for restored websites](https://restorix.io/en/restorix-cms)** (product page with full feature list and FAQ)

## What is Restorix CMS?

Restorix CMS is exactly one file — `webarchive-cms.php` — that turns a folder of static HTML into an editable website:

- **Visual editing** — click into any page and change text and images in your browser
- **Site-wide search & replace** — fix an old phone number or email across every page in one pass
- **File manager and automatic backups** with one-click rollback
- **No database setup** — built-in SQLite; you never touch phpMyAdmin or a config file
- **Safe mode on by default** — learning the panel cannot break your site
- **Runs anywhere PHP runs** — PHP 5.6 through 8.x, any cPanel, Plesk, or budget shared host

## What is Restorix?

Restorix CMS is made by the team behind **[Restorix — restore and download websites from the Wayback Machine](https://restorix.io)**, a service that pulls lost or deleted websites out of the web archive and hands them back to you as clean, ready-to-host files with exact upfront pricing. Every Restorix restore zip already includes this CMS, and one-click deploys install it automatically.

## Requirements

- PHP **5.6 or newer** (5.6 → 8.x all work) with the standard `pdo_sqlite` extension
- Any web server (Apache, nginx + PHP-FPM, LiteSpeed, …)
- No MySQL, no Composer, no Node — nothing else

## Install / deploy

### Method 1 — With a Restorix restore zip (easiest)

If you downloaded a restored website from Restorix, the CMS is already inside the zip.

1. Upload the zip to your hosting and extract it into your web root (`public_html` on cPanel, `httpdocs` on Plesk), so `webarchive-cms.php` sits next to `index.html`.
2. Visit `https://your-domain.com/webarchive-cms.php`.
3. The first launch asks you to **create your admin password** — that's the entire setup.
4. The CMS imports your pages automatically. Start editing.

The full walkthrough with diagrams: **[how to put a restored website back online](https://restorix.io/en/restore-website-from-zip)** (Cloudflare Pages, cPanel/Plesk, CMS, and WordPress paths).

### Method 2 — Manual upload to cPanel / Plesk / any panel

1. Download `webarchive-cms.php` from this repository.
2. Open your panel's **File Manager**, go to the web root (`public_html` / `httpdocs`), and upload the file next to your site's `index.html`. FTP works just as well (FileZilla → drag the file in).
3. Visit `https://your-domain.com/webarchive-cms.php` and set your admin password.

### Method 3 — VPS / own server

```bash
# copy the single file into your site's document root, e.g.:
scp webarchive-cms.php user@your-server:/var/www/your-site/
```

Make sure PHP is enabled for the site (nginx users: route `*.php` to PHP-FPM). Then open `https://your-domain.com/webarchive-cms.php`.

### A note on Cloudflare Pages (and Netlify/Vercel/GitHub Pages)

Those are **static-only** hosts — PHP never executes there, so the CMS cannot run on them. Host the static site there without the CMS file, or put the site on any PHP hosting if you want in-browser editing. The CMS runs fine behind Cloudflare's DNS/CDN proxy on a normal host.

## Good to know

- **Rename-friendly:** you can rename `webarchive-cms.php` to anything (e.g. `admin-panel.php`); the CMS detects the new name and reminds you to bookmark it.
- **Security:** after the first visit, the admin is protected by your password with login rate-limiting; safe mode (default) blocks custom PHP files. You can also restrict access by IP in the settings.
- **Unlimited sites:** GPL v3 means you can install it for every client and every project, and modify it as needed.

## License

GNU General Public License v3 — see [LICENSE](LICENSE). © Restorix.
