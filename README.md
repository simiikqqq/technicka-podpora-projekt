# 🎮 Technická podpora – VDF Games

Jednoduchá webová aplikace pro odesílání dotazů na technickou podporu herní společnosti VDF Games. Uživatel může popsat svůj problém, volitelně zadat e-mail a získat odpověď od backendového serveru.

## 📋 Funkce

- Odesílání dotazů prostřednictvím webového formuláře.
- Volitelné zadání e-mailové adresy.
- Zobrazení stavu při zpracování dotazu.
- Zobrazení odpovědi ze serveru.
- Ošetření prázdného dotazu a chyb při komunikaci se serverem.
- Demo režim bez nutnosti komunikace s backendem.

## 🛠️ Použité technologie

- **HTML5** – struktura webové stránky.
- **CSS3** – vzhled a rozložení stránky.
- **JavaScript** – zpracování formuláře a komunikace s API.
- **Python** – backendová logika.
- **Flask** – vytvoření HTTP API.
- **Flask-CORS** – povolení komunikace mezi frontendem a backendem.

## 📁 Struktura projektu

```text
technicka-podpora-vdf-games/
├── index.html
├── style.css
├── script.js
├── app.py
└── README.md
```

- `index.html` – hlavní webová stránka.
- `style.css` – styly aplikace.
- `script.js` – logika frontendu a komunikace se serverem.
- `app.py` – backend vytvořený pomocí Flasku.
- `README.md` – dokumentace projektu.

## ⚙️ Jak aplikace funguje

1. Uživatel zadá svůj dotaz do formuláře.
2. JavaScript ověří, zda dotaz není prázdný.
3. Formulář odešle data na backend ve formátu JSON.
4. Backend zpracuje požadavek a vytvoří odpověď.
5. Frontend zobrazí přijatou odpověď nebo chybovou zprávu.

## 📡 API

Backend nabízí následující endpointy:

### `GET /`

Ověření, zda backend běží.

### `POST /chat`

Přijímá dotaz uživatele ve formátu JSON.

Příklad požadavku:

```json
{
  "message": "Hra se mi po aktualizaci nespustí.",
  "student": "Novak_Simon_4IT",
  "email": "uzivatel@email.cz"
}
```

Pole `email` je volitelné. Backend ho v současné době nezpracovává.

Příklad odpovědi:

```json
{
  "reply": "[DEMO] Přijal jsem dotaz od Novak_Simon_4IT: Hra se mi po aktualizaci nespustí."
}
```

**Poznámka:** Backend aktuálně vrací pouze testovací odpovědi. Aplikace zatím není napojena na skutečný systém zákaznické podpory ani na umělou inteligenci.

## 🚀 Spuštění projektu

### 1. Frontend

Otevři soubor `index.html` v internetovém prohlížeči nebo projekt spusť pomocí lokálního webového serveru.

### 2. Backend

Je potřeba mít nainstalovaný Python.

Nainstaluj potřebné knihovny:

```bash
pip install flask flask-cors
```

Spusť backend příkazem:

```bash
python app.py
```

Server se standardně spustí na portu `8000`, pokud není nastavena proměnná prostředí `PORT`.

### 3. Konfigurace frontendu

V souboru `script.js` lze upravit nastavení komunikace s backendem:

```javascript
const USE_BACKEND = true;
const BACKEND_URL = "https://technicka-podpora-projekt-2.onrender.com/chat";
```

- `USE_BACKEND = true` – aplikace komunikuje se vzdáleným backendem.
- `USE_BACKEND = false` – aplikace zobrazí demo odpověď bez komunikace se serverem.

**Důležité:** Frontend musí odesílat požadavky na endpoint `/chat`, protože právě ten backend používá ke zpracování dotazů.

## 🔮 Možná budoucí rozšíření

- Napojení na umělou inteligenci pro automatické odpovědi.
- Ukládání dotazů do databáze.
- Historie komunikace se zákaznickou podporou.
- Zasílání potvrzení o přijetí dotazu e-mailem.
- Vylepšení vzhledu a responzivního designu.
- Rozšíření validace a zabezpečení API.

## 🎓 Účel projektu

Projekt slouží jako školní ukázka propojení webového frontendu s backendovým API. Demonstruje práci s HTML, CSS, JavaScriptem, Pythonem a frameworkem Flask.

---

**Autor:** Šimon Novák  
**Projekt:** Technická podpora – VDF Games  
**Typ projektu:** Školní projekt

