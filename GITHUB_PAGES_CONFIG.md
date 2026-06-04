# GitHub Pages Deployment Configuration

**Minimal Academic Design for Tammetry Static Site**

---

## SITE STRUCTURE

```
docs/
├── index.md                          (Home page)
├── _config.yml                       (Jekyll configuration)
├── assets/
│   ├── css/
│   │   ├── style.css                (Custom styling)
│   │   └── minimal-academic.css      (Theme base)
│   └── js/
│       └── mathjax-config.js         (Math rendering)
├── about.md                          (About Tammetry)
├── author.md                         (About Arthur Nguyen)
├── foundations/
│   ├── 01-definition.md
│   ├── 02-axioms.md
│   ├── 03-field-equations.md
│   └── 04-operator-algebra.md
├── disciplinary/
│   ├── 05-manifesto.md
│   ├── 06-cross-domain-unity.md
│   └── 07-knowledge-taxonomy.md
├── integration/
│   ├── 08-physics-integration.md
│   ├── 09-mathematical-foundations.md
│   └── 10-epistemology.md
├── submissions/
│   ├── arxiv.md
│   ├── math-journals.md
│   ├── physics-journals.md
│   └── philosophy-journals.md
└── _layouts/
    ├── default.html
    ├── post.html
    └── page.html
```

---

## CONFIGURATION FILE: _config.yml

```yaml
# Tammetry Static Site Configuration

title: Tammetry - Toroidal-Artic Meta-Manifold Geometry
description: A new mathematical discipline for recursive toroidal manifolds and operator-driven geometry
author: Arthur Nguyen
baseurl: "/Tammetry-Toroidal-Artic-Meta-Manifold-Geometry"
url: "https://thearchitect132.github.io"

# Theme
theme: jekyll-theme-minimal
remote_theme: pages-themes/minimal@v0.2.0
plugins:
  - jekyll-remote-theme
  - jekyll-feed
  - jekyll-seo-tag

# Markdown
markdown: kramdown
kramdown:
  math_engine: mathjax
  input: GFM

# Collections
collections:
  foundations:
    output: true
    permalink: /foundations/:name/
  disciplinary:
    output: true
    permalink: /disciplinary/:name/
  integration:
    output: true
    permalink: /integration/:name/
  submissions:
    output: true
    permalink: /submissions/:name/

# Navigation
nav_menu:
  - title: "Home"
    url: "/"
  - title: "About"
    url: "/about"
  - title: "Foundations"
    url: "/foundations/"
    submenu:
      - title: "Definition"
        url: "/foundations/01-definition"
      - title: "Axioms"
        url: "/foundations/02-axioms"
      - title: "Field Equations"
        url: "/foundations/03-field-equations"
      - title: "Operator Algebra"
        url: "/foundations/04-operator-algebra"
  - title: "Disciplinary"
    url: "/disciplinary/"
    submenu:
      - title: "Manifesto"
        url: "/disciplinary/05-manifesto"
      - title: "Cross-Domain Unity"
        url: "/disciplinary/06-cross-domain-unity"
      - title: "Knowledge Taxonomy"
        url: "/disciplinary/07-knowledge-taxonomy"
  - title: "Integration"
    url: "/integration/"
    submenu:
      - title: "Physics"
        url: "/integration/08-physics-integration"
      - title: "Mathematical Foundations"
        url: "/integration/09-mathematical-foundations"
      - title: "Epistemology"
        url: "/integration/10-epistemology"
  - title: "Submissions"
    url: "/submissions/"
  - title: "Author"
    url: "/author"

# Build settings
exclude:
  - .gitignore
  - README.md
  - LICENSE
  - .jekyll-cache
  - .sass-cache
```

---

## CUSTOM CSS: assets/css/style.css

