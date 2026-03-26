# GrowthOS — Installation Guide

**GrowthOS** is a Progressive Web App (PWA). It runs entirely in your browser and can be installed on your Android home screen like a native app — no App Store needed.

---

## 📦 OPTION A — Deploy to GitHub Pages (Free Hosting)

### Step 1 — Create a GitHub Account
1. Go to [github.com](https://github.com)
2. Click **Sign up** and create a free account
3. Verify your email address

### Step 2 — Create a New Repository
1. Click the **+** icon in the top right corner
2. Select **New repository**
3. Name it exactly: `growthos`
4. Set visibility to **Public** (required for free GitHub Pages)
5. Do **NOT** check "Add a README file"
6. Click **Create repository**

### Step 3 — Push the Code
Open your terminal (Mac/Linux) or Git Bash (Windows) and run:

```bash
cd /path/to/this/folder   # navigate to the growthos folder

git init
git add .
git commit -m "Initial commit: GrowthOS PWA"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/growthos.git
git push -u origin main
```

> ⚠️ Replace `YOUR_USERNAME` with your actual GitHub username

### Step 4 — Enable GitHub Pages
1. Go to your repository on GitHub
2. Click **Settings** (tab near the top)
3. Scroll down to **Pages** in the left sidebar
4. Under **Source**, select **GitHub Actions**
5. Click **Save**

### Step 5 — Trigger the Deployment
The GitHub Actions workflow (`.github/workflows/deploy.yml`) runs automatically when you push to `main`.

To check the deployment:
1. Click the **Actions** tab in your repository
2. You should see "Deploy GrowthOS to GitHub Pages" running
3. Wait for the green checkmark ✅ (usually 1–2 minutes)

### Step 6 — Your App is Live!
After deployment, your app is available at:
```
https://YOUR_USERNAME.github.io/growthos
```

Visit this URL in Chrome on your phone to install it!

---

## 📱 OPTION B — Install on Android from GitHub Pages

### Prerequisites
- Android phone with Chrome browser
- Your app deployed (see Option A above)
- Internet connection for first load

### Step 1 — Open Chrome on Android
Open the **Chrome** browser app on your Android phone (not Samsung Internet or Firefox).

### Step 2 — Navigate to Your App
Type your app URL in Chrome's address bar:
```
https://YOUR_USERNAME.github.io/growthos
```
Wait for the page to **fully load** (all content visible).

### Step 3 — Open Chrome Menu
Tap the **three-dot menu** (⋮) in the top-right corner of Chrome.

### Step 4 — Add to Home Screen
Look for one of these options in the menu:
- **"Add to Home screen"** — tap it
- **"Install app"** — tap it (newer Chrome versions)

> 💡 If you see a banner at the bottom of the screen saying "Add GrowthOS to Home screen" — tap that instead!

### Step 5 — Confirm Installation
A popup will appear asking you to confirm. Tap **"Install"** or **"Add"**.

### Step 6 — Find Your App
The **GrowthOS** icon (indigo square with "G") will appear on your home screen.

### Step 7 — Launch GrowthOS
Tap the icon. GrowthOS opens **full screen** like a native app — no browser chrome, no address bar.

> 🎉 The first time you open the app, complete the onboarding to set up your habits!

---

## 🔌 Offline Usage

GrowthOS works **fully offline** after the first load.

- First open: requires internet (downloads all app files)
- After that: works with no internet connection
- All your data is stored locally on your device

---

## 🔧 Troubleshooting

### "Install button not showing"
- Clear Chrome's cache: Settings → Privacy → Clear browsing data
- Reload the page and wait 5 seconds
- Make sure you're using Chrome (not another browser)
- Try visiting the URL twice and waiting for full load

### "App not working offline"
- Open the app once while on WiFi
- Wait for the page to fully load (watch for loading indicators)
- Then close Chrome and open the home screen icon

### "Icon looks blurry or low quality"
- This is a GitHub Pages CDN caching issue
- Wait 24 hours and the icon will update
- Or force-refresh: hold the icon → App info → Clear cache

### "Data disappeared after update"
- GrowthOS stores all data in localStorage on your device
- Data persists across app updates
- Use Settings → Export Data to back up regularly

### "Can't push to GitHub"
Make sure Git is installed:
```bash
# macOS
brew install git

# Ubuntu/Debian
sudo apt install git

# Windows: Download from git-scm.com
```

Configure your identity:
```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

---

## 💡 Pro Tips

1. **Back up your data**: Go to Settings → Export Data weekly
2. **Day navigation**: Tap ‹ › arrows to review past days
3. **Swipe to delete**: On the Expenses tab, swipe an expense left to delete it
4. **Habit notes**: Tap any weekly bar on a habit to see notes for that day
5. **Tomorrow's focus**: Set priorities the night before from the Dashboard

---

## 📊 Technical Details

- **Type**: Progressive Web App (PWA)
- **Hosting**: GitHub Pages (static files)
- **Storage**: Browser localStorage (local only, no cloud sync)
- **Offline**: Service Worker with cache-first strategy
- **Data limit**: ~5MB of habit/expense data (localStorage limit)
- **Browser support**: Chrome 80+, Edge 80+, Safari 14+

---

*Built with ♥ — GrowthOS v1.0.0*
