# Investigation Board

Investigation Board is a browser-based relationship mapping prototype for organizing entities and connections in an investigation. The default interface language is English; use the language button to switch to Sinhala.

## Features
- Interactive link chart powered by vis-network: pan, zoom, drag entities, and fit the chart.
- Automatic ID generation by entity type (for example `PER-0001`, `PHN-0001`, `VEH-0001`).
- Entity types include people, phones, social accounts, vehicles, businesses, employment, email, addresses, devices, websites, crypto wallets, evidence/documents, events, locations, and other.
- Entity-specific icons, names, and unique IDs shown on the chart.
- Right-side details panel for entity properties and connected entities.
- Connections between entities with a dropdown relationship type and optional notes/source.
- Undo/redo for common edits, entity changes, connection changes, and dragging.
- Light/dark theme and English/Sinhala language control.
- Import/export of a complete project as JSON.
- Print/PDF layout: Page 1 is portrait with investigation details, entities, and connections; Page 2 is landscape with the link chart.
- No automatic browser storage. Work remains in memory until exported; export JSON frequently.

## Publish on GitHub Pages
1. Create a GitHub repository.
2. Upload `index.html`, `styles.css`, `app.js`, and `README.md` to the repository root.
3. Open **Settings → Pages**.
4. Select **Deploy from a branch**, then choose `main` and `/(root)` and save.
5. Open the Pages URL shown by GitHub after deployment completes.

## Use
1. Enter the investigation name, reference number, and description in the left panel.
2. Select the **Entities** ribbon tab and add entities.
3. Select two entities and use **Connections → Create Connection**, or create one from the selected entity's details panel.
4. Use **Export Project** to save the investigation to a JSON file. Use **Import Project** to continue editing it later.
5. Use **Report → Print / Save PDF** and choose Save as PDF in the browser print dialog.

## Important limitations
- This is a prototype, not a secure evidence-management platform. It does not provide authentication, encryption at rest, multi-user collaboration, server-side storage, or a formal chain-of-custody audit trail.
- The app does not automatically save data in the browser. Refreshing or closing the page can lose unsaved work. Export a JSON project before leaving.
- The network visualization library and fonts are loaded from external CDNs, so an internet connection is needed when loading the page.
- Use a backend with access controls and audit logging before handling sensitive real-world investigation data.


Print troubleshooting update: The print chart is rendered in a dedicated off-screen layout before the browser print dialog opens, then fitted to the second A4 landscape page.


Print chart fix v2: print network uses explicit pixel dimensions matching A4 landscape rendering, waits for redraw and fit before opening the print dialog, and preserves entity icon colors where the browser print settings allow backgrounds. In Chrome print settings, enable Background graphics for colored icons and chart styling.
