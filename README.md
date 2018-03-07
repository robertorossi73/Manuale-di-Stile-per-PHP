# Manuale di Stile per PHP
Guida alla redazione di programmi in PHP (in lavorazione).

* [Costanti](#costanti)
* [Stringhe](#stringhe)
* [Arrays](#arrays)

## Costanti

### I nomi delle costanti **DEVONO** contenere solo caratteri alfanumerici ed il carattere di sottolineatura (underscore).

### Tutte le lettere utilizzate nel nome di una costante **DEVONO** essere in maiuscolo.

### Tutte le parole nel nome di una costante **DEVONO** essere separate da caratteri di sottolineatura (underscore).

## Stringhe
### Le stringhe letterali **DEVONO** essere delimitate dalle virgolette singole.
```php
$string = 'example string';
```

### Le stringhe che contengono virgolette singole **DEVONO** essere delimitate dalle virgolette doppie.
```php
$str = "That's a 'magic' sock.";
```
> Questa sintassi è preferibile rispetto al carattere di escape `\` poiché è molto più facile da leggere.
> Inoltre è particolarmente utile per le istruzioni SQL:
> ```php
> $sql = "SELECT `id`, `name` from `people` "
>     . "WHERE `name`='Mickey' OR `name`='Minnie'";
> ```

### Le stringhe **NON DEVONO** contenere variabili da sostituire.
```php
$string = 'Hello ' . $name . ', welcome back!';
```
> Questa sintassi migliora le leggibilità del codice rispetto ai seguenti esempi:
> ```php
> $string = "Hello $name, welcome back!";
> $string = "Hello {$name}, welcome back!";
> $string = "Hello ${name}, welcome back!";
> ```

### L'operatore di concatenazione **DEVE** essere preceduto e seguito da un singolo spazio.
```php
$string = 'Mickey' . ' ' . 'Mouse';
```
> Migliora la leggibilità del codice.

### L'operatore di concatenazione `.` **DEVE** essere allineato all'operatore di assegnazione `=` quando l'istruzione è suddivisa su più righe.
```php
$sql = "SELECT `id`, `name` from `people` "
     . "WHERE `name`='Mickey' OR `name`='Minnie'";
     . "ORDER BY `name` ASC ";
```
> Quando si concatenano le stringhe con l'operatore `.`, è meglio suddividere l'istruzione in più righe per migliorarne la leggibilità. In questi casi, ogni riga successiva deve essere riempita con tanti spazi bianchi, tali che l'operatore di concatenazione `.` sia allineato all'operatore di assegnazione `=`. 

## Arrays
### Gli arrays **DEVONO** essere dichiarati con la sintassi concisa.
```php
$arr = [];
```

### Gli arrays **NON DEVONO** avere indici numerici negativi.
> L'uso di numeri negativi come indici di un array può causare problemi con alcune funzioni della libreria standard di PHP.

### I delimitatori degli elementi `,` di un array **DEVONO** essere seguiti da uno spazio.
```php
$arr = ['Mickey', 'Minnie', 1, 2, 3];

```
> Migliora la leggibilità del codice.

### Gli operatori di assegnazione di un valore a una chiave `=>` **DEVONO** essere preceduti e seguiti da uno spazio.
```php
$arr = ['firstKey'  => 'firstValue', 'secondKey' => 'secondValue'];

```
> Migliora la leggibilità del codice.

### Gli array suddivisi su più righe **DEVONO** seguire le seguenti raccomandazioni:
* il primo elemento **DEVE** essere posizionato sulla riga successiva a quella della dichiarazione dell'array;
* ogni elemento **DEVE** essere su una propria riga;
* gli elementi **DEVONO** avere un'indentazione maggiore rispetto alla riga di dichiarazione dell'array;
* gli operatori di assegnazione di un valore a una chiave `=>` **DEVONO** essere allineati;
* l'ultimo elemento **DEVE** essere sempre delimitato da una virgola;
* la parentesi di chiusura **DEVE** essere su una propria riga allo stesso livello di indentazione della riga contenente la dichiarazione dell'array;
```php
$arr = [
    'firstKey'  => 'firstValue', 
    'secondKey' => 'secondValue',
];

```
> L'uso della virgola finale dopo l'ultimo elemento nell'array riduce al minimo la possibilità che si verifichino errori di analisi a causa di una virgola mancante per l'aggiunta di nuovi elementi.
