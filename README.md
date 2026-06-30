# ESP32S3DIV1-MIDI-CONSOLE
UNA CONSOLE DJ MIDI FAI DATE
📋 SCHEMA COLLEGAMENTI COMPONENTI (ESP32-S3 DJ MIDI)
🎛️ 1. POTENZIOMETRI (Canali Analogici ADC1 - Sicuri)
Ogni potenziometro ha 3 pin: i due esterni vanno a 3V3 e GND, quello centrale (segnale) va all'ESP32.
Componente
Pin ESP32-S3
Nota Hardware
Potenziometro 1 (CC 10)
GPIO 4
Canale ADC1_3
Potenziometro 2 (CC 11)
GPIO 5
Canale ADC1_4
Potenziometro 3 (CC 12)
GPIO 6
Canale ADC1_5
Potenziometro 4 (CC 13)
GPIO 7
Canale ADC1_6
Potenziometro 5 (CC 14)
GPIO 8
Canale ADC1_7
Potenziometro 6 (CC 15)
GPIO 9
Canale ADC1_8
Potenziometro 7 (CC 16)
GPIO 10
Canale ADC1_9

🔘 2. PULSANTI (Canali Digitali Generici)
Ogni pulsante va collegato tra il pin dell'ESP32 e il GND comune (il codice usa il PULLUP interno).
Componente
Pin ESP32-S3
Nota Hardware
Pulsante 1 (Nota 60)
GPIO 11
Digitale sicuro
Pulsante 2 (Nota 61)
GPIO 12
Digitale sicuro
Pulsante 3 (Nota 62)
GPIO 13
Digitale sicuro
Pulsante 4 (Nota 63)
GPIO 14
Digitale sicuro
Pulsante 5 (Nota 64)
GPIO 21
Digitale sicuro
Pulsante 6 (Nota 65)
GPIO 47
Digitale puro (No ADC)
Pulsante 7 (Nota 66)
GPIO 48
Digitale puro (No ADC)
Pulsante 8 (Nota 67)
GPIO 18
Digitale sicuro

🔄 3. ENCODER ROTATIVI (Ingressi Veloci Dedicati)
Il pin centrale dell'encoder va a GND. I pin A e B vanno ai rispettivi GPIO.
Componente
Pin ESP32-S3
Nota Hardware
Encoder A - Pin A
GPIO 41
Lettura veloce (No ADC)
Encoder A - Pin B
GPIO 42
Lettura veloce (No ADC)
Encoder B - Pin A
GPIO 38
Lettura veloce (No ADC)
Encoder B - Pin B
GPIO 39
Lettura veloce (No ADC)

🔌 4. PIN DI ALIMENTAZIONE E COMUNICAZIONE USB
Questi pin servono per l'alimentazione generale della scheda e dei potenziometri.
Funzione
Pin sulla Scheda
Nota Progettazione
GND
Qualsiasi pin GND
Massa comune per pulsanti, potenziometri ed encoder
3V3
Pin 3V3
Alimentazione per i pin esterni dei potenziometri (NON USARE IL 5V!)
USB NATIVA
Porta USB inferiore (OTG)
Collegata internamente a GPIO 19 (D-) e GPIO 20 (D+). Lasciare i pin liberi sul PCB.

🛑 PIN DA LASCIARE ASSOLUTAMENTE VUOTI (Vietati sul PCB)
    • GPIO 0 (BOOT): Se viene premuto a massa all'avvio da un pulsante, la scheda non parte.
    • GPIO 19 e 20: Sono le piste fisiche della porta USB che va al computer.
    • GPIO 43 e 44: Sono i pin RX/TX per i messaggi di debug.
