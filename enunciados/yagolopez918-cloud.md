# Examen Parcial - yagolopez918-cloud

**Usuario GitHub:** yagolopez918-cloud
**Fecha:** 4 de noviembre de 2025
**Retos tenidos en cuenta:** Reto 003

---

## Instrucciones

A continuación encontrarás fragmentos de código extraídos de tus entregas. Cada fragmento contiene una o más situaciones relacionadas con los conceptos vistos en clase.

Para cada pregunta debes:
1) Identificar a qué se refiere la observación
2) Explicar si es o no un error y por qué
3) Proponer la corrección

Nota: Responde 5 de las 10 preguntas (en función a lo indicado en el examen).


---

## Pregunta 1

Archivo: `SimulacionHotel.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/68c3a571aa52659f92d22b863c17d3b5cd9f3ed9/entregas/yago.lopez/SimulacionHotel.java) (Reto 003)

```java
while (dia <= DIAS) {
    int consumoDia = 0;
    // ...
    int hora = 0;
    while (hora < HORAS) {
        // ...
        hora++;
    }
}
```

¿Qué observas en este código?

---

## Pregunta 2

Archivo: `SimulacionHotel.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/68c3a571aa52659f92d22b863c17d3b5cd9f3ed9/entregas/yago.lopez/SimulacionHotel.java) (Reto 003)

```java
if (hayMantenimiento && hora == horaMantenimiento)
    System.out.println(plantaMantenimiento + "ª planta en mantenimiento");
```

¿Qué observas en este código?

Observo que este código está correcto gracias a que la variable **`hora`** es una **variable primitiva**, y la variable **`hayMantenimiento`** es de tipo **boolean**.  
Debido a esto, el operador **`==`** puede usarse para **comparar** ambos valores.  
De no ser así, sería necesario emplear **otro tipo de marcador de equidad**, como **`equals`**.

---

## Pregunta 3

Archivo: `SimulacionHotel.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/68c3a571aa52659f92d22b863c17d3b5cd9f3ed9/entregas/yago.lopez/SimulacionHotel.java) (Reto 003)

```java
if (hayRayo && c == columnaRayo) {
    celda = "[X]";
} else if (hayMantenimiento && p == plantaMantenimiento && hora >= horaMantenimiento) {
    celda = "[#]";
} else if (persianaAbierta && luzEncendida) {
    celda = "[*]";
    consumoDia++;
} else if (persianaAbierta && !luzEncendida) {
    celda = "[º]";
} else {
    celda = "[ ]";
}
```

¿Qué observas en este código?

Lo que veo principalmente como error en este código es que, si por ejemplo **hay un rayo** y **hay mantenimiento** en la **misma celda**, al ser el **rayo** el que se evalúa primero siempre se marcará como que **hay un rayo** en esa celda, dejando de lado si **hay mantenimiento** o no.

---

## Pregunta 4

Archivo: `SimulacionHotel.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/68c3a571aa52659f92d22b863c17d3b5cd9f3ed9/entregas/yago.lopez/SimulacionHotel.java) (Reto 003)

```java
System.out.println("Dia " + dia + " - " + hora + ":00  Consumo hora: " + consumoDia);
```

¿Qué observas en este código?

El problema en este código está en la **última expresión que aparece entre comillas**, ya que debería decir **"Consumo Día"** y no **"Consumo Hora"**.  

Esto se debe a que posteriormente se suma la variable **`consumoDia`**, la cual **mide el consumo diario** y no el consumo por hora.  
Por tanto, había una **incongruencia** en el texto mostrado.

```java
System.out.println("Día " + dia + " - " + hora + ":00  Consumo Día: " + consumoDia);

---

## Pregunta 5

Archivo: `SimulacionHotel.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/68c3a571aa52659f92d22b863c17d3b5cd9f3ed9/entregas/yago.lopez/SimulacionHotel.java) (Reto 003)

```java
System.out.println("Media semanal: " + (consumoTotalSemana / 7));
```

¿Qué observas en este código?

---

## Pregunta 6

Archivo: `Calculadora de precio.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/ae72036461e313168f4fd4c3bf593a6ab14a683c/entregas/yago.lopez/Calculadora%20de%20precio.java) (Reto 001)

```java
int rebaja = cantidadProducto >= 100 ? 15 :
             cantidadProducto >= 50 ? 10 :
             cantidadProducto >= 10 ? 5 : 0;

