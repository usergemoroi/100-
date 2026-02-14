# 🛠️ Setup Guide — How to Publish Elite Themes

**Complete step-by-step guide to publish your themes and start making money.**

---

## 📋 Prerequisites

Before publishing, you need:

1. ✅ GitHub account (create at github.com)
2. ✅ VS Code installed
3. ✅ Node.js 18+ installed (download from nodejs.org)
4. ✅ Microsoft account (for Azure DevOps — free)

**Total time:** 30-45 minutes first time, 5 minutes for updates

---

## 🚀 Part 1: Initial Setup (One-Time)

### Step 1: Update Your Information

Edit `package.json` and replace:
- `YOUR_USERNAME` → your GitHub username
- `elite-dev-studio` → your publisher name (choose a unique name)
- Update `repository.url` to your repo URL

Example:
```json
{
  "publisher": "johndoe-themes",
  "repository": {
    "url": "https://github.com/johndoe/elite-themes-2026"
  }
}
```

### Step 2: Create Publisher Account

1. Go to https://marketplace.visualstudio.com/manage
2. Click "Sign in" → use your Microsoft account
3. Click "Create Publisher"
4. Publisher ID: same as in `package.json` (e.g., `johndoe-themes`)
5. Display name: Your display name (e.g., "John's Themes")
6. Click "Create"

**✅ Publisher created!**

### Step 3: Generate Personal Access Token (PAT)

1. Go to https://dev.azure.com
2. Click your profile icon → "Personal access tokens"
3. Click "+ New Token"
4. Name: "Elite Themes Publishing"
5. Organization: "All accessible organizations"
6. Expiration: 1 year (or custom)
7. Scopes: Click "Show all scopes" → check ☑️ **"Marketplace (Publish)"**
8. Click "Create"
9. **IMPORTANT:** Copy the token! You can't see it again!

**Save token somewhere safe (password manager).**

### Step 4: Install Publishing Tool

Open terminal in your project folder:

```bash
# Install vsce (VS Code Extension Manager)
npm install

# Login with your publisher name and token
npx vsce login YOUR_PUBLISHER_NAME
# Paste your Personal Access Token when prompted
```

Example:
```bash
npx vsce login johndoe-themes
# Personal Access Token: [paste token]
# Success: logged in as johndoe-themes
```

**✅ Ready to publish!**

---

## 📦 Part 2: Package & Publish

### Step 1: Test Locally First

```bash
# Package themes into .vsix file (doesn't publish yet)
npx vsce package

# Output: elite-themes-2026-1.0.0.vsix created
```

### Step 2: Test the Package

1. In VS Code: Press `Ctrl + Shift + P`
2. Type: "Install from VSIX"
3. Select `elite-themes-2026-1.0.0.vsix`
4. Test 5-10 themes to make sure they work
5. If issues: fix them and run `npx vsce package` again

### Step 3: Publish to Marketplace

```bash
# Publish to VS Code Marketplace
npx vsce publish

# Output:
# Publishing elite-themes-2026 v1.0.0...
# Success! Published johndoe-themes.elite-themes-2026@1.0.0
# https://marketplace.visualstudio.com/items?itemName=johndoe-themes.elite-themes-2026
```

**🎉 Your themes are now live!**

### Step 4: Verify Publication

1. Go to your marketplace URL (from output above)
2. Check that:
   - ✅ Title looks good
   - ✅ Description is clear
   - ✅ Screenshots show (if you added any)
   - ✅ Install button works

**Wait 5-10 minutes for it to appear in VS Code search.**

---

## 💰 Part 3: Setup Monetization

### Step 1: Enable GitHub Sponsors

1. Go to https://github.com/sponsors
2. Click "Join the waitlist" (if not approved yet)
3. Once approved:
   - Set up payment info (Stripe account)
   - Create sponsor tiers:
     - ☕ $5/mo — Coffee tier
     - 💎 $15/mo — Pro tier
     - 🔥 $50/mo — Founder tier
     - 👑 $100/mo — Elite tier
   - Write tier descriptions (copy from our SPONSORS.md)
4. Enable "Sponsor" button in your repo settings

**Test:** Go to your repo → you should see "Sponsor" button

### Step 2: Setup Patreon (Optional)

1. Go to https://patreon.com
2. Create creator account
3. Set up same tiers as GitHub Sponsors
4. Add link to README.md

### Step 3: Setup Buy Me a Coffee (Optional)

1. Go to https://buymeacoffee.com
2. Create account
3. Enable one-time and monthly donations
4. Add "Custom themes" as extra ($100)
5. Add link to README.md

### Step 4: Update Links in Files

Edit these files and replace `YOUR_USERNAME`:
- `README.md`
- `SPONSORS.md`
- `MARKETING.md`
- `package.json`

Search for:
- `github.com/sponsors/YOUR_USERNAME`
- `patreon.com/YOUR_USERNAME`
- `buymeacoffee.com/YOUR_USERNAME`
- `twitter.com/YOUR_USERNAME`
- `discord.gg/YOUR_SERVER`

---

## 🌐 Part 4: Create Community

### Step 1: Create Discord Server

1. Open Discord → click "+" → "Create My Own"
2. Server name: "Elite Themes Community"
3. Create channels:
   - #welcome
   - #general
   - #support
   - #showcase (users share screenshots)
   - #premium (sponsor-only)
   - #feature-requests
4. Set up roles:
   - @Supporter ($5/mo sponsors)
   - @Pro ($15/mo sponsors)
   - @Founder ($50/mo sponsors)
   - @Elite ($100/mo sponsors)
