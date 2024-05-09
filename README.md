<div>
  <img
    src="https://i.imgur.com/MLlNSm4.png"
    class="logo-img"
    style="width:200px;heigth:200px"
    />
</div>

# Wolfie Airlines Server

A server that allows online checkin validation across the webpage.

Server can be found at this link [wolfie-airlines-server](https://wolfie-airlines-server.vercel.app/).

<details>
  <summary>
    🇵🇱 POLISH
  </summary>

# Opis
Serwer przeprowadzający odprawę biletową online, zwracający odpowiedź do [strony projektu](https://github.com/wolfie-airlines/wolfie-airlines-webpage). Napisany w całości przy użyciu języka JavaScript oraz przy użyciu biblioteki Express.js z użyciem biblioteki dla bazy danych MongoDB.

## Endpointy

### `GET` [https://wolfie-airlines-server.vercel.app/odprawa/username/email/flightId/seats](https://wolfie-airlines-server.vercel.app/odprawa/username/email/flightId/seats)
| username | email | flightId | seats |
| --- | --- | --- | --- |
| `nazwa użytkownika` | `e-mail użytkownika` | `unikalne ID lotu` | `miejsca wykupione na bilecie` |

Ten endpoint zaczyna odprawę. Przekazuje zwrotne parametry znajdujące się [tutaj](https://github.com/wolfie-airlines/wolfie-airlines-server/blob/main/index.js#L98) na stronę, która wysyła kolejne zapytanie do następnego endpointa.
- Takie obejście było nieuniknione, ponieważ React, żeby sprawdzić poprawność wczytywania wszystkich komponentów renderuje się dwuktrotnie. W tym momencie, nie zdążyła się wyświetlić wiadomość o poprawnie przeprowadzonej odprawie, tylko błąd, że użytkownik takową odprawę już posiadał.

### `GET` [https://wolfie-airlines-server.vercel.app/odprawa/accept/username/email/flightId/seats](https://wolfie-airlines-server.vercel.app/odprawa/accept/username/email/flightId/seats)
| username | email | flightId | seats |
| --- | --- | --- | --- |
| `nazwa użytkownika` | `e-mail użytkownika` | `unikalne ID lotu` | `miejsca wykupione na bilecie` |

Ten endpoint akceptuje odprawę z przekazanymi parametrami z poprzedniego endpointa, które zostały wysłane do niego przez stronę. Waliduje odprawę online oraz zapisuje ją do bazy danych. Zwraca również komunikat o poprawności przeprowadzenia odprawy online i pozwala wygenerować karty pokładowe w późniejszym etapie na stronie. Zwraca jedynie [success](https://github.com/wolfie-airlines/wolfie-airlines-server/blob/main/index.js#L172).

## Requirements
Opisane w pliku [package.json](https://github.com/wolfie-airlines/wolfie-airlines-server/blob/main/package.json).

## Self-hosting
1. Sklonuj repozytorium, bądź utwórz forka.
2. W folderze sklonowanego projetku uruchom komendę
   ```npm install```
3. Żeby wystartować projekt na localhoście (domyślny port to **5000**) wpisz komendę ```node index.js```

## Commity
Pełny opis commitów znajduje się w [głównym repozytorium projektu](https://github.com/wolfie-airlines/wolfie-airlines).
Konkretne i szczegółowe committy związane z serwerem w repozytorium projektu to:
- [a5f1dd5](https://github.com/wolfie-airlines/wolfie-airlines/commit/a5f1dd5013b1226b092d7d1ca6aefdbca0003163)
- [0add627](https://github.com/wolfie-airlines/wolfie-airlines/commit/0add627f8dc71bc8d102228b97814b36e811985a)
- [f28a724](https://github.com/wolfie-airlines/wolfie-airlines/commit/f28a724ca747aa3d71035a862983adb9a1ea44de)
- [970400e](https://github.com/wolfie-airlines/wolfie-airlines/commit/970400e8666cd91c28debffeda302a09fdea3d5b)
oraz:
- [efb4adc](https://github.com/wolfie-airlines/wolfie-airlines-server/commit/efb4adc2227bbf6b0f8cbb14e4a8e5cacdfa6b0b)
- [1d55131](https://github.com/wolfie-airlines/wolfie-airlines-server/commit/1d55131a7e7ee768a9501a4e3ad5cb68dcd00af8)

</details>

<details>
  <summary>
    🇬🇧 ENGLISH
  </summary>

# Description
A server that performs online check-in, returning a response to [project site](https://github.com/wolfie-airlines/wolfie-airlines-webpage). Written entirely using JavaScript and using the Express.js library with a library for the MongoDB database.

## Endpoints

### `GET` [https://wolfie-airlines-server.vercel.app/odprawa/username/email/flightId/seats](https://wolfie-airlines-server.vercel.app/odprawa/username/email/flightId/seats)
| username | email | flightId | seats |
| --- | --- | --- | --- |
| `user name` | `user email` | `unique flight ID` | `seats purchased on ticket` |

This endpoint starts the check-in. It passes the return parameters found [here](https://github.com/wolfie-airlines/wolfie-airlines-server/blob/main/index.js#L98) to the page, which sends another query to the next endpoint.
- Such a workaround was unavoidable because React, in order to validate the loading of all components, renders itself twice. At this point, it didn't manage to display a message about a valid check-in, only an error that the user already had such a check-in.

### `GET` [https://wolfie-airlines-server.vercel.app/odprawa/accept/username/email/flightId/seats](https://wolfie-airlines-server.vercel.app/odprawa/accept/username/email/flightId/seats)
| username | email | flightId | seats |
| --- | --- | --- | --- |
| `user name` | `user email` | `unique flight ID` | `seats purchased on ticket` |

This endpoint accepts the check-in with the passed parameters from the previous endpoint that were sent to it by the site. It validates the online check-in and saves it to the database. It also returns a message that the online check-in has been validated and allows boarding passes to be generated later on the site. It only returns [success](https://github.com/wolfie-airlines/wolfie-airlines-server/blob/main/index.js#L172).

## Requirements
Opisane w pliku [package.json](https://github.com/wolfie-airlines/wolfie-airlines-server/blob/main/package.json).

## Self-hosting
1. clone the repository, or create a fork.
2. in the folder of the cloned project, run the command
   ``npm install``.
3. to start the project on the localhost (default port is **5000**) type the command ``node index.js``.

## Commits
A full description of the commits can be found in the [main project repository](https://github.com/wolfie-airlines/wolfie-airlines).
The specific and detailed commits associated with the server in the project's main repository are:
- [a5f1dd5](https://github.com/wolfie-airlines/wolfie-airlines/commit/a5f1dd5013b1226b092d7d1ca6aefdbca0003163)
- [0add627](https://github.com/wolfie-airlines/wolfie-airlines/commit/0add627f8dc71bc8d102228b97814b36e811985a)
- [f28a724](https://github.com/wolfie-airlines/wolfie-airlines/commit/f28a724ca747aa3d71035a862983adb9a1ea44de)
- [970400e](https://github.com/wolfie-airlines/wolfie-airlines/commit/970400e8666cd91c28debffeda302a09fdea3d5b)
also:
- [efb4adc](https://github.com/wolfie-airlines/wolfie-airlines-server/commit/efb4adc2227bbf6b0f8cbb14e4a8e5cacdfa6b0b)
- [1d55131](https://github.com/wolfie-airlines/wolfie-airlines-server/commit/1d55131a7e7ee768a9501a4e3ad5cb68dcd00af8)

## Stars
If you liked the website or the whole project, I would appreciate you marking it with a `star`.

</details>
