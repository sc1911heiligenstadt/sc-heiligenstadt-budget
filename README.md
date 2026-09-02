# 💰 Vereinsbudget

Saison-Budget des Vereins: Einnahmen und Ausgaben planen, eingereichte Belege prüfen und zuordnen. Drei Seiten für drei Rollen — Helfer reichen ein, die Geschäftsstelle prüft, der Kassierer plant.

**➡️ [Vereinsbudget öffnen](https://sc1911heiligenstadt.github.io/sc-heiligenstadt-budget/vereinsbudget.html)**

## Seiten

| Seite | Wofür |
|---|---|
| [Beleg-Eingang](https://sc1911heiligenstadt.github.io/sc-heiligenstadt-budget/beleg-eingang.html) | Mobiles Formular für Helfer zum Einreichen von Belegen. |
| [Geschäftsstelle](https://sc1911heiligenstadt.github.io/sc-heiligenstadt-budget/geschaeftsstelle.html) | Eingegangene Belege prüfen, korrigieren und als geprüft markieren — ohne Einblick in die Budgetplanung. |
| [Vereinsbudget](https://sc1911heiligenstadt.github.io/sc-heiligenstadt-budget/vereinsbudget.html) | Budgetübersicht, Einnahmen/Ausgaben und Belegverwaltung für den Kassierer. |

## Wie ein Beleg durchläuft

1. Ein Helfer fotografiert den Beleg am Handy und reicht ihn über **Beleg-Eingang** ein.
2. Die **Geschäftsstelle** prüft ihn, korrigiert bei Bedarf und markiert ihn als geprüft.
3. Im **Vereinsbudget** ordnet der Kassierer ihn dem Haushalt zu.

Jede Rolle sieht dabei nur ihren Schritt: Die Geschäftsstelle bekommt die Belege,
aber keinen Einblick in die Budgetplanung.

## Was die Seiten können

**Vereinsbudget** — Übersicht über Einnahmen, Ausgaben und Saldo der laufenden
Saison. Buchungen werden mit Datum, Betrag, Beschreibung und Kategorie erfasst;
die Kategorien legt der Kassierer selbst an und löscht sie wieder. Die Liste
lässt sich nach Kategorie, Zeitraum und Text filtern. Mehrere Saisons stehen
nebeneinander und werden über eine Auswahl oben umgeschaltet — Datendatei und
Sicherungen enthalten immer alle Saisons. An jede Buchung lassen sich Belege als
Bild oder PDF hängen, die sich in Originalgröße ansehen und wieder entfernen
lassen. Ausgeben lässt sich das Ganze als CSV für Excel oder über die
Druckansicht als PDF, auf Wunsch mit den Belegen als eigene Seiten dahinter.
Jede Buchung merkt sich, wer sie erfasst hat. Das Leeren einer Saison ist
zusätzlich durch ein Passwort abgesichert.

**Speichern und Sichern** — Die Daten liegen in einer Datei am festen
Speicherort in der Vereins-Cloud und werden von dort automatisch geladen und
gespeichert. Zusätzlich legt die Seite lokale Sicherungen der letzten fünf
Stände an; ein verknüpfter Ordner kann als zweiter Sicherungsort dienen. Belege
lassen sich wahlweise im Browser-Speicher oder in einem eigenen Ordner ablegen.

**Beleg-Eingang** — Formular für Helfer, gedacht fürs Handy: Beleg
fotografieren oder als PDF anhängen (mehrere Dateien pro Beleg sind möglich),
Datum, Beschreibung und den eigenen Namen ergänzen, absenden. Der Name bleibt
für die nächste Einreichung gemerkt. Kein Konto und keine Anmeldung nötig — es
genügt ein Zugriffscode vom Verein. Aus dem [Fahrtenbuch](https://sc1911heiligenstadt.github.io/Fahrtenbuch/)
heraus lässt sich das Formular direkt zu einer bestimmten Fahrt aufrufen, damit
Beleg und Fahrt zusammenfinden.

**Geschäftsstelle** — Zeigt den Eingangs-Ordner und die eingegangenen Belege,
jeweils mit Foto oder PDF in Originalgröße. Belege lassen sich als geprüft oder
erledigt markieren oder löschen; erledigte wandern in einen aufklappbaren
Bereich. Im Vereinsbudget übernimmt der Kassierer einen eingegangenen Beleg
anschließend mit einem Klick als Einnahme oder Ausgabe samt Kategorie — oder
verwirft ihn. Beides räumt den Beleg aus dem Eingangs-Ordner.

## Wichtig: nicht die Vereinsverwaltung

Hier geht es um das **Saison-Budget** und die Belege. Mitglieder, Beiträge und
Beitragsläufe stehen in der
[Vereinsverwaltung](https://sc1911heiligenstadt.github.io/vereinsverwaltung/).

## Zugang

Der Zugang läuft nicht über das Vereinskonto, sondern je Seite getrennt — so
sieht die Geschäftsstelle die Belege, ohne Einblick in die Budgetplanung zu
bekommen. Vereinsbudget und Geschäftsstelle sind je mit einem eigenen Passwort
geschützt, der Beleg-Eingang mit einem Zugriffscode für Helfer. Alle drei werden
serverseitig geprüft und stehen nicht im öffentlichen Quellcode.

## Lokal starten

Über den Eintrag `sc-heiligenstadt-budget` in `E:\.claude\launch.json` — der Server läuft dann auf `http://localhost:8772/`.

## Technik

Vanilla JavaScript ohne Build-Schritt — die Dateien werden so ausgeliefert, wie sie im Repo liegen. Veröffentlicht über GitHub Pages. Eigene Cloudflare-Worker in diesem Repo: `worker.js`. Die werden **nicht** über GitHub Pages ausgeliefert, sondern separat bei Cloudflare veröffentlicht.

`worker.js` nimmt die Einreichungen aus dem Beleg-Eingang entgegen und legt sie
serverseitig in der Vereins-Cloud ab. Er begrenzt dabei, was hochgeladen werden
kann: höchstens zehn Dateien je Einreichung, 10 MB je Datei und 25 MB insgesamt,
und nur Bilder oder PDF.

---

Ein Werkzeug des 1. SC 1911 Heiligenstadt. Alle Werkzeuge auf einen Blick: [Tools-Übersicht](https://sc1911heiligenstadt.github.io/ToolsUebersicht/) · Erklärungen im [Toolbox Wiki](https://sc1911heiligenstadt.github.io/Vereinswiki/).
