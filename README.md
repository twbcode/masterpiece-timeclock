# Masterpiece Time Clock

Clock in and out, time off, overtime approvals, weekly payroll and time card summaries for Masterpiece Construction Experts.

- The time clock: https://twbcode.github.io/masterpiece-timeclock/
- Owner setup page: https://twbcode.github.io/masterpiece-timeclock/#owner

## How it's set up

Records live in a private Google Apps Script server in the owner's Google account (a Google Sheet only the owner can open). The website keeps no employee data. Passwords and PINs are checked on that server.

- Employees sign in with only a 6-digit PIN, for everything. Managers also have a password, which opens the manager pages. A manager can reset anyone's PIN from Team.
- Only office computers the manager allows can be used, plus each field worker's own phone (from their phone invite). Phone punches save the phone's location; office computers don't.
- Every Thursday at 5 PM Boise time the server emails the week's payroll sheet (spreadsheet + PDF) to the address in Settings → Payroll email. If payroll wasn't done by then, it does it with each person's usual hours for Friday.

## Updating the server code

When `Code.gs.txt` changes: open the Apps Script project, replace all the code with the new `Code.gs.txt`, save, then Deploy → Manage deployments → pencil (Edit) → Version: New version → Deploy. The web app address stays the same. If Google asks for permission again, allow it.

If the Thursday email ever stops, run `setUpThursdayEmail` once from the Apps Script editor.
