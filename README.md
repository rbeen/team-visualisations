# Team Visualisations

Interactive D3 force map showing which team members are working on which stories and epics.

## Quick start
- Serve the files locally so the CSV load and D3 CDN work: `python -m http.server` (or any static file server).
- Open `index.html` in your browser.
- Click **Load Jira CSV** to pick an export (the file stays in your browser). The expected columns match Jira’s default CSV: `Issue Type, Issue key, Issue id, Summary, Assignee, Assignee Id, Reporter, Reporter Id, Priority, Status, Resolution, Created, Updated, Due date, Components, Parent, Parent key, Parent summary, Sprint...`.
- If you don’t have a CSV handy, click **Use sample** to load the bundled dataset.
- Drag nodes to rearrange; hover to highlight related nodes; click empty space to reset focus.

## Data mapping
- Rows with `Issue Type` = Epic become epics.
- All other rows become stories; `Parent key` links stories to their epics (uses `Parent summary` for the epic title if the epic row isn’t present).
- `Assignee` becomes a member node; assignments are only created when an assignee is present.

## Files
- `index.html` — UI, D3 graph, CSV upload and parsing logic.
- `data.json` — sample dataset (also embedded as sample data in the page).