```css
/* Tammetry Minimal Academic Theme */

:root {
  --primary-color: #1a1a2e;      /* Deep navy */
  --secondary-color: #16213e;    /* Darker navy */
  --accent-color: #0f3460;       /* Deep blue */
  --highlight-color: #e94560;    /* Crimson accent */
  --text-color: #333333;
  --light-gray: #f5f5f5;
  --border-color: #e0e0e0;
  --font-family: 'Georgia', 'Times New Roman', serif;
  --mono-family: 'Courier New', monospace;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: var(--font-family);
  color: var(--text-color);
  background-color: white;
  line-height: 1.6;
  font-size: 16px;
}

header {
  background-color: var(--primary-color);
  color: white;
  padding: 40px 20px;
  text-align: center;
  border-bottom: 3px solid var(--highlight-color);
}

header h1 {
  font-size: 2.5em;
  font-weight: 700;
  margin-bottom: 10px;
  letter-spacing: 1px;
}

header p {
  font-size: 1.1em;
  font-style: italic;
  opacity: 0.9;
}

nav {
  background-color: var(--secondary-color);
  overflow: hidden;
  padding: 0;
  margin: 0;
}

nav ul {
  list-style: none;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

nav li {
  position: relative;
}

nav a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 20px;
  text-decoration: none;
  transition: background-color 0.3s;
}

nav a:hover {
  background-color: var(--accent-color);
}

main {
  max-width: 900px;
  margin: 40px auto;
  padding: 0 20px;
}

article {
  line-height: 1.8;
}

h1 {
  font-size: 2em;
  margin-top: 40px;
  margin-bottom: 20px;
  border-bottom: 2px solid var(--highlight-color);
  padding-bottom: 10px;
  color: var(--primary-color);
}

h2 {
  font-size: 1.6em;
  margin-top: 30px;
  margin-bottom: 15px;
  color: var(--primary-color);
}

h3 {
  font-size: 1.3em;
  margin-top: 20px;
  margin-bottom: 10px;
  color: var(--accent-color);
}

p {
  margin-bottom: 15px;
  text-align: justify;
}

code {
  background-color: var(--light-gray);
  padding: 2px 6px;
  border-radius: 3px;
  font-family: var(--mono-family);
  font-size: 0.9em;
}

pre {
  background-color: var(--light-gray);
  padding: 15px;
  border-radius: 5px;
  overflow-x: auto;
  border-left: 4px solid var(--highlight-color);
}

table {
  border-collapse: collapse;
  margin: 20px 0;
  width: 100%;
}

table th {
  background-color: var(--accent-color);
  color: white;
  padding: 12px;
  text-align: left;
  border: 1px solid var(--border-color);
}

table td {
  padding: 10px;
  border: 1px solid var(--border-color);
}

table tr:nth-child(even) {
  background-color: var(--light-gray);
}

blockquote {
  border-left: 4px solid var(--highlight-color);
  padding-left: 15px;
  margin: 20px 0;
  font-style: italic;
  color: #555;
}

a {
  color: var(--accent-color);
  text-decoration: none;
  border-bottom: 1px dotted var(--accent-color);
}

a:hover {
  color: var(--highlight-color);
  border-bottom-color: var(--highlight-color);
}

footer {
  background-color: var(--primary-color);
  color: white;
  text-align: center;
  padding: 20px;
  margin-top: 60px;
  font-size: 0.9em;
}

/* Responsive Design */
@media (max-width: 768px) {
  header h1 {
    font-size: 1.8em;
  }

  nav ul {
    flex-direction: column;
  }

  nav li {
    width: 100%;
  }

  main {
    margin: 20px auto;
  }

  h1 {
    font-size: 1.5em;
  }

  h2 {
    font-size: 1.2em;
  }
}

/* Math rendering */
.math {
  font-family: 'STIX Two Math', var(--mono-family);
}

mjx-container {
  text-align: center;
  margin: 20px 0;
}
```

---

## HOME PAGE: index.md

