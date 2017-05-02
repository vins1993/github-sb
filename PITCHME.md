# SHIELD THESIS
## Design Aspects

---
# Implementazione vNSF
## KVM vs Docker
---
## Approccio KVM
Virtualizzazione dell'intero sistema operativo. 
- PRO
 - Maggior Isolamento
 - General-purpose (più flessibilità)
- CONTRO 
 - Lento
 - Dipendente da architettura sottostante
--- 
## Approccio Docker 
- PRO
 - Veloce
 - Leggero (facile migrazione di immagini)
- CONTRO
 - Minor Isolamento
 - Sicurezza (namespaces, root capabilities e shared kernel)
---

## Configurazione di una vNSF (es Reverse Proxy)
KVM:
- Espone un'interfaccia REST
- Riceve configurazione in formato character-oriented (es JSON)
- Crea un file di configurazione readable dal Software Proxy
- Rilancia il processo della vNSF (NO RIAVVIO MACCHINA VIRTUALE)
---
## Configurazione di una vNSF (es Reverse Proxy) (2)
Docker:
Ogni container parte da una immagine _STATICA_ 
 - -> Come incorporare un file di configurazione in una vNSF su Docker?

Due soluzioni:
 - File di Configurazione incapsulato nell'immagine (Dockerfile) 
 - Volume Docker
---
## Dockerfile con file di configurazione

 
 ![Image of Volume Approach]
 (assets/volume.png)
