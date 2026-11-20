# Dashboard Excel per il monitoraggio del budget e l'analisi delle spese

## Sommario

Prendere decisioni finanziarie efficaci richiede la stessa disciplina necessaria per una buona gestione operativa: definire gli indicatori KPI, monitorarli con costanza e individuare i principali fattori che determinano i costi. Questo progetto applica tale approccio alla gestione delle finanze personali. Ho realizzato una cartella di lavoro Excel composta da più fogli, progettata per un ipotetico nucleo familiare, che registra le transazioni quotidiane, le consolida in riepiloghi mensili e annuali e le trasforma in una dashboard interattiva attraverso tabelle pivot, filtri slicer, grafici dinamici e menu a discesa per la ricerca dei dati. La cartella di lavoro comprende 6 anni di storico delle entrate e delle uscite (2019-2024), una panoramica mensile del 2019, un registro dettagliato delle transazioni e un budget separato dedicato ad un viaggio.

## Problema

Una persona desidera iniziare a gestire il budget in modo proattivo. Le spese sono distribuite tra numerose piccole transazioni, rendendo difficile capire dove finiscono effettivamente i soldi, se le uscite sono in aumento o in diminuzione e se gli obiettivi di risparmio vengono raggiunti. Ho ipotizzato che l'utente voglia comprendere:
- Dove vengono spesi i soldi e quali categorie incidono maggiormente sulla spesa totale?
- Come sono cambiate le entrate e le uscite nel corso degli anni?
- Il nucleo familiare riesce a risparmiare con costanza? L'avanzo di bilancio è in crescita o in diminuzione?
- Quali sono i mesi più e meno costosi?
- Come monitorare un evento, come un viaggio, senza alterare l'analisi del budget ordinario?

## Struttura della Cartella di lavoro

| Foglio | Scopo |
|---|---|
| **Monthly Tracker** | Registro delle transazioni (data, voce, importo, categoria) relative a entrate e uscite, con saldo mensile, tabella pivot per categoria e grafico collegato |
| **Year Expenses at a glance** | Totale delle spese mensili del 2019, con totale annuale, visualizzato attraverso un grafico navigabile con controlli di scorrimento e zoom |
| **Yearly income** | Entrate suddivise per tipologia (Stipendio, Entrate passive, Altro) dal 2019 al 2024, con ricerca dinamica dell'anno |
| **Yearly expenses** | Spese suddivise in 11 categorie dal 2019 al 2024, con ricerca dinamica per categoria e anno |
| **Trip expenses** | Budget dettagliato di un viaggio con ripartizione delle spese per metodo di pagamento |
| **List** | Elenco principale delle categorie, utilizzato per alimentare i menu a discesa e mantenere uniformità nella classificazione delle spese |

## Metodologia

```
Inserimento dei dati delle transazioni
        ↓
Categorie standardizzate (menu a discesa)
        ↓
Consolidamento mensile e annuale
        ↓
Tabelle pivot, filtri e grafici dinamici
        ↓
Analisi dei risultati e raccomandazioni
```

**Struttura e Validazione dei Dati**
- Ho definito un elenco principale di 11 categorie di spesa e utilizzato la convalida dei dati con menu a discesa, in modo da classificare ogni transazione in maniera coerente.
- Ho separato entrate, uscite e spese relative ad un singolo viaggio, così da poterle analizzare individualmente.
- Ho utilizzato le formule `SUM` per calcolare i totali e i saldi di ciascun periodo in ogni foglio.
- Ho verificato che la somma dei totali mensili nel foglio di riepilogo annuale corrispondesse al totale delle spese del 2019 (34.483 €) e che il registro delle transazioni di Febbraio coincidesse con il relativo totale mensile.

**Analisi e reportistica**
- Ho utilizzato le tabelle pivot per riepilogare le spese per categoria e applicato filtri interattivi (slicer) per facilitarne l'analisi.
- Ho implementato formule di ricerca `INDEX` / `MATCH` e `CHOOSE` / `MATCH`, collegate a menu a discesa, per ottenere immediatamente qualsiasi combinazione di categoria e anno.
- Ho calcolato gli indicatori KPI relativi a entrate, uscite, saldo e risparmio per ciascun periodo.
- Ho confrontato il peso delle diverse categorie e la loro evoluzione nel corso dei 6 anni analizzati.

**Progettazione della dashboard**
- Ho creato grafici dinamici basati su intervalli denominati, con controlli di scorrimento e zoom per esplorare la panoramica annuale.
- Ho aggiunto un grafico pivot che si aggiorna quando vengono inserite nuove transazioni e la tabella pivot viene aggiornata.
- Ho integrato una ripartizione delle spese per metodo di pagamento nel budget del viaggio.

## Risultati

*I dati riportati di seguito provengono dalla cartella di lavoro Excel. Tutti gli importi sono espressi in euro (€).*

**Dove vengono spesi i soldi?**

Le spese sono concentrate in poche categorie principali. Nel 2024, le Utenze (affitto, assicurazioni e bollette) rappresentavano il 40,7% delle spese totali, seguite da Trasporti (16,9%), Spesa alimentare (10,4%) e Vacanze (10,1%). Queste quattro categorie rappresentano complessivamente circa il 78% del budget. Le categorie di spesa discrezionale, come Ristoranti, Shopping e Tempo libero, costituiscono invece meno del 7% del totale.

