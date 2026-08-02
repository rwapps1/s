# Photos → PDF

A single-file, browser-based tool that combines photos and scans (JPG, PNG, GIF, BMP, WEBP, TIFF) into one ordered, compressed PDF. No installs, no server, no uploads — everything runs locally in the browser.

## Features

- **Multiple formats** — JPG, JPEG, PNG, GIF, BMP, WEBP, and TIFF/TIF, including multi-page TIFFs (each page becomes its own entry in the list).
- **Reorderable pages** — drag and drop, or use the up/down arrows on each item. A numbered badge always shows the final page order.
- **Rotate** — fix sideways or upside-down photos with a one-click rotate button per page; it's applied to the actual image before it goes into the PDF.
- **Compression controls** — an image quality slider and a max-dimension setting, so you can balance sharpness against file size.
- **Page size** — fit each page to A4 (default), US Letter, or the photo's native size with no borders.
- **Runs entirely in your browser** — files are read and processed locally using the Canvas API; nothing is uploaded anywhere.
- **Start over** — one button resets the tool back to its defaults.

## Using it

1. Open `photos-to-pdf.html` in a browser (double-click it, or host it and visit the page).
2. Drop in your images, or click the box to browse for files.
3. Reorder pages as needed and rotate any that are the wrong way round.
4. Adjust quality / max size / page fit if the defaults don't suit.
5. Click **Generate PDF**, then **Download PDF** once it's ready.

## Hosting on GitHub Pages

1. Push `photos-to-pdf.html` to a GitHub repository.
2. In the repo, go to **Settings → Pages**, and set the source to the branch containing the file (e.g. `main`, root folder).
3. GitHub will give you a URL like `https://<username>.github.io/<repo>/photos-to-pdf.html`.

No build step, no dependencies to install — it's a single HTML file.

## Limitations

- **HEIC/HEIF** (the default format on iPhones) isn't supported. Browsers can't decode it natively, and the conversion libraries available are too large/unreliable to bundle. Convert HEIC photos to JPG or PNG first (e.g. via your phone's share/export options), then add them here.
- Very large batches of very high-resolution images will use more memory and take longer to process, since everything happens in the browser tab.

## Built with

This is a single self-contained HTML file with the following open-source libraries inlined (no CDN calls, so it works offline or behind a restrictive firewall):

- [jsPDF](https://github.com/parallax/jsPDF) — PDF generation
- [UTIF.js](https://github.com/photopea/UTIF.js) — TIFF decoding
- [pako](https://github.com/nodeca/pako) — Deflate decompression (used by UTIF.js for some compressed TIFFs)

## Privacy

All processing happens on-device in the browser. Photos are never uploaded, transmitted, or stored anywhere — closing the tab clears everything.