5. Create invite link (never expires):
   - Right-click server → "Invite People"
   - "Edit Invite Link" → set to "Never Expire"
   - Copy link

**Update `YOUR_SERVER` in all files with your invite code.**

### Step 2: Create Social Media

**Twitter/X:**
1. Create account: @elite_themes (or @yourname_themes)
2. Bio: "100 VS Code themes for devs who earn $10k+/mo | Free + Premium"
3. Link: github.com/YOUR_USERNAME/elite-themes-2026
4. Pin tweet: "Just launched Elite Themes! 🚀"

**Optional: TikTok, Instagram Reels**
- Same handle
- Post theme previews (screen recordings)

---

## 📈 Part 5: Launch Day

### Checklist (Do in Order):

**Morning (9 AM):**
- [ ] Verify themes are live on Marketplace
- [ ] Post launch tweet with screenshots
- [ ] Post in Discord (if you have existing communities)

**Noon (12 PM PST):**
- [ ] Submit to ProductHunt
  - Go to producthunt.com/posts/new
  - Title: "Elite Themes — 100 VS Code themes for $10k+/mo devs"
  - Tagline: "Scientifically designed themes with AI highlighting & integrations"
  - Gallery: Add 5-7 screenshots
  - Launch!
- [ ] Engage with every comment on ProductHunt

**Evening (6 PM):**
- [ ] Post to HackerNews: "Show HN: Elite Themes"
  - URL: your GitHub repo
  - Title: "Show HN: Elite Themes — 100 VS Code themes for developers earning $10k+/month"
  - Engage with all comments (be humble!)

**Day 2:**
- [ ] Post to Reddit:
  - r/vscode
  - r/webdev
  - r/SideProject
  - r/EntrepreneurRideAlong
- [ ] Email dev influencers (use template from MARKETING.md)

**Day 3-7:**
- [ ] Post 1 TikTok/day showing different themes
- [ ] Tweet daily progress ("Day 3: 500 downloads! 🚀")
- [ ] Answer all questions in Discord/Reddit

---

## 🔄 Part 6: Updates & Maintenance

### How to Publish Updates:

1. Make changes to themes
2. Update version in `package.json`:
   ```json
   "version": "1.0.1"  // increment last number
   ```
3. Update `CHANGELOG.md` (create if doesn't exist):
   ```markdown
   ## [1.0.1] - 2026-02-20
   ### Added
   - New theme: EditorDark Elite
   ### Fixed
   - Improved contrast in NeonHustle
   ```
4. Commit and push to GitHub
5. Publish update:
   ```bash
   npx vsce publish
   ```

**Users get auto-updated within 24 hours!**

---

## 💡 Pro Tips

### Tip 1: Add Screenshots
Before first publish, add screenshots:
1. Open VS Code with a theme
2. Open a code file (React, Python, etc.)
3. Take screenshot (`Win + Shift + S` or `Cmd + Shift + 4`)
4. Save to `assets/screenshots/themename.png`
5. Add to README.md gallery

### Tip 2: Add Icon
Create a 512x512 PNG logo:
1. Use Canva / Figma / AI generator
2. Save as `assets/icons/logo.png`
3. Update `package.json`: `"icon": "assets/icons/logo.png"`

### Tip 3: Track Analytics
- VS Code Marketplace shows install count
- Google Analytics (add to GitHub Pages if you make a site)
- Track revenue in spreadsheet:
  ```
  Date | Sponsors | MRR | Notes
  Feb 14 | 10 | $50 | Launch day!
  Feb 21 | 50 | $250 | ProductHunt boost
  ```

### Tip 4: Automate with GitHub Actions
Create `.github/workflows/publish.yml`:
```yaml
name: Publish
on:
  push:
    tags:
      - 'v*'
jobs:
  publish:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
      - run: npm install
      - run: npx vsce publish -p ${{ secrets.VSCE_TOKEN }}
```

Add `VSCE_TOKEN` secret in repo settings → publish by creating git tag!

---

## 🆘 Troubleshooting

### "Publisher not found"
- Make sure you created publisher at marketplace.visualstudio.com/manage
- Publisher name in `package.json` must match exactly

### "Personal Access Token is invalid"
- Generate new token at dev.azure.com
- Make sure "Marketplace (Publish)" scope is checked
- Run `npx vsce login YOUR_PUBLISHER` again

### "Themes don't show up in search"
- Wait 10-15 minutes after publishing
- Try exact name: "Elite Themes 2026"
- Check marketplace.visualstudio.com for your extension

### "Can't install vsce"
- Make sure Node.js 18+ is installed: `node --version`
- Run `npm install` in project folder first
- Try `npm install -g @vscode/vsce` (global install)

---

## ✅ Success Checklist

Before you finish, verify:

- [ ] Themes published and searchable on Marketplace
- [ ] GitHub Sponsors enabled with tiers
- [ ] All links in README point to your accounts
- [ ] Discord server created and invite works
- [ ] Twitter/X account created
- [ ] ProductHunt post scheduled
- [ ] Screenshots look good

**You're ready to make money! 🚀💰**

---

## 📞 Need Help?

If you get stuck:
1. Check VS Code publishing docs: https://code.visualstudio.com/api/working-with-extensions/publishing-extension
2. Ask in GitHub Discussions (if we enable them)
3. Email: elite@yourmail.com

**Good luck with your launch! 🎉**
