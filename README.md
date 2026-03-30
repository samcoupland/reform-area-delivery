# 📋 Leaflet Delivery Area Manager

A single-file web application for managing leaflet delivery areas. Track streets, monitor progress, print area sheets, and export everything as a PDF — all styled in Reform Party teal.

---

## Getting Started

No installation is required. Simply open `leaflet-delivery.html` in any modern web browser (Chrome, Firefox, Edge, Safari).

```
File → Open → leaflet-delivery.html
```

Two sample areas are pre-loaded on first launch so you can see how the app looks straight away. Delete them and add your real areas when you're ready.

---

## Features

- **Area index** — a numbered contents page showing all delivery areas at a glance
- **Per-area pages** — each area has its own page with a street checklist, map slot, and summary panel
- **Progress tracking** — tick off streets as you go; progress is saved automatically in the browser
- **Print to A4** — print any individual area page cleanly, with all UI chrome hidden
- **Export all as PDF** — generate a single PDF containing the index page followed by one A4 sheet per area

---

## How to Use

### Adding an Area

1. Click **+ Add Area** in the top-right corner
2. Enter the area name (e.g. *North High Street*)
3. Optionally add notes (e.g. *include side roads*) and a map URL
4. Click **Add Area**

### Adding Streets to an Area

1. Click an area card to open its detail page
2. Type a street name into the **Add a street name…** field at the bottom of the checklist
3. Press **Enter** or click **Add**

### Ticking Off Streets

Click the checkbox next to any street to mark it as completed. Click again to unmark it. Progress is saved automatically.

### Adding a Map

On any area detail page, paste a Google Maps embed URL into the map URL field and click **Save**. To get an embed URL from Google Maps:

1. Search for your area on [maps.google.com](https://maps.google.com)
2. Click **Share → Embed a map**
3. Copy the `src="..."` URL from the iframe code

> **Note:** Maps will display in the web app but will not render in the exported PDF due to browser security restrictions. The PDF will note to refer to the digital version instead.

### Deleting an Area

Open the area detail page and click **Delete Area** (bottom right). You will be asked to confirm before anything is removed.

---

## Printing

### Print a Single Area

Open the area detail page and click the **🖨 Print** button. The browser print dialogue will open. Make sure to select:

- **Paper size:** A4
- **Margins:** Default or Minimum
- **Background graphics:** Enabled (for colour headers and progress bars)

### Export All Areas as PDF

Click **⬇ Export PDF** in the top navigation bar. A PDF named `leaflet-delivery-areas.pdf` will be generated and downloaded automatically. It includes:

1. An index/contents page listing all areas with their progress
2. One A4 page per area, showing the street checklist and summary

---

## Data Storage

All data is saved to your browser's **local storage**. This means:

- Data persists between sessions on the same browser and device
- Data is **not** synced between devices or browsers
- Clearing your browser's site data will erase all areas and streets

To back up your data, use the **Export PDF** feature regularly.

---

## Technical Notes

| Detail | Value |
|---|---|
| File type | Single self-contained `.html` file |
| Dependencies | Google Fonts (loaded online), html2pdf.js (loaded via CDN) |
| Browser support | Chrome, Edge, Firefox, Safari (modern versions) |
| Offline use | Fully functional offline except for Google Fonts and map embeds |
| Primary colour | `#00bed6` (Reform Party teal) |

---

## File Structure

This is a single-file application. Everything — HTML, CSS, and JavaScript — lives in `leaflet-delivery.html`. There are no other files to manage.

---

## Troubleshooting

**The PDF export button does nothing or shows an error**
Make sure you have an internet connection when first loading the page, as the PDF library is loaded from a CDN.

**My data has disappeared**
Check that you are using the same browser you originally used. Data is stored per-browser. If you cleared your browsing data, the areas will have been removed.

**The map is not showing**
Ensure the URL you pasted is a valid Google Maps *embed* URL (it should begin with `https://www.google.com/maps/embed?`), not a regular Google Maps link.

**Print colours are not showing**
In your browser's print settings, enable **Background graphics** (sometimes called *Print backgrounds*).
