# Publishing The Last Alibi

## Before you upload
Open `privacy.html` and replace `YOUR-EMAIL@example.com` (two places) with a real contact email.
Google Play requires a working contact address.

## Step 1: Put it online (free)
Upload the WHOLE folder (keep the `icons` folder next to `index.html`).

Easiest, Netlify Drop:
1. Go to https://app.netlify.com/drop and sign in.
2. Drag this whole folder onto the page.
3. You get a link like `https://something.netlify.app`. Rename it under Site settings.

Google's own option, Firebase Hosting (needs Node.js):
    npm install -g firebase-tools
    firebase login
    firebase init hosting      (public directory: .   single-page app: No)
    firebase deploy

## Step 2: Get it on Google Search
1. Go to https://search.google.com/search-console and add your site link (URL-prefix option).
2. Verify ownership (the HTML-file method works: download their file into this folder and upload again).
3. Use "URL inspection" with your link, then "Request indexing". Listing can take a few days.

## Step 3 (optional): Google Play Store
1. Go to https://www.pwabuilder.com, paste your site link, choose Package for stores > Android.
2. Download the package. Keep the signing key file it gives you safe: you need it for every update.
3. Upload `assetlinks.json` from the package to a folder called `.well-known` on your site,
   so the app opens without a browser address bar.
4. Create a Google Play Console developer account (one-time fee).
5. New app > upload the .aab file. Fill in: privacy policy link (`yoursite/privacy.html`),
   content rating questionnaire, Data safety form (answer: no data collected or shared),
   icon (`icons/icon-512.png`), feature graphic 1024x500, and at least 2 phone screenshots.
6. New personal accounts: run a Closed test with at least 12 testers opted in for 14 days in a row,
   then apply for production access.

## Note about the AI
On your own website the suspect runs in the game's built-in offline mode (scripted answers).
The live Claude-powered suspect only works when the game is opened inside Claude.
