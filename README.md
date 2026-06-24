# vikas-resume-template
Iniatial Resume templete-2026

# Vikas's Resume Template

**Your resume shouldn't look like everyone else's Word doc.**

I know most of y'all are doing this right now:

1. Open Word
2. Use whatever template came with it
3. Wrestle with margins for 2 hours
4. Export to PDF
5. It looks fine but not great
6. Wonder why your resume doesn't stand out

I did the same thing freshman year. Then I saw upperclassmen using LaTeX and their resumes looked ten times cleaner with half the effort. That's why I'm sharing this.

---

## Table of Contents

- [What Even Is LaTeX?](#what-even-is-latex)
- [Why Should I Care?](#why-should-i-care)
- [The 3 Ways To Use This](#the-3-ways-to-use-this)
- [Getting Started (Pick One)](#getting-started-pick-one)
  - [Overleaf (Easiest)](#overleaf-easiest)
  - [VS Code + LaTeX Workshop](#vs-code--latex-workshop)
  - [Local Install (Terminal People)](#local-install-terminal-people)
- [Your First 15 Minutes](#your-first-15-minutes)
- [How to Edit the Template](#how-to-edit-the-template)
- [Customizing the Look](#customizing-the-look)
- [Mistakes Every Beginner Makes](#mistakes-every-beginner-makes)
- [Which Route Should I Use?](#which-route-should-i-use)
- [Going Further](#going-further)

---

## What Even Is LaTeX?

You know how Word is a "what you see is what you get" editor where you drag things around until the margins cry? LaTeX flips it. You write your resume like code, compile it, and out pops a PDF that actually looks professional.

Here's what it can do that Word can't:

- Consistent spacing every single time -- no more "why is this line a pixel off"
- Version control with git (your resume lives in a repo like real code)
- Change one color or font and it applies everywhere
- Re-render in seconds instead of re-dragging text boxes
- Looks cleaner than literally any default Word template

Easiest way to think about it:

| | Word / Google Docs | LaTeX |
|---|---|---|
| How you edit | Click and drag | Write markup |
| Spacing consistency | Depends on your mouse | Pixel-perfect every time |
| Version control | "resume_final_v4_ACTUAL.docx" | Git like a normal person |
| Looks out of the box | Fine | Clean |
| Change accent color | Reformat 20 sections | Edit one line |

Word is like writing your resume in Photoshop. LaTeX is like writing your resume in React -- you define the structure once and the formatting just works.

---

## Why Should I Care?

Honestly? This changed how I apply to things. Here's what's different:

- **Recruiters notice.** Your resume looks different from the 400 other Word docs in the stack. Not flashy -- just clean.
- **Edits take seconds.** Need to tweak for a specific role? Change two lines instead of re-formatting the whole page.
- **One source, many versions.** Keep a main version in git and branch off tailored ones.
- **You learn a real tool.** LaTeX shows up in academia, research papers, and technical writing. Might as well pick it up now.

I'm not gonna pretend LaTeX has zero learning curve. The first hour is rough. But after that it's just faster than fighting Word.

---

## The 3 Ways To Use This

There are three common paths. All of them are free.

| Option | Setup Effort | Best For |
|---|---|---|
| **Overleaf** | Zero (browser) | Just want to edit and export a PDF |
| **VS Code + LaTeX Workshop** | Medium | Already live in VS Code |
| **Local Install (MacTeX/TeX Live)** | Annoying | Full control, terminal power users |

You don't need all three. Pick one and go.

---

## Getting Started (Pick One)

### Overleaf (Easiest)

No install. Runs in your browser. Free.

1. Go to [overleaf.com](https://www.overleaf.com) and make an account.
2. Click **New Project** -> **Upload Project**.
3. Upload `resume.tex` from this repo.
4. Click the green **Recompile** button. You should see the PDF appear.

That's it. Edit the `.tex` file on the left, watch the PDF update on the right.

---

### VS Code + LaTeX Workshop

If you already use VS Code for everything:

1. Install [VS Code](https://code.visualstudio.com) if you don't have it.
2. Install a LaTeX distribution:
   - **Mac:** [MacTeX](https://www.tug.org/mactex/) (big download, one time)
   - **Windows:** [MiKTeX](https://miktex.org/download)
   - **Linux:** `sudo apt install texlive-full` (or your distro's equivalent)
3. In VS Code, install the **LaTeX Workshop** extension.
4. Open `resume.tex`. Hit the little green play button (top right) to compile.

Now you get hot reload, autocomplete, and inline error messages. Feels like writing real code.

---

### Local Install (Terminal People)

If you want to compile from the command line:

```bash
# Mac (Homebrew)
brew install --cask mactex

# Windows
# Download MiKTeX from https://miktex.org/download

# Linux (Debian/Ubuntu)
sudo apt install texlive-full
```

Then:

```bash
cd andrew-resume-template
pdflatex resume.tex
```

Your PDF comes out as `resume.pdf`.

---

## Your First 15 Minutes

Alright you've got it opened. Here's what to do.

### 1. Find your name

At the top of `resume.tex` there's a `HEADING` section. It looks like this:

```latex
{\Huge \scshape \textcolor{AccentColor}{\textbf{YOUR NAME}}}
```

Replace `YOUR NAME` with your actual name. Do the same for email, LinkedIn, phone, and GitHub right below it.

### 2. Fill in Education

Find the `\section{Education}` block and swap the placeholder fields for your real ones. Don't delete the `\resumeSubheading` or `\resumeItemListStart` commands -- those are the formatting.

### 3. Experience and Projects

Same pattern. Each entry is a `\resumeSubheading` or `\resumeProjectHeading` followed by a list of bullet points (`\resumeItem{...}`). Copy an existing block if you need more entries.

### 4. Recompile

Hit recompile (Overleaf) or save (VS Code with auto-build). PDF updates. If it doesn't compile, scroll up in the log and look for the first red error -- that's usually the real problem.

### 5. Export the PDF

- **Overleaf:** download button, top right.
- **VS Code:** the PDF is already in the project folder -- `resume.pdf`.
- **Terminal:** same folder you ran `pdflatex` in.

That's it. You've got a professional-looking resume in under 15 minutes.

---

## How to Edit the Template

The template has these sections, in order:

- **Heading** -- your name and contact info
- **Education** -- school, degree, GPA, coursework
- **Experience** -- jobs and internships
- **Projects** -- side projects you want to show off
- **Leadership** -- clubs, orgs, volunteering
- **Skills** -- languages, frameworks, tools
- **Awards** -- anything you've won or been recognized for

You can delete any section you don't need. Just delete everything from `\section{SectionName}` down to the next `\section{...}` (or `\end{document}` if it's the last one).

To add more entries inside a section, copy an existing `\resumeSubheading{...}` or `\resumeProjectHeading{...}` block.

---

## Customizing the Look

### Change the accent color

Near the top of the file:

```latex
\definecolor{AccentColor}{RGB}{0, 32, 96} % Navy Blue
```

Swap the RGB values. A few that look good:

```latex
\definecolor{AccentColor}{RGB}{0, 100, 0}    % Dark Green
\definecolor{AccentColor}{RGB}{128, 0, 32}   % Burgundy
\definecolor{AccentColor}{RGB}{33, 33, 33}   % Near-black (most conservative)
```

### Change the font

The template uses Helvetica by default:

```latex
\usepackage[scaled]{helvet}
\renewcommand{\familydefault}{\sfdefault}
```

If you want a more traditional serif look, delete those two lines. LaTeX defaults back to Computer Modern (the classic academic font).

### Adjust margins

Near the top:

```latex
\addtolength{\oddsidemargin}{-0.7in}
\addtolength{\textwidth}{1.4in}
```

Making `-0.7in` smaller (like `-0.5in`) gives you wider margins. Making it larger (like `-0.9in`) gives you more text space. Keep them symmetric.

---

## Mistakes Every Beginner Makes

### 1. Not reading the error message

LaTeX errors look scary but the important line is usually the first red one. Scroll up, read it, fix it. Don't panic.

### 2. Special characters breaking things

`%`, `&`, `#`, `_`, `$` are all special in LaTeX. If you want them in your text, escape them with a backslash: `\%`, `\&`, `\_`, etc. This one trips up everyone the first time.

### 3. Trying to format by adding spaces

In LaTeX, adding extra spaces or blank lines doesn't always do what you think. Use `\vspace{...}`, `\\`, or the existing commands for layout. Brute-forcing with whitespace will fight you.

### 4. Making your resume longer than one page

If you're a student or early-career, keep it one page. The template is designed to fit on one page. If yours is spilling to two, cut the weakest bullet points -- don't shrink the font below 10pt.

### 5. Not saving a `.cls`-free version

Some job application portals reject `.cls` or auxiliary files. Always submit the compiled **PDF**, not the raw LaTeX.

---

## Which Route Should I Use?

If you're still going back and forth:

```
Never used LaTeX? ..................... Overleaf
Already use VS Code? .................. VS Code + LaTeX Workshop
Want the nerdiest workflow? ........... Local install
Using a Chromebook / tablet? .......... Overleaf
```

They all produce the same PDF. Seriously, pick one.

---

## Going Further

Once you're comfortable:

**Version control your resume** -- fork this repo, commit every edit, branch off tailored versions for specific roles.

**Read the source** -- skim through `resume.tex` and figure out what each command does. The custom commands at the top (`\resumeItem`, `\resumeSubheading`, `\resumeProjectHeading`) are where the magic lives.

**Go deeper:**
- [Overleaf LaTeX in 30 Minutes](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes) -- the official crash course.
- [LaTeX Wikibook](https://en.wikibooks.org/wiki/LaTeX) -- full reference when you want to do something weird.

---

## Contributing

If something in here confused you, open an issue. If you made a cleaner version or a fix, open a PR.

---

MIT License. Use it, share it, whatever.
