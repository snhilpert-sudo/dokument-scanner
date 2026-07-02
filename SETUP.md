# Dokument Scanner — Einrichtung

## Dateien
- `index.html` — Haupt-App
- `manifest.json` — PWA-Manifest
- `sw.js` — Service Worker (Offline-Fähigkeit)
- `icon-192.png` / `icon-512.png` — App-Icons (selbst erstellen oder generieren lassen)

## GitHub Pages Deployment (wie Kassenbuch)

1. Neues Repo erstellen: z.B. `dokument-scanner`
2. Alle Dateien hochladen (inkl. Icons)
3. Settings → Pages → Branch: main, Folder: root
4. App läuft auf: `https://snhilpert-sudo.github.io/dokument-scanner/`

**Wichtig:** In `sw.js` und `manifest.json` den BASE-Pfad `/dokument-scanner` anpassen falls Repo anders heisst.

## Einstellungen in der App (⚙️)

### 1. Gemini API-Key
- Derselbe Key wie in der Kassenbuch-App
- Einstellungen → Gemini API-Key eintragen

### 2. OneDrive-Ordner
- Pfad innerhalb von OneDrive, z.B. `Dokumente/Scans`
- Ordner muss nicht vorher erstellt werden — wird automatisch angelegt

### 3. Microsoft Client-ID (Azure App)
- Einmalige Einrichtung nötig für OneDrive-Zugriff
- Anleitung: https://portal.azure.com → App-Registrierungen → Neue Registrierung
  - Name: DokumentScanner
  - Kontotypen: Konten in beliebigen Organisationsverzeichnissen und persönliche Microsoft-Konten
  - Redirect-URI: Web → https://snhilpert-sudo.github.io/dokument-scanner/
  - Nach Erstellung: Application (client) ID kopieren
- In App-Einstellungen eintragen

## Nutzung

1. **+ Seite** → Kamera öffnet sich (oder Galerie)
2. Mehrere Seiten möglich (werden zu einem PDF zusammengeführt)
3. **✨ KI-Analyse** → Datum, Absender und Beschreibung werden automatisch erkannt
4. Felder bei Bedarf manuell korrigieren
5. **☁ OneDrive** → PDF wird direkt gespeichert
   - Beim ersten Mal: Microsoft-Login im Popup
   - Dateiname: `260702_Mobiliar_Betriebsversicherung.pdf`

## Icons erstellen
Einfachste Lösung — ein 512×512 PNG generieren lassen und auf 192×192 verkleinern.
Oder temporär Platzhalter-Icons aus dem Kassenbuch-Repo kopieren.
