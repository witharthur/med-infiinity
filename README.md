# Tilda Zero Block Test Assignment

This project is a single-page interactive landing page built with plain HTML, CSS, and JavaScript. It demonstrates three animation mechanics often used in custom Tilda Zero Block work:

- A sticky scroll section with step-by-step state changes.
- A scroll-driven marquee that reacts to page direction and speed.
- Magnetic buttons and layered hover cards for tactile interaction.

## Project Structure

```text
.
+-- favicon.svg
+-- index.html
+-- README.md
`-- style.css
```

## Files

`index.html` contains the page markup and the vanilla JavaScript interactions. The document links Google Fonts, the SVG favicon, and the external stylesheet.

`style.css` contains all visual styling, responsive layout rules, CSS-generated image scenes, hover states, and mobile adaptations. There is no inline page CSS in the HTML.

`favicon.svg` contains the supplied SVG group wrapped in a complete SVG document so browsers can use it as the site favicon.

`README.md` documents setup, structure, behavior, and editing notes.

## How To Run

No build step is required. Open `index.html` directly in a browser.

For a local server, run one of these commands from the project folder:

```bash
python -m http.server 8000
```

```bash
npx serve .
```

Then open:

```text
http://localhost:8000
```

## Page Sections

### Navigation

The fixed navigation links to the three page sections:

- Scroll
- Interact
- Layers

### Hero

The hero introduces the assignment and sets the page style with large display typography, a dark editorial background, and a scroll hint.

### Sticky Scroll Narrative

The first section uses a two-column layout. On desktop, the left column remains sticky while the right panels scroll. JavaScript checks which panel is centered in the viewport and updates the active step plus the progress indicator.

On smaller screens, the layout switches to a stacked flow and disables the desktop sticky behavior for better touch usability.

### Interactive Marquee And Magnetic Buttons

The marquee listens to scroll direction and speed. The track continues moving with easing so it feels responsive instead of snapping.

The magnetic buttons listen to pointer movement. When the cursor enters the magnetic radius, the button moves toward the cursor and smoothly returns to its original position when the cursor leaves.

### Layered Composition

The final section creates overlapping cards with CSS backgrounds and hover states. The hovered card moves forward visually while the other cards soften, giving the section a layered portfolio-style interaction.

## Customization

Update colors and typography in `style.css` under the `:root` variables:

```css
:root {
  --black: #0a0a0a;
  --white: #f5f2ed;
  --cream: #ede9e2;
  --accent: #c8a96e;
  --accent-dark: #9c7d45;
  --muted: #6b6560;
  --border: rgba(200,169,110,0.25);
  --font-display: 'Playfair Display', Georgia, serif;
  --font-body: 'DM Sans', system-ui, sans-serif;
}
```

To change navigation labels or section copy, edit the relevant text in `index.html`.

To tune animations, edit the constants inside the matching JavaScript initializer in `index.html`:

- `initSticky`
- `initMagnetic`
- `initMarquee`
- `initLayered`

## Browser Support

The page uses modern browser features:

- CSS Grid
- CSS custom properties
- `position: sticky`
- `clip-path`
- `requestAnimationFrame`
- `matchMedia`

Use current versions of Chrome, Edge, Firefox, or Safari for the best result.

## Notes

The code has been cleaned so styling is separated from markup, page comments are removed, and the favicon is loaded from a standalone SVG file.
