**Rule of thumb:** every subject/practicals HTML page and its PDFs live in the same folder, so links between them stay simple (just the filename, no folder path needed).

---

## ➕ How to add a new PDF to an existing subject page

Example: adding a new PDF to Anatomy & Physiology.

1. **Upload the PDF** into `pharmacy-technician/year1/` (Add file → Upload files → type the folder path `pharmacy-technician/year1` before dragging the file in).
   - Keep filenames lowercase, no spaces — use hyphens. Example: `nervous-system-notes.pdf`
2. **Open the subject's HTML file** (e.g. `pharmacy-technician/year1/anatomy-physiology.html`) → click the pencil (✏️) icon to edit.
3. **Copy one existing note-card block** (the whole thing from `<div class="note-card">` to its matching `</div>`) and paste it right after the last one.
4. **Edit 3 things** in the new card:
   - The title inside `<h4>...</h4>`
   - The description inside `<p class="desc">...</p>`
   - The `href="..."` value — must exactly match your uploaded PDF's filename
5. **Commit changes.**

A note-card looks like this:
```html
<div class="note-card">
  <div class="icon">PDF</div>
  <div class="meta">
    <h4>Topic Title Here</h4>
    <p class="desc">Short description of what this covers.</p>
    <p class="tags">Subject Name · Year 1</p>
  </div>
  <div class="dl">
    <a class="btn btn-primary" href="your-file-name.pdf" download>Download</a>
  </div>
</div>
```

---

## 📚 How to add a brand-new subject page (Year 1 or Year 2)

1. Create a new file, e.g. `pharmacy-technician/year1/pharmaceutics.html`.
2. Copy the full content of `anatomy-physiology.html` as a starting template.
3. Update the `<title>`, the `<h1>` heading, and the breadcrumb text to match the new subject.
4. Replace the note-cards with real ones (or leave a "coming soon" placeholder — see `practicals.html` for an example of that pattern).
5. Go to `pharmacy-technician/index.html` and update the matching subject card's link (it likely already points to the right filename if you followed the naming pattern) and remove the "coming soon" wording if present.

---

## 🧪 How Practicals work

`pharmacy-technician/year1/practicals.html` has **one section per subject** (Anatomy & Physiology, Pharmaceutics, Pharmacognosy, Biochemistry, Microbiology). Each section either shows a "no practicals yet" placeholder paragraph, or one or more note-cards — same pattern as subject notes pages. To add a practical PDF, follow the same steps as "adding a new PDF" above, just place the card under the correct subject heading inside `practicals.html`.

---

## 🗓️ Adding Year 2

When Year 2 subjects are decided:
1. Create a `pharmacy-technician/year2/` folder (same pattern as `year1/`).
2. Build subject pages and a practicals page the same way as Year 1.
3. Update the "Year 2" section in `pharmacy-technician/index.html` — replace the "coming soon" text with real subject cards, same layout as the Year 1 grid.
4. Add the new page URLs to `sitemap.xml`.

---

## 🌱 Adding a whole new course (e.g. OTT, Medical Lab Technician)

1. Create a new top-level folder, e.g. `medical-lab-technician/`, with the same internal structure as `pharmacy-technician/` (`index.html`, `year1/`, etc.).
2. Add a card for it on the root `index.html` linking to `medical-lab-technician/index.html`.
3. `about.html`, `contact.html`, `privacy.html`, and `css/style.css` are shared — no need to duplicate them.

---

## 🔍 Google Search Console (SEO)

- Site is verified in [Google Search Console](https://search.google.com/search-console).
- `sitemap.xml` lists all pages for Google to crawl — **update this file** whenever a major new page (a full subject page) is added.
- After adding a significant new page, use **URL Inspection → Request Indexing** in Search Console to speed up discovery. Don't bother doing this for small edits (like adding one card to an existing page).
- New sites can take weeks to a couple months to rank well. Consistent content + real visitors (shared via WhatsApp/Facebook groups, forums, etc.) speeds this up.

---

## ✅ Content rules

- All notes must be **original** — no scanned textbooks or copyrighted material. This matters both legally and for future Google AdSense approval.
- Keep filenames lowercase with hyphens, no spaces.
- Every new HTML page needs `<link rel="stylesheet" href="...css/style.css">` in the `<head>` — count the folder depth carefully:
  - 1 level deep (e.g. `about.html`) → `css/style.css`
  - 2 levels deep (e.g. `pharmacy-technician/index.html`) → `../css/style.css`
  - 3 levels deep (e.g. `pharmacy-technician/year1/anatomy-physiology.html`) → `../../css/style.css`
