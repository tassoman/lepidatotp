# Lepida TOTP

Permette di utilizzare un generico client TOTP (Time based One Time Password) per autenticarsi con lo SPID di Lepida senza usare la app LepidaID e senza qrcode. 

Il codice sorgente è stato ispirato da un [post apparso su Reddit](https://www.reddit.com/r/ItalyInformatica/comments/oxateo/da_lepidaid_a_totp/).

## Installazione

Configurare un ambiente virtuale di Python3

`python -m venv env`

Attivare l'ambiente virtuale

`source env/bin/activate`

Installare le dipendenze:

`pip install -r requirements.txt`

## Creazione del token

Se già hai usato la app "ufficiale" LepidaID, allora occorre accedere al profilo e cliccare il bottone __Disassocia App__. Elimina anche la app, buttandola nel cestino. Avrai a disposizione 4 tentativi per generare il token iniziale via SMS.

Installa le dipendenze, come indicato in precedenza.

Lancia lo script e segui le istruzioni. 

`python lepidaotp.py`

Si aprirà il browser, effettua l'accesso ottenendo il token OTP via SMS. Poi segui le istruzioni indicate a schermo.

Quando apparirà il QR code, scansionalo con la tua app client TOTP (ad esempio [andOTP](https://f-droid.org/en/packages/org.shadowice.flocke.andotp/), oppure [Aegis](https://f-droid.org/it/packages/com.beemdevelopment.aegis/), che supporta anche i dispositivi biometrici).

Per provare se tutto funziona correttamente, prova a svolgere una autenticazione SPID. Naturalmente, dovrai impiegare username/password, prendendo il codice OTP a sei cifre dalla tua app.

