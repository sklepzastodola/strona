# Maisingerhof — Strona internetowa

Gotowa strona w HTML/CSS dla Maisingerhof, po polsku, 5 podstron.

---

## Struktura plików

```
maisingerhof/
├── index.html       ← strona główna
├── sklep.html       ← sklep gospodarczy
├── automat.html     ← automat do mleka
├── o-nas.html       ← o nas
├── kontakt.html     ← kontakt
├── style.css        ← wspólne style
└── img/             ← tu wrzuć swoje zdjęcia
```

---

## Zdjęcia — co podmienić

Wrzuć własne zdjęcia do folderu `img/` pod tymi nazwami:

| Plik              | Gdzie używany                        |
|-------------------|--------------------------------------|
| hero.jpg          | Duże tło na stronie głównej          |
| mleko.jpg         | Karta "Surowe mleko"                 |
| sklep.jpg         | Karta "Sklep gospodarczy"            |
| pole.jpg          | Karta "Zrównoważona uprawa" + O nas  |
| automat.jpg       | Strona automatu do mleka             |
| sklep-wnetrze.jpg | Wnętrze sklepu (podstrona Sklep)     |
| nabiał.jpg        | Karta nabiał                         |
| warzywa.jpg       | Karta warzywa                        |
| przetwory.jpg     | Karta przetwory                      |
| jajka.jpg         | Karta jajka i wędliny                |
| zboze.jpg         | Karta zboża                          |
| inne.jpg          | Karta dla zwierząt                   |
| historia.jpg      | Sekcja historia (O nas)              |
| krowy.jpg         | Sekcja hodowla (O nas)               |

Jeśli jakiegoś zdjęcia nie masz — nic się nie stanie, pojawi się szare tło.

---

## Jak wdrożyć na Vercel

### Krok 1 — GitHub
1. Wejdź na github.com → zaloguj się lub załóż konto
2. Kliknij "New repository" → nazwij np. `maisingerhof`
3. Ustaw jako **Public** → kliknij "Create repository"
4. Wgraj wszystkie pliki (przeciągnij na stronę repozytorium)

### Krok 2 — Vercel
1. Wejdź na vercel.com → zaloguj się przez GitHub
2. Kliknij "Add New Project"
3. Wybierz swoje repozytorium `maisingerhof`
4. Framework preset: **Other** (zwykły HTML, bez frameworka)
5. Kliknij "Deploy" — strona gotowa w ~30 sekund!

### Krok 3 — Własna domena z home.pl
1. W Vercel: Settings → Domains → wpisz swoją domenę → Add
2. Vercel pokaże Ci rekordy DNS do dodania
3. Zaloguj się do home.pl → panel DNS domeny → dodaj:
   - Rekord **A**: `@` → adres IP podany przez Vercel
   - Rekord **CNAME**: `www` → adres podany przez Vercel
4. Poczekaj do 24h na propagację DNS

---

## Kolory strony (możesz zmienić w style.css)

```css
--zielony:     #3a5a2e   ← główny kolor
--brazowy:     #8b6914   ← akcenty
--kremowy:     #f7f3ec   ← tło strony
--ciemny:      #1e1e1e   ← tekst
```

---

## Formularz kontaktowy

Obecny formularz pokazuje tylko potwierdzenie po kliknięciu "Wyślij".
Aby naprawdę odbierać wiadomości, zarejestruj się na **formspree.io** (darmowe):
1. Załóż konto → utwórz nowy formularz
2. Dostaniesz adres np. `https://formspree.io/f/xyzabc`
3. W `kontakt.html` zmień:
   ```html
   <form class="formularz" action="https://formspree.io/f/TWOJ_KOD" method="POST">
   ```
   i usuń `onsubmit="wyslijFormularz(event)"` oraz cały `<script>` z tą funkcją.
