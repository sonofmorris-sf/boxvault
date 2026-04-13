# BoxVault — Deploying to GitHub Pages

A single-file storage inventory app. Scanning a printed QR label with iPhone Camera opens the app directly to that box's record.

## Deploy in 5 minutes

1. **Create a new GitHub repository.** Go to github.com → New repository. Name it something like `boxvault`. Make it **Public** (required for free GitHub Pages).

2. **Upload `index.html`.** On the new repo page, click "uploading an existing file" and upload the `index.html` file. Commit it to the `main` branch.

3. **Enable GitHub Pages.** In the repo, go to **Settings → Pages**. Under "Build and deployment", set:
   - **Source:** Deploy from a branch
   - **Branch:** `main` / `(root)`
   Click **Save**.

4. **Wait ~1 minute.** GitHub will show a URL like `https://YOUR-USERNAME.github.io/boxvault/`. That's your app.

5. **Open the URL on your iPhone.** Add it to your Home Screen (Share → Add to Home Screen) for an app-like icon.

## How the QR deep link works

Each QR code encodes a URL like `https://YOUR-USERNAME.github.io/boxvault/?id=A-001`. When you scan it:

- iPhone Camera recognizes it as a URL and shows a yellow link banner
- Tap it → Safari opens the app and jumps straight to that box's record

## Where your data lives

- Box records are stored in **your browser's localStorage** — on your device only
- Nothing is sent to GitHub, Anthropic, or any server
- The only network call is the one-time fetch of the QR library from Cloudflare's CDN (cached thereafter)
- Use the **Backup** tab to export JSON or CSV copies to iCloud Drive periodically

## Updating the app

Replace `index.html` in the repo. GitHub Pages redeploys automatically within a minute or two.

## Using on a desktop

Just open the same URL. Note that localStorage is per-browser per-device — data on your phone does not sync to your laptop automatically. Use Export JSON on one device and Import JSON on the other to move data between them.
