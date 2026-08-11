# Socialtee — website package

Alles wat nodig is om de site te hosten.

## Inhoud van deze zip

```
index.html          → de volledige website (start hier)
images/              → alle foto's + logo, gebruikt door index.html
robots.txt           → instructies voor zoekmachines
sitemap.xml           → sitemap voor Google
```

## Hosten — belangrijk

`index.html` verwijst naar afbeeldingen via relatieve paden (bv. `images/cyclelink-hero-bw.jpg`).
**De `images`-map moet dus altijd in dezelfde map staan als `index.html`, anders tonen er geen foto's.**

Zet op de webserver (of hostingdienst zoals Combell, Vimexx, Netlify, Vercel, GitHub Pages, …):
- `index.html`
- `images/` (volledige map, met alle bestanden erin)
- `robots.txt`
- `sitemap.xml`

allemaal in de **hoofdmap (root)** van het domein.

## Voor je live gaat — nog aan te passen

1. **Domeinnaam.** Ik heb overal `https://www.socialtee.be/` gebruikt als voorlopige URL (in de `<head>` van `index.html`, in `sitemap.xml` en in `robots.txt`). Zoek-en-vervang dit naar het echte domein zodra dat vaststaat.
   - In `index.html`: zoek naar `socialtee.be` (komt een paar keer voor: canonical link, Open Graph, Twitter Card, structured data/JSON-LD).
   - In `sitemap.xml`: alle `<loc>`-tags.
   - In `robots.txt`: de `Sitemap:`-regel.

2. **Google Analytics.** Al ingesteld met het echte Measurement ID (`G-DRJGT9CTDX`), gekoppeld aan een cookiebanner — bezoekers moeten expliciet toestemmen voor er getrackt wordt. Niets meer aan te passen, tenzij het ID ooit wijzigt (zoek naar `GA_MEASUREMENT_ID` in `index.html`).

3. **Contactformulier & pre-orders.** Deze werken via `mailto:` — klikken op "Verstuur bericht" of "Pre-order" opent het eigen e-mailprogramma van de bezoeker, gericht aan `hello@socialtee.be`, met onderwerp en tekst al ingevuld. Er is dus **geen backend/server nodig**, maar het werkt niet voor bezoekers zonder ingesteld e-mailprogramma op hun toestel (bv. sommige mobiele browsers). Wil je een "echt" formulier met eigen backend (bv. via Formspree), laat het weten.

4. **Productfoto's apparel.** De 4 kledingstukken (Short Sleeve, Bib Short, Thermal Long, Sprintsuit) hebben nog geen echte productfoto — dit zijn nu lege plaatshouders met enkel een naam-label. Zodra er productfoto's zijn, kunnen die toegevoegd worden.

5. **Overige portfolio-cases.** De cases "Sallt", "MVG" en "Serge" (in het portfolio-overzicht) bevatten nog de originele demo-foto's uit de eerste versie van de site (nu terug te vinden als `images/legacy-XX.jpg`) — deze zijn nooit besproken/aangepast in dit traject.

## Wat al in orde is

- **SEO**: title, meta description, Open Graph, Twitter Card, canonical URL en structured data (JSON-LD) staan klaar.
- **Privacy & cookies**-pagina (`#privacy`) en **Algemene voorwaarden**-pagina (`#voorwaarden`), beide bereikbaar via de footer.
- **Cookiebanner** met opt-in voor Google Analytics.
- **404-pagina** bij een onbekende link.
- **Skip-to-content link** voor toetsenbordgebruikers.
- Alle foto's hebben beschrijvende `alt`-tekst en laden lazy (behalve de hero-foto op de homepage).

## Techniek in het kort

Eén enkele HTML-pagina (single-page app) die client-side van "pagina" wisselt via de `#hash` in de URL (bv. `jouwsite.be/#portfolio`). Er is geen server-side logica, database of build-proces nodig — het is pure HTML/CSS/JavaScript en kan op eender welke statische hosting geplaatst worden.