**Come si sono evolute entrate e uscite?**

Entrambe risultano molto stabili. Le entrate totali sono passate da 39.536 € nel 2019 a 39.667 € nel 2024, con un incremento dello 0,3%. Lo stipendio ha rappresentato costantemente circa il 92% delle entrate complessive. Le spese totali sono passate da 34.483 € a 34.215 €, registrando una diminuzione dello 0,8%. La struttura dei costi è in gran parte fissa, quindi il margine di risparmio ottenibile attraverso piccoli aggiustamenti è limitato.

**Il nucleo familiare riesce a risparmiare?**

L'avanzo annuale (entrate meno tutte le uscite, inclusi i contributi destinati al risparmio) è variato tra il 10,9% delle entrate nel 2021 e il 13,7% nel 2024. Tuttavia, la categoria specifica dedicata ai Risparmi è diminuita da 2.678 € nel 2021 a 2.006 € nel 2024 (-25%), mentre le spese per Vacanze sono aumentate del 12,9% tra il 2019 e il 2024 (da 3.064 € a 3.459 €). Una parte del miglioramento dell'avanzo di bilancio è quindi rappresentata da liquidità non ancora destinata a uno scopo preciso, piuttosto che da somme effettivamente accantonate.

**Quali sono i mesi più costosi?**

Nel riepilogo mensile del 2019, la spesa media si attesta intorno a 2.874 €. Luglio è il mese con le spese più elevate (3.546 €, il 23% sopra la media), seguito da Dicembre (3.214 €) e Marzo (3.087 €). Giugno è invece il mese meno costoso, con 2.539 €. Il picco di Luglio coincide con le spese legate ai viaggi estivi, mentre quello di Dicembre è associato alle festività. Si tratta quindi di costi prevedibili che dovrebbero essere pianificati in anticipo, anziché essere assorbiti dal saldo mensile.


**Come si presenta un mese tipo?**

Nel registro delle transazioni di Febbraio, a fronte di entrate pari a 3.100 € e uscite pari a 2.768 €, il saldo risultante è di 332 €, equivalente al 10,7% delle entrate. Le Utenze rappresentano da sole il 48% delle spese del mese. Inoltre, il totale di 2.768 € registrato a Febbraio coincide con il valore riportato nel riepilogo annuale delle spese mensili.

**Come monitorare un evento specifico?**

Il budget del viaggio ammonta complessivamente a 767 €. Volo e hotel rappresentano il 58% della spesa totale. Il 75% delle spese è stato effettuato tramite carta di debito, mentre la parte restante è stata suddivisa tra Apple Pay e contanti. Monitorare queste spese in un foglio separato permette di evitare che costi eccezionali alterino l'analisi del budget mensile ordinario.


## Suggerimenti

- **Concentrarsi prima sui costi fissi:** Utenze e Trasporti rappresentano circa il 58% delle spese. Una revisione dei contratti assicurativi, delle utenze domestiche e dei trasporti avrebbe quindi un impatto maggiore rispetto al taglio di piccoli acquisti discrezionali.
- **Automatizzare il risparmio:** i contributi destinati ai risparmi sono diminuiti nonostante la crescita dell'avanzo di bilancio. Impostare un trasferimento automatico all'inizio di ogni mese, calcolato come percentuale delle entrate, permetterebbe di tutelare l'obiettivo di risparmio.
- **Pianificare la stagionalità delle spese:** Luglio e Dicembre registrano spese superiori del 12-23% rispetto alla media mensile. Accantonare ogni mese una somma fissa per affrontare questi periodi eviterebbe di intaccare il saldo disponibile.
- **Pianificare le vacanze come categoria autonoma:** le Vacanze rappresentano la principale categoria di spesa in crescita e meritano quindi un obiettivo di budget annuale dedicato.
- **Mantenere un monitoraggio regolare:** registrare le transazioni ogni settimana e aggiornare le tabelle pivot consente di mantenere la dashboard affidabile come strumento di supporto alle decisioni.

## Competenze

**Analisi dei dati**
- Definizione e monitoraggio degli indicatori KPI
- Analisi dei principali fattori di costo
- Analisi dei trend e degli scostamenti
- Analisi della stagionalità
- Elaborazione di insight e formulazione di suggerimenti

**Microsoft Excel**
- Tabelle pivot e grafici pivot
- Filtri interattivi (Slicer)
- Intervalli denominati dinamici e grafici dinamici
- Controlli modulari (scorrimento e zoom)
- Convalida dei dati e menu a discesa
- Formule INDEX / MATCH, CHOOSE, SUM e formule di ricerca
- Formattazione condizionale
- Progettazione di dashboard e visualizzazione dei dati

## Dati

I dati sono puramente illustrativi e sono stati creati esclusivamente per finalità di portfolio. Non contengono informazioni finanziarie o personali reali relative ad alcun individuo. Sono stati realizzati per simulare un budget familiare realistico, comprendente bollette ricorrenti, acquisti quotidiani e un viaggio. L'intera struttura, le formule, le tabelle pivot, i grafici, le analisi e i suggerimenti sono stati progettati e realizzati autonomamente da me.

## Cartelle e File

- Budget_Tracker.xlsx: Cartella di lavoro completa, contenente tutti i fogli, le tabelle pivot e i grafici.
- Screenshots: Anteprime di ciascun foglio della dashboard.
