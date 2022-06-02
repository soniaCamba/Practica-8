# Practica-8

## CÓDIGO
```
#include <Arduino.h>

void setup() {
 
 Serial.begin(115200);
 Serial2.begin(115200);
}
 
void loop() { //Choose Serial1 or Serial2 as required
 while (Serial.available()) {
   Serial2.print(char(Serial.read()));
 }
 while (Serial2.available()) {
   Serial.print(char(Serial2.read()));
 }
}
```

## FUNCIONAMIENTO

Esta practica está diseñada para entender y aprender a trabajar con los buses de comunicación UART

> Excepto la de arduino, no nos hacen falta librerias
```
#include <Arduino.h>
```
> En el setup inicializamos dos Serials que proximamente se comunnicarán entre ellos, el primero será para leer y el segundo para escribir
```
void setup() {
 
 Serial.begin(115200);
 Serial2.begin(115200);
}
```
En el loop tenemos los dos whiles, unos para escribir y otro para leer
> En el primero si esta libre el Serial que lee, nos dejará escribir, uno siempre necesita al otro
```
void loop() { //Choose Serial1 or Serial2 as required
while (Serial.available()) {
 Serial2.print(char(Serial.read()));
}
```
> Y el segundo funciona al revés
```
while (Serial2.available()) {
 Serial.print(char(Serial2.read()));
 }
```
Y para acabar el programa y que funciones solo tendríamos que cerrar los corchetes que hayan quedado abiertos
