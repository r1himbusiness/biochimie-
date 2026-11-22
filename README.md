# Photo Gallery – Pay-to-Unlock Demo (AR / EN / FR)

Static demo site (HTML + CSS + JS, no backend) with pay-per-bundle unlocking.
Payment is **fake**: it always ends in "card declined" and nothing is ever charged.

## Files
- `index.html` — the whole site (no build step needed)
- `images/` — the photo files referenced by the bundles

## Run locally
Just open `index.html` in a browser, or serve the folder with any static server:

```bash
npx serve .
```

## Deploy on GitHub Pages
1. Push this folder to a GitHub repo.
2. In the repo settings, enable **GitHub Pages** on the `main` branch (root).
3. Your site will be live at `https://<user>.github.io/<repo>/`.

## Editing content
Open `index.html` and edit the `GROUPS` array near the top of the `<script>` block:

```js
{id:"g1", imgs:["file1.png","file2.jpg"],
 t:{ar:"العنوان بالعربية", en:"Title in English", fr:"Titre en français"},
 n:{ar:"وصف قصير", en:"Short description", fr:"Description courte"}}
```

Put the matching image files in `images/`. Price is `50 × number of images` per
bundle by default — change the `price()` function to adjust.

## Language
The site ships in Arabic, English and French (switch buttons at the top).
Translations live in the `I18N` object in `index.html`.

## ⚠️ Important
This payment form is a **non-functional demo for UI/learning purposes only**.
It must never be connected to a real payment processor as-is, and must never
be deployed in a way that could lead a visitor to believe their real card
details are being processed (it isn't — nothing is sent anywhere).
