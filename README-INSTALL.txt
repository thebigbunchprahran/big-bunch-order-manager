# The Big Bunch Order Manager — Mobile App

This package turns the latest Order Manager into an installable Progressive Web App (PWA) for iPhone and Android.

## Files
- `index.html` — latest order manager, including per-order stock quantity and Buy more checkbox
- `manifest.webmanifest` — app name, display mode and install icons
- `service-worker.js` — app-shell caching for quicker loading and basic offline shell access
- `icon-192.png`, `icon-512.png`, `icon-512-maskable.png` — app icons

## Important
A PWA must be hosted on an HTTPS website (or localhost for testing). It cannot be installed by opening the HTML file directly from Downloads or Google Drive.

The service worker caches the app shell. Firebase synchronisation, sign-in, and other online services still require an internet connection. Existing app data is not automatically transferred between devices; configure the same Firebase project in the app on each device to synchronise.

## Publish it using GitHub Pages (free hosting)
1. On a computer, sign in to GitHub and create a new repository, for example `big-bunch-order-manager`.
2. Upload **all files in this folder** to the repository's root. Make sure `index.html`, `manifest.webmanifest`, `service-worker.js`, and all three PNG icons are at the same level.
3. In the repository, open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then Save.
5. Wait for GitHub Pages to publish the site. It will provide an HTTPS address similar to `https://YOUR-USERNAME.github.io/big-bunch-order-manager/`.
6. Open that HTTPS address on a phone.

## Install on iPhone
1. Open the HTTPS app link in **Safari**.
2. Tap **Share** (square with arrow).
3. Choose **Add to Home Screen**.
4. Confirm **Add**. Open The Big Bunch from the new home-screen icon.

## Install on Android
1. Open the HTTPS app link in **Chrome**.
2. Tap **Install app** if shown, or use **⋮ → Add to Home screen → Install**.
3. Open The Big Bunch from the new home-screen icon.

## Firebase
If you already have Firebase Web configuration, open the app's Firebase/cloud settings and enter the same API key, database URL, project ID and auth domain on each device. Confirm Firebase Authentication and Realtime Database rules are configured before staff use it.

## Updating the app later
Replace `index.html` in the GitHub repository with the newer version. When releasing a significant update, increment `CACHE_NAME` in `service-worker.js` (for example, `big-bunch-order-manager-v2`) so devices refresh their cached app shell.
