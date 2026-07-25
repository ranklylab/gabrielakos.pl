# AGENTS.md — gabrielakos.pl

## Charakter projektu

Repozytorium zawiera fragmenty HTML i CSS przeznaczone do osadzania w WordPressie.

Każda podstrona jest samodzielnym fragmentem zawierającym:

1. blok `<style>`,
2. właściwą zawartość w `<main class="gk-block ...">`.

Nie dodawaj pełnego dokumentu HTML (`doctype`, `html`, `head`, `body`), chyba że zadanie wyraźnie tego wymaga.

## Wersje językowe

Strona zawsze wspiera język polski i francuski.

Dla każdej podstrony muszą istnieć dwa pliki:

- polski: `<slug>.html`,
- francuski: `<slug>_fr.html`.

Przykłady:

- `o-mnie.html` → `/o-mnie`,
- `o-mnie_fr.html` → `/o-mnie/fr`,
- `uslugi.html` → `/uslugi`,
- `uslugi_fr.html` → `/uslugi/fr`.

Jeżeli tworzysz lub istotnie zmieniasz podstronę:

- zaktualizuj obie wersje językowe,
- zachowaj tę samą strukturę sekcji, klas i komponentów,
- CSS polskiego i francuskiego odpowiednika powinien być identyczny,
- przetłumacz także teksty alternatywne, etykiety ARIA, przyciski i tematy wiadomości e-mail,
- lokalizuj linki wewnętrzne, np. `/kontakt` oraz `/kontakt/fr`.

Francuska wersja powinna być naturalnym tłumaczeniem, a nie tłumaczeniem słowo w słowo. Nie zmieniaj przy tym faktów ani zakresu usług.

Sekcje strony głównej są podzielone na dwa katalogi:

- `main/` — polska wersja strony głównej,
- `main_fr/` — francuska wersja strony głównej.

Odpowiadające sobie partiale w `main/` i `main_fr/` muszą mieć takie same nazwy, strukturę oraz identyczny CSS. Zmieniając sekcję strony głównej, zawsze zaktualizuj jej odpowiednik w drugim języku.

## Nawigacja i footer

Wspólne partiale znajdują się w `shared/`:

- `shared/navbar.html` — wersja polska,
- `shared/navbar_fr.html` — wersja francuska,
- `shared/footer.html` — wersja polska,
- `shared/footer_fr.html` — wersja francuska.

Polska nawigacja prowadzi do:

- `/o-mnie`,
- `/uslugi`,
- `/wycena`,
- `/kontakt`.

Francuska nawigacja prowadzi do:

- `/o-mnie/fr`,
- `/uslugi/fr`,
- `/wycena/fr`,
- `/kontakt/fr`.

Przełącznik języka powinien prowadzić do odpowiednika aktualnej strony:

- `/` ↔ `/fr`,
- `/uslugi` ↔ `/uslugi/fr`,
- `/o-mnie` ↔ `/o-mnie/fr`.

Jeżeli nowa strona ma znaleźć się w nawigacji lub footerze, zaktualizuj oba języki.

## Design system

Istniejący wygląd jest zatwierdzony i stanowi źródło prawdy.

Nie wprowadzaj bez wyraźnej zgody:

- nowych kolorów,
- nowych fontów,
- nowych rozmiarów typografii,
- nowych odstępów i wartości `gap`,
- nowych szerokości kontenera,
- nowych cieni,
- nowych breakpointów,
- nowych stylów przycisków,
- zewnętrznych bibliotek CSS,
- importów Google Fonts.

Nie używaj `@import` do ładowania fontów.

Podstawowe fonty są już wskazane przez istniejący CSS:

- tekst: `"Karla", system-ui, sans-serif`,
- nagłówki: `"Cormorant Garamond", Georgia, serif`.

Fonty są dostarczane przez WordPress lub motyw. Zachowaj istniejące fallbacki.

Używaj wyłącznie istniejących zmiennych:

- `--gk-paper`,
- `--gk-paper-light`,
- `--gk-ink`,
- `--gk-soft`,
- `--gk-line`,
- `--gk-accent`,
- `--gk-accent-dark`,
- `--gk-accent-soft`,
- `--gk-white`,
- `--gk-shadow`.

Nowe układy buduj przez ponowne użycie istniejących komponentów, klas, wartości i wzorców z najbliższej tematycznie podstrony.

## Źródła wzorców

Przed zmianą sprawdź istniejące podstrony:

- `o-mnie.html` — sekcje narracyjne, statystyki, karty i CTA,
- `uslugi.html` — rozbudowane listy usług,
- `wycena.html` — stawki i karty informacyjne,
- `kontakt.html` — dane kontaktowe i instrukcje,
- pliki `_fr.html` — odpowiedniki francuskie.

Nie kopiuj skróconego zestawu stylów. Polska i francuska wersja konkretnej podstrony powinny mieć identyczny blok CSS.

## Treść

Nie wymyślaj:

- kwalifikacji,
- zakresu usług,
- terminów realizacji,
- cen,
- nazw instytucji,
- procedur prawnych lub administracyjnych.

Rozbudowuj treść wyłącznie na podstawie informacji dostarczonych przez użytkownika lub już obecnych w repozytorium.

## Walidacja

Po każdej zmianie sprawdź:

- poprawne domknięcie HTML,
- zbalansowane nawiasy CSS,
- brak zduplikowanych identyfikatorów,
- brak importów Google Fonts,
- poprawność linków polskich i francuskich,
- identyczność CSS między wersjami językowymi,
- zgodność struktury sekcji między wersjami językowymi,
- responsywność dla breakpointów `980px` i `620px`,
- wynik `git diff --check`.

W podsumowaniu wymień zmienione pliki oraz wykonane kontrole.
