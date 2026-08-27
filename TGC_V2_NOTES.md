# TGC Field Register v2 — What's New & How to Deploy

## Deploying

Replace `index.html` in the `tgc-field-register` GitHub repository with the new file (Add file → Upload files → drag it in → Commit). That's the whole deployment: it keeps the existing Google Apps Script backend URL, so all current data — sessions, roster, registrations, bag counts, the admin PIN — carries straight over. No backend changes needed. The file is bigger than before (~1.6 MB) because all 24 property maps and the club crest are embedded in it; it loads once and the browser caches it.

This build is based on the repo's **current** live version (24 Aug), so Kurt's recent additions — hourly session weather, the "add a shooter who was missed" tool, the reworked Results layout — are all preserved.

## What's new

**1. Property maps (24 embedded).** Tap-to-view stand-layout maps on the Register tab (a "Property maps" card), the Draw tab (buttons under the session header, scoped to that weekend's available properties), and the Results tab. Maps open full-screen; very wide maps display tall and scroll sideways. They work offline in the field. Includes the **updated 12-stand Arcadia map** and the **updated Schawfield–Gaza Side map** (filed under GAZA), plus the full 2025 map book: Bidham, Dog, Dundee Pool, Garden Piece, Glidden, Greenside, New Greenside, Hyde Hall, Kent, Kirkpatrick, New Kirkpatrick, Mango Walk, Mary Ticker, Midlands, Mozambique, New Court, Pembroke, Power Line, Roslyn Castle, Roslyn Pond, Schawfield, Smith & Bell.

**2. TGC crest** in the header (crossed shotguns on a cream badge).

**3. Stats tab rebuilt as a Stats Explorer.**
- Opens on the **most recent weekend shot** by default; "All-time view" and "Latest weekend" buttons switch perspectives instantly.
- Filter by **Year → Weekend → Property → Stand → Shooter** (each filter's options adapt to the ones above it).
- The charts adapt to the selection: birds **by year** (all-time), **by weekend** (year view), **by session** (weekend view); **top properties**, or **stands within a property** once one is chosen (with its map one tap away); **top shooters**, or a full **session-by-session log** when a single shooter is selected. Summary tiles show birds / shooters / sessions, best single bag, and the species breakdown.
- **Export filtered CSV** downloads exactly what the current filters show.
- The full **2020–2025 history** is built in: 3,599 shooter-session records and 34,573 birds imported from the combined Cumulative Stats workbook. Results logged in the app are layered on top automatically — where the same shooter/session exists in both, the app's logged bag wins.

## Caveats & follow-ups

- **2024 bag counts are estimated.** The 2024 draws and stand assignments exist in the workbook (426 records), but no bird counts were recorded against them. Each 2024 entry therefore carries the **historical average for its property & stand** (387 records; 39 fell back to the property average), split by that stand's usual species mix — about 4,736 birds in total. These rows are marked with **~** and a footnote wherever they appear, exported as "Estimated (2024 stand avg)" in the CSV, and excluded from "best single bag" callouts. If the real 2024 counts ever surface, send them and they'll replace the estimates.
- **Greenside naming:** the map book has "GREENSIDE" and "OLD GREENSIDE"; the app has "GREENSIDE" and "NEW GREENSIDE". I mapped map-book *Old Greenside* → app **GREENSIDE** and map-book *Greenside* → app **NEW GREENSIDE**. If that's backwards, say so — it's a two-line swap.
- **Pea Dove / Paloma:** the workbook's "Pea Dove" column is treated as the app's PALOMA species so the totals unify.
- **Upgraded maps:** Pembroke now uses the new colour map (6 stands) and Midlands the new dedicated 5-stand map, replacing the map-book versions. **Still unmapped:** Barrett Hall, Bell, Bryan Castle, Gore Hill, McKenzie Lands, Murray Lands, Orange Grove, Park Pen, Scotts Lands, Thatch Walk, White Bay — buttons simply don't appear for those; send images any time.
- Property names on map buttons match the names stored in the app's database — if a property is ever renamed in Setup, its map key needs the same rename.