double precioConIva = precioBaseEuros * (1 + tipoIva / 100.0);
double precioUnitarioFinal = precioConIva * (1 - rebaja / 100.0);
double precioTotal = precioUnitarioFinal * cantidadProducto;
```

¿Qué observas en este código?

---

## Pregunta 7

Archivo: `Conversor de segundos.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/ae72036461e313168f4fd4c3bf593a6ab14a683c/entregas/yago.lopez/Conversor%20de%20segundos.java) (Reto 001)

```java
System.out.println("\n" + segundosTotales + " segundos son:");
System.out.println(dias + " días");
System.out.println(horas + " horas");
System.out.println(minutos + " minutos");
System.out.println(segundos + " segundos");
```

¿Qué observas en este código?

No es un **error**, ya que el código está escrito con una **buena sintaxis**.  
El único posible detalle sería el **nombre de las variables**, que **debería estar en mayúsculas** si fueran **variables fijas**.  
Sin embargo, al no serlo, **el código está correcto tal como está**.

---

## Pregunta 8

Archivo: `SimulacionHotel.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/68c3a571aa52659f92d22b863c17d3b5cd9f3ed9/entregas/yago.lopez/SimulacionHotel.java) (Reto 003)

```java
int dia = 1;
int consumoTotalSemana = 0;

while (dia <= DIAS) {
    int consumoDia = 0;
    // ... código ...
    int hora = 0;
    while (hora < HORAS) {
        // ... código ...
        if (persianaAbierta && luzEncendida) {
            celda = "[*]";
            consumoDia++;
        }
        // ... más código ...
        hora++;
    }
    System.out.println("Consumo total del día " + dia + ": " + consumoDia);
```

¿Qué observas en este código?

---

## Pregunta 9

Archivo: `SimulacionHotel.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/68c3a571aa52659f92d22b863c17d3b5cd9f3ed9/entregas/yago.lopez/SimulacionHotel.java) (Reto 003)

```java
if (random.nextDouble() < PROB_MANTENIMIENTO) {
    hayMantenimiento = true;
    plantaMantenimiento = 1 + random.nextInt(PLANTAS);
    horaMantenimiento = random.nextInt(HORAS);
}

int hora = 0;
while (hora < HORAS) {
    // ... código ...
    if (hayMantenimiento && p == plantaMantenimiento && hora >= horaMantenimiento) {
        celda = "[#]";
    }
```

¿Qué observas en este código?
### 1. Problema con la condición `PROB_MANTENIMIENTO`

El principal problema que observo es que, si **`PROB_MANTENIMIENTO` no se cumple**, su valor por defecto es `false`.  
En ese caso, **el código no realizaría ninguna acción**, lo cual lo haría ineficaz.  

###  Propuesta de mejora

Inicializar las variables **antes del bloque `if`**, garantizando valores válidos iniciales:

```java
hayMantenimiento = false;
plantaMantenimiento = -1; 
horaMantenimiento = -1;

if (random.nextDouble() < PROB_MANTENIMIENTO) {
    hayMantenimiento = true;
    plantaMantenimiento = 1 + random.nextInt(PLANTAS);
    horaMantenimiento = random.nextInt(HORAS);
}
```
## Problema con la generación de la hora de mantenimiento

En la segunda parte del código, el problema que observo es que, si por ejemplo la **hora es 23**, solo habría **un mantenimiento por día**, lo cual resulta **poco realista**.  

##  Propuesta de solución 

Sugiero **intercambiar ese fragmento de código** por el siguiente, de modo que exista **un rango de horas** y un **mínimo de dos mantenimientos** al día:

```java
horaMantenimiento = random.nextInt(HORAS - 2);

---

## Pregunta 10

Archivo: `SimulacionHotel.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/68c3a571aa52659f92d22b863c17d3b5cd9f3ed9/entregas/yago.lopez/SimulacionHotel.java) (Reto 003)

```java
int p = PLANTAS;
while (p >= 1) {
    System.out.print(":");
    int c = 1;
    while (c <= HABITACIONES) {
        String celda = "[ ]";
        boolean persianaAbierta = random.nextDouble() < PROB_PERSIANA;
        boolean luzEncendida = random.nextDouble() < PROB_LUZ;
```

¿Qué observas en este código?