```markdown
---
layout: default
title: Tammetry
---

# Welcome to Tammetry

**Toroidal-Artic Meta-Manifold Geometry**

A rigorous mathematical discipline for recursive toroidal manifolds and domain-operator dynamics.

## What is Tammetry?

Tammetry is a new mathematical framework that studies recursive toroidal manifolds through a five-operator non-commutative algebra. It provides:

- **Mathematical rigor** — Seven axioms, seven field equations, proven theorems
- **Physics unification** — Single framework for General Relativity, Quantum Mechanics, and Thermodynamics
- **Epistemological clarity** — Meta-structure for organizing all human knowledge
- **Systems theory** — Foundation for modeling complex multi-layered systems

## Core Concepts

### The Tammetric Manifold
$$\mathcal{T} = (\Theta, \Phi, n, \Omega, \mathbb{U})$$

### The Five Operators
- **Identity** (𝕀) — Invariant coherence
- **Structure** (𝕊) — Pattern and form
- **Restoration** (𝕽) — Stability and correction
- **Direction** (𝔻) — Flow and causality
- **Expansion** (𝔼) — Growth and innovation

### Key Axioms
1. Recursive Toroidal Geometry
2. Operator Primacy
3. Non-Commutativity: $[\mathbb{S}, \mathbb{D}] \neq 0$
4. Duality: $[\mathbb{R}, \mathbb{E}] = \mathbb{I}$
5. Identity Invariance
6. Horizon-Rotational Metric
7. Q-State Convergence

## Documentation Structure

### [Foundations](/foundations/)
- [Definition](foundations/01-definition)
- [Axioms](foundations/02-axioms)
- [Field Equations](foundations/03-field-equations)
- [Operator Algebra](foundations/04-operator-algebra)

### [Disciplinary Layer](/disciplinary/)
- [Manifesto](disciplinary/05-manifesto)
- [Cross-Domain Unity](disciplinary/06-cross-domain-unity)
- [Knowledge Taxonomy](disciplinary/07-knowledge-taxonomy)

### [Integration](/integration/)
- [Physics Integration](integration/08-physics-integration)
- [Mathematical Foundations](integration/09-mathematical-foundations)
- [Epistemology](integration/10-epistemology)

### [Submissions & Publications](/submissions/)
- arXiv Master Document
- Mathematics Journal Submission
- Physics Journal Submission
- Philosophy Journal Submission

## About the Author

**Arthur Nguyen** — Founder of Aleph Prime Enterprises, systems thinker, pharmacist, regulatory inspector. Creator of Tammetry and the Aleph Prime Universe.

For more: [About Arthur](about)

## Get Started

1. **New to Tammetry?** Start with the [Manifesto](disciplinary/05-manifesto)
2. **Mathematician?** Begin with [Axioms](foundations/02-axioms)
3. **Physicist?** Explore [Physics Integration](integration/08-physics-integration)
4. **Philosopher?** Dive into [Epistemology](integration/10-epistemology)

---

**Latest Update:** June 4, 2026  
**Status:** Foundation Documentation Complete (v1.0)  
**Submissions:** Ready for arXiv and academic journals
```

---

## DEPLOYMENT INSTRUCTIONS

### Step 1: Enable GitHub Pages
1. Go to repository Settings
2. Navigate to Pages section (left sidebar)
3. Select "Deploy from a branch"
4. Choose branch: `tammetry-core-documentation`
5. Choose folder: `/docs`
6. Click Save

### Step 2: Create docs/ Directory
Create a `docs/` folder in the `tammetry-core-documentation` branch and upload all markdown files and configuration.

### Step 3: Verify Deployment
- Check repository Settings → Pages
- Wait 1-2 minutes for build
- Site appears at: `https://thearchitect132.github.io/Tammetry-Toroidal-Artic-Meta-Manifold-Geometry`

### Step 4: Custom Domain (Optional)
To use custom domain:
1. Settings → Pages → Custom domain
2. Enter domain (e.g., tammetry.org)
3. Update DNS records at domain registrar
4. Verify SSL certificate

---

## SITE FEATURES

✅ Clean, minimal academic design
✅ Full mathematical rendering (MathJax)
✅ Responsive mobile design
✅ Fast load times (static HTML)
✅ Built-in search (Jekyll search plugin)
✅ Automatic sitemap generation
✅ SEO optimized
✅ Free hosting on GitHub

---

**Site Status:** Ready to deploy  
**Estimated Build Time:** 1-2 minutes after first push  
**Maintenance:** Automatic updates when branch content changes
