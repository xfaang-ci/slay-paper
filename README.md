# slay-paper 📄

**Uniwersalna formatka + schemat pracy Slayer** — jedno źródło prawdy dla dokumentów.
Od dialektyki (jak myślimy) do empirycznego raportu LaTeX → PDF (jak to wydajemy).

## Co tu jest
```
slay-paper/
├── szablon-dokumentu/           ← KOPIUJ to do projektu jako paper/
│   ├── main.tex                 ← wrapper (wiring; nie pisz tu treści)
│   ├── formatka/slayer.sty      ← WYGLĄD (podmienialny bez ruszania treści)
│   └── tresc/
│       ├── 00-strona-tytulowa.tex   ← tytuł + PODPIS autorem + wykres z podpisem
│       └── 10-tresc.tex             ← body: tylko sekcje/akapity (to piszesz)
├── .github/workflows/latex.yml  ← CI: .tex → PDF (artefakt)
└── docs/
    ├── INSTRUKCJA-Dokumenty-Dialektyczne.md   ← schemat pracy (dialektyka + ewaluacja)
    └── Runbook-LaTeX-CI.md                    ← jak ustawić LaTeX→PDF w CI
```

## Schemat pracy (skrót)
1. **Warsztat** (Obsidian / `docs/`): Cel → Teza ↔ Antyteza → Synteza, a nad wszystkim ⭐**Ewaluacja** („co się NAPRAWDĘ dzieje", żadnej tezy bez dowodu).
2. **Finał** dojrzałej nitki: **dokument LaTeX → PDF** (ten szablon). Obsidian = warsztat; PDF = artefakt-produkt.

## Twarde reguły formatki
- **Matematyka zawsze w LaTeX, nigdy unicode** — `$\perp$` nie `⟂`, `$\Delta$` nie `Δ`, `$\le$` nie `≤`.
- **Formatka ⟂ treść** — `tresc/*.tex` to czysty content; zmiana wyglądu = jeden plik `formatka/slayer.sty`.
- **Wykres + podpis na pierwszej stronie** (empiria od razu widoczna) · **podpis autorem**.

## Jak użyć w nowym projekcie
1. Skopiuj `szablon-dokumentu/` → `<projekt>/paper/`.
2. Pisz w `paper/tresc/`, zostaw `paper/formatka/`.
3. Dodaj workflow CI (jak `.github/workflows/latex.yml`) → push buduje PDF jako artefakt.

## Kompilacja lokalnie
`cd szablon-dokumentu && latexmk -pdf main.tex` (lub `pdflatex main.tex` ×2).
