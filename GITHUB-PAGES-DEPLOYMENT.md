# GitHub Pages Deployment Instructions

This guide will help you deploy your AI for Cybersecurity portfolio as your GitHub Pages homepage.

## Package Contents

The `github-pages-website.zip` contains:

- **index.html** - Main portfolio page (fully built and ready)
- **assets/** - CSS and JavaScript files
- **README.md** - Repository documentation
- **.nojekyll** - Tells GitHub Pages not to use Jekyll processing

## Deployment Options

You have two main options for deploying this portfolio:

### Option 1: User GitHub Pages (Recommended for Homepage)

This makes the portfolio your main GitHub homepage at `https://smsafavi.github.io`

#### Steps:

1. **Create a new repository** named exactly `smsafavi.github.io` (replace with your username)
   - Go to https://github.com/new
   - Repository name: `smsafavi.github.io`
   - Make it **Public**
   - Do NOT initialize with README

2. **Extract the zip file** and navigate to the `github-pages` folder

3. **Initialize git and push**:
   ```bash
   cd github-pages
   git init
   git add .
   git commit -m "Initial commit: AI for Cybersecurity Portfolio"
   git branch -M main
   git remote add origin https://github.com/smsafavi/smsafavi.github.io.git
   git push -u origin main
   ```

4. **Wait 1-2 minutes** for GitHub to build and deploy

5. **Visit your site** at https://smsafavi.github.io

### Option 2: Project GitHub Pages

This deploys the portfolio to a specific repository at `https://smsafavi.github.io/portfolio`

#### Steps:

1. **Create a new repository** with any name (e.g., `portfolio`)
   - Make it **Public**
   - Do NOT initialize with README

2. **Extract and push** (same as Option 1, but with different URL):
   ```bash
   cd github-pages
   git init
   git add .
   git commit -m "Initial commit: AI for Cybersecurity Portfolio"
   git branch -M main
   git remote add origin https://github.com/smsafavi/portfolio.git
   git push -u origin main
   ```

3. **Enable GitHub Pages**:
   - Go to repository **Settings**
   - Navigate to **Pages** (left sidebar)
   - Under "Source", select **Deploy from a branch**
   - Branch: **main**, Folder: **/ (root)**
   - Click **Save**

4. **Wait 1-2 minutes** for deployment

5. **Visit your site** at https://smsafavi.github.io/portfolio

## Updating Your Portfolio

When you want to update the portfolio:

1. Make changes to the files
2. Commit and push:
   ```bash
   git add .
   git commit -m "Update portfolio"
   git push
   ```

3. GitHub Pages will automatically rebuild (takes 1-2 minutes)

## Verification

After deployment, verify:

- ✅ Site loads at the correct URL
- ✅ All 5 batches are visible
- ✅ All 50 projects are displayed
- ✅ Links to GitHub repositories work
- ✅ Responsive design works on mobile
- ✅ No console errors in browser DevTools

## Customization

### Update GitHub Links

If you need to update the GitHub repository links in the portfolio:

1. Open `index.html` in a text editor
2. Search for `https://github.com/smsafavi/ai-cybersecurity-lab`
3. Replace with your actual repository URLs
4. Save and push changes

### Custom Domain (Optional)

To use a custom domain like `safavi.com`:

1. **Purchase a domain** from a registrar
2. **Add CNAME file** to your repository:
   ```bash
   echo "safavi.com" > CNAME
   git add CNAME
   git commit -m "Add custom domain"
   git push
   ```

3. **Configure DNS** at your domain registrar:
   - Add a CNAME record pointing to `smsafavi.github.io`
   - Or add A records pointing to GitHub's IPs:
     - 185.199.108.153
     - 185.199.109.153
     - 185.199.110.153
     - 185.199.111.153

4. **Enable HTTPS** in repository Settings → Pages

## Troubleshooting

### Site Not Loading

- Check repository name is exactly `username.github.io` for user pages
- Ensure repository is **Public**
- Wait 2-5 minutes for initial deployment
- Check Settings → Pages for deployment status

### 404 Error

- Verify `index.html` is in the root directory
- Check branch and folder settings in Pages configuration
- Ensure `.nojekyll` file is present

### Styling Issues

- Check browser console for errors
- Verify all files in `assets/` folder are present
- Clear browser cache and reload

### Links Not Working

- Update repository URLs in `index.html` if needed
- Ensure target repositories exist and are public

## Integration with Other Repositories

This portfolio links to:

1. **ai-cybersecurity-playbook** - Documentation hub
2. **ai-cybersecurity-lab** - Project implementations

Make sure to create these repositories and update links accordingly.

## Repository Structure

```
smsafavi.github.io/
├── index.html              # Main portfolio page
├── assets/
│   ├── index-*.css        # Compiled styles
│   └── index-*.js         # Compiled JavaScript
├── README.md              # Repository documentation
└── .nojekyll              # Disable Jekyll processing
```

## Performance

The built portfolio is optimized:

- **Minified CSS**: ~115 KB (gzipped: ~18 KB)
- **Minified JS**: ~530 KB (gzipped: ~155 KB)
- **Total page size**: ~366 KB (gzipped: ~105 KB)
- **Load time**: < 2 seconds on average connection

## SEO Optimization

The portfolio includes:

- ✅ Proper page title
- ✅ Meta viewport for mobile
- ✅ Semantic HTML structure
- ✅ Descriptive headings

To improve SEO, consider adding:

```html
<meta name="description" content="Dr. Seyedmostafa Safavi - AI for Cybersecurity Educational Playbook with 50 reproducible ML projects">
<meta name="keywords" content="AI, Cybersecurity, Machine Learning, Intrusion Detection, XAI">
<meta name="author" content="Dr. Seyedmostafa Safavi">
```

## Analytics (Optional)

To track visitors, add Google Analytics:

1. Create a Google Analytics account
2. Get your tracking ID (e.g., `G-XXXXXXXXXX`)
3. Add before `</head>` in `index.html`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

## Support

For issues:

- Check GitHub Pages documentation: https://docs.github.com/pages
- Review deployment logs in repository Actions tab
- Open an issue in your repository

---

**Your portfolio is ready to deploy!** Follow the steps above to make it live. 🚀

