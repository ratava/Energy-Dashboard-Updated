# ⚡ "Alive" Energy Dashboard - Home Assistant

![Preview](https://raw.githubusercontent.com/Giorgio866/Energy-dashboard/refs/heads/main/80451.jpg)

---
## 🇺🇸 ENGLISH

This is an advanced **Custom Card** for Home Assistant that turns your PV system data into a realistic visual experience (Augmented Reality style).
Instead of using abstract graphs, the dashboard is built on top of a **real photo of the installation** and overlays SVG/CSS animated energy flows that react in real-time to current power usage.

### ✨ Key Features
* **Real Background:** The background is loaded automatically from GitHub (you don't need to upload local files).
* **Dynamic Speed:** The "laser" flows accelerate based on real-time Watts (more power = faster animation).
* **Dual String (MPPT):** Separate visualization for String 1 (Cyan, Front) and String 2 (Blue, Back) with 3D perspective.
* **Liquid Battery:** The battery fill level rises and falls with a fluid "wave" effect based on the charge percentage.
* **Dual Battery Support:** Supports 1 or 2 batteries (automatically calculates percentage average and Watts sum).
* **Smart Colors:** Cyan/Blue (Solar/Battery), Red (Grid Import), White (Standby).
* **Automatic Unit Conversion:** Automatically detects and converts kW to W for all power sensors.
* **Flexible Display Units:** Choose to display power values in Watts (W) or Kilowatts (kW).
* **Optional Sensors:** Support for optional PV2, Battery 2, and Car charging sensors (leave empty if not used).
* **Customizable Labels:** Configurable daily production label for multi-language support.
* **Dashboard Grid Control:** Specify how many columns the card should span (1-12).

### ⚙️ Requirements
Before starting, make sure you have:
1.  **Home Assistant** running.
2.  **[HACS](https://hacs.xyz/)** installed.
3.  The frontend integration **`custom:button-card`** (Search for "button-card" in HACS > Frontend and install it).

### 🚀 Installation Guide
1.  Open the [`energy_card.yaml`](energy_card.yaml) file present in this repository.
2.  Click on the "Copy raw file" icon at the top right (or select all text and copy).
3.  Go to your Home Assistant dashboard.
4.  Click the pencil icon at the top right (**Edit Dashboard**).
5.  Click on **"Add Card"** at the bottom right.
6.  Scroll to the bottom and select the **Manual** card.
7.  Delete all default code and **paste the code you copied**.

### 🔧 Configuration (Important!)
After pasting the code, scroll to the top of the editor. You will find a section called `variables`.
You must replace the example names with the **names of your real sensors**.

```yaml
variables:
  # --- SOLAR ---
  sensor_pv1: "sensor.solar_production_string_1" # Can be combined PV value or individual string
  sensor_pv2: "sensor.solar_production_string_2" # Leave empty "" if using combined value in sensor_pv1
  sensor_daily: "sensor.daily_production"

  # --- BATTERY ---
  sensor_bat1_soc: "sensor.battery_percent"      # Can be combined battery SOC or individual battery
  sensor_bat1_power: "sensor.battery_power"      # Can be combined battery power or individual battery
  
  # If you have only one battery, leave the quotes empty for the second one:
  sensor_bat2_soc: ""  # Leave empty "" if using combined value in sensor_bat1_soc
  sensor_bat2_power: ""  # Leave empty "" if using combined value in sensor_bat1_power
  
  # --- HOME & GRID ---
  sensor_home_load: "sensor.home_consumption"
  sensor_grid_power: "sensor.grid_power"
  
  # --- CAR (Optional) ---
  sensor_car_power: ""  # Leave empty "" to hide car charging display
  
  # --- DISPLAY OPTIONS ---
  display_unit: "kW"  # Set to "W" for Watts or "kW" for Kilowatts
  card_columns: 2  # Number of columns the card should span (1-12)
  daily_production_label: "DAILY PRODUCTION"  # Customize the label text
  
  # --- BACKGROUND IMAGE ---
  bg_image: "https://your-image-url.jpg"  # URL to your custom background image
```

**Important Notes:**
- All power sensors automatically handle both W and kW units
- Leave sensor_pv2 empty if you have a single combined PV sensor
- Leave sensor_bat2_soc and sensor_bat2_power empty if you have a single battery
- Leave sensor_car_power empty if you don't want to display car charging
- The card updates automatically whenever any configured sensor changes state



## 🇮🇹 ITALIANO

Questa è una **Custom Card** avanzata per Home Assistant che trasforma i dati del tuo impianto fotovoltaico in un'esperienza visiva realistica (stile Realtà Aumentata).
Invece di usare grafici astratti, la dashboard è costruita sopra una **foto reale dell'impianto** e sovrappone flussi di energia animati in SVG/CSS che reagiscono in tempo reale alla potenza attuale.

### ✨ Caratteristiche Principali
* **Sfondo Reale:** Lo sfondo viene caricato automaticamente da GitHub (non devi caricare file locali).
* **Velocità Dinamica:** I flussi "laser" accelerano in base ai Watt reali (più potenza = animazione più veloce).
* **Doppia Stringa (MPPT):** Visualizzazione separata per Stringa 1 (Ciano, davanti) e Stringa 2 (Blu, dietro) con prospettiva 3D.
* **Batteria Liquida:** Il livello della batteria sale e scende con un effetto "onda" fluido basato sulla percentuale di carica.
* **Supporto Doppia Batteria:** Supporta 1 o 2 batterie (fa la media automatica della percentuale e la somma dei Watt).
* **Colori Intelligenti:** Ciano/Blu (Solare/Batteria), Rosso (Prelievo Rete), Bianco (Standby).
* **Conversione Automatica Unità:** Rileva e converte automaticamente kW in W per tutti i sensori di potenza.
* **Unità di Visualizzazione Flessibili:** Scegli di visualizzare i valori di potenza in Watt (W) o Kilowatt (kW).
* **Sensori Opzionali:** Supporto per sensori opzionali PV2, Batteria 2 e ricarica Auto (lascia vuoto se non usati).
* **Etichette Personalizzabili:** Etichetta di produzione giornaliera configurabile per supporto multilingua.
* **Controllo Griglia Dashboard:** Specifica quante colonne deve occupare la scheda (1-12).

### ⚙️ Requisiti
Prima di iniziare, assicurati di avere:
1.  **Home Assistant** funzionante.
2.  **[HACS](https://hacs.xyz/)** installato.
3.  L'integrazione frontend **`custom:button-card`** (Cerca "button-card" in HACS > Frontend e installala).

### 🚀 Guida all'Installazione
1.  Apri il file [`energy_card.yaml`](energy_card.yaml) presente in questa repository.
2.  Clicca sull'icona "Copy raw file" in alto a destra (o seleziona tutto il testo e copialo).
3.  Vai nella tua dashboard di Home Assistant.
4.  Clicca sulla matita in alto a destra (**Modifica plancia**).
5.  Clicca su **"Aggiungi Scheda"** (Add Card) in basso a destra.
6.  Scorri fino in fondo e seleziona la scheda **Manuale** (Manual).
7.  Cancella tutto il codice predefinito e **incolla il codice che hai copiato**.

### 🔧 Configurazione (Importante!)
Dopo aver incollato il codice, scorri all'inizio dell'editor. Troverai una sezione chiamata `variables`.
Devi sostituire i nomi di esempio con i **nomi dei tuoi sensori** reali.

```yaml
variables:
  # --- FOTOVOLTAICO ---
  sensor_pv1: "sensor.produzione_stringa_1"      # Può essere il valore PV combinato o stringa individuale
  sensor_pv2: "sensor.produzione_stringa_2"      # Lascia vuoto "" se usi il valore combinato in sensor_pv1
  sensor_daily: "sensor.produzione_giornaliera"

  # --- BATTERIA ---
  sensor_bat1_soc: "sensor.percentuale_batteria"  # Può essere SOC batteria combinata o batteria individuale
  sensor_bat1_power: "sensor.potenza_batteria"    # Può essere potenza batteria combinata o batteria individuale
  
  # Se hai una sola batteria, lascia le virgolette vuote per la seconda:
  sensor_bat2_soc: ""  # Lascia vuoto "" se usi il valore combinato in sensor_bat1_soc
  sensor_bat2_power: ""  # Lascia vuoto "" se usi il valore combinato in sensor_bat1_power
  
  # --- CASA E RETE ---
  sensor_home_load: "sensor.consumo_casa"
  sensor_grid_power: "sensor.potenza_rete"
  
  # --- AUTO (Opzionale) ---
  sensor_car_power: ""  # Lascia vuoto "" per nascondere la visualizzazione ricarica auto
  
  # --- OPZIONI DI VISUALIZZAZIONE ---
  display_unit: "kW"  # Imposta "W" per Watt o "kW" per Kilowatt
  card_columns: 2  # Numero di colonne che la scheda deve occupare (1-12)
  daily_production_label: "PRODUZIONE OGGI"  # Personalizza il testo dell'etichetta
  
  # --- IMMAGINE DI SFONDO ---
  bg_image: "https://url-tua-immagine.jpg"  # URL della tua immagine di sfondo personalizzata
```

**Note Importanti:**
- Tutti i sensori di potenza gestiscono automaticamente sia le unità W che kW
- Lascia sensor_pv2 vuoto se hai un singolo sensore PV combinato
- Lascia sensor_bat2_soc e sensor_bat2_power vuoti se hai una singola batteria
- Lascia sensor_car_power vuoto se non vuoi visualizzare la ricarica auto
- La scheda si aggiorna automaticamente ogni volta che cambia uno dei sensori configurati
"# Energy-Dashboard-Updated" 
