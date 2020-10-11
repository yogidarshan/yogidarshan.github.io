---
layout: post
title:  "Statystyka"
date:   2020-10-11 8:09:00 +0200
categories: jekyll update
---
Spotkałem się z zaprzeczaniem faktów.

## Nieprzyjemne spotkanie w sklepie

Myślałem już o napisaniu tego artykułu gdy pokłóciłem się z chłopakiem, który wyzywał mnie za noszenie maseczki. Myślałem:

> Czy on wie, że w jeden dzień zmarło kilkudziesięciu ludzi na koronawirusa?

Mógł nie wiedzieć. Był to pierwszy dzień, którego zmarło kilkudziesięciu ludzi. Jeżeli nie wierzy w istnienie koronawirusa, to może nie sprawdza statystyk i zwyczajnie nie wie; wtedy nie miałbym prawa używać wobec niego tego argumentu, bo nie musiał tego wiedzieć.

Śledziłem temat protestów. Zastanawiałem się przeciwko czemu ludzie protestują. Przeciwko koronawirusowi? Chciałbym, żeby wychodząc na ulice można było powstrzymać epidemię.

Domyślam się, że protestują przeciwko obostrzeniom, w tym maseczkom. Lecz czy chłopak mógł nawrzeszczeć na mnie za to, że noszę maseczkę?

## Statystyka

Uważam, że została już przekroczona masa krytyczna. Oznacza to, że nawet jeśli część chorych nikogo nie zarazi, to chorych jest na tyle dużo, że i tak liczba chorych narasta wykładniczo (lawinowo).

Ciągle jednak zachorował „tylko” 1 na 312,5 mieszkańców Polski. Oznacza to, że nawet w dużym tłumie ludzi (około 300) może się nie zdarzyć ani jeden chory. Mało kto ma 300 znajomych, więc prawdopodobnie wielu ludzi nie zna nikogo chorego.

W tym artykule będę się posługiwał matematyką i informatyką, bo bardzo lubię obie te dziedziny.

Strona [koronawirus u nas][koronawirus] podaje, że:

> Do tej pory zakażenie koronawirusem wywołującym chorobę COVID-19 potwierdzono u 0.32% mieszkańców Polski.

0,32% to inaczej 0,0032 całości.

1/0,0032 to 312,5. Stąd wiem, że 0,32% to 1 na 312,5.

Ostatnio zachorowało 5300 ludzi w jeden dzień. Jeżeli stale będzie chorować 5300 ludzi dziennie, to epidemia dotknie wszystkich mieszkańców Polski za 19 lat i 209 dni.

Tyle jeśli liczba chorych nie będzie narastała wykładniczo.

Zakładam jednak, że tempo zachorowań ma wykładniczy charakter.

Napisałem program, który symuluje ilość zachorowań w najbliższych dniach. Program można pobrać stąd:

> <https://github.com/syrop/MyApplication/tree/calculator>

Wymaga uruchomienia na Androidzie.

Wyliczyłem, że w ostatnim dniu ilość wykrytych przypadków wzrosła o 11,84%. Jeżeli tempo wzrostu się utrzyma, kolejnego dnia będzie 5927 zachorowań, potem 6629. Po 5 dniach 9273 zachorowań, po 7 dniach 11598. Po 10 dniach 16224, po 20 dniach 49666, a w ciągu 60 dni zachorują wszyscy mieszkańcy Polski.

Wyliczyłem jak często podwaja się ilość wykrytych przypadków w ciągu dnia według tego wzoru w Kotlinie:

```kotlin
private fun doubling() = log(2.0, perCentDaily() / 100.0 + 1.0)

private fun perCentDaily() =
        (PER_DAY.toDouble() / YESTERDAY.toDouble() - 1.0) * 100.0
```

Wyszło na to, że ilość dziennych zachorowań podwaja się w ciągu 6,2 dnia.

Nie każdego dnia pobijany jest rekord, a w weekendy jest zwykle mniej wykrytych zachorowań, niż w sąsiednich dniach.

Tak czy inaczej, każdej niedzieli jest więcej wykrytych przypadków niż poprzedniej niedzieli, a w ciągu ostatniego tygodnia ilość dziennych zachorowań wzrosła o 123,9.

Jestem ciekaw, czy dobrze oszacowałem wzrost zachorowań. Jeżeli trzymać się wyniku, który otrzymałem analizując tylko dwa ostatnie dni, za 27 dni będzie ponad 100 tysięcy zachorowań dziennie, a za 47 dni ponad milion!

Pewnie w praktyce wzrost nie będzie tak szybki, bo z czasem coraz trudniej będzie znaleźć ludzi, którzy jeszcze nigdy nie byli chorzy.

To jest paradoks: Pandemia trwa ponad pół roku, i ciągle nie ma nawet 1 wykrytego przypadku na 300 mieszkańców Polski, a już za trzy tygodnie ma być 1 na 64 (jeżeli liczba dziennych zachorowań podwaja się co 6,2 dnia).

## YouTube

Do napisania tego artykułu nie zainspirowała mnie jeszcze kłótnia w sklepie. Nie nagrałem jej, więc nie miałbym czego cytować na potrzeby tego artykułu.

Zainspirowała mnie wymiana na YouTube pod tym wideo:

> <https://www.youtube.com/watch?v=9PYRBfErA7w>

To wideo z wczorajszej demonstracji we Wrocławiu.

Nie wiem czy policja ostatecznie zakończyła demonstrację, czy ją tylko utrudniała. Nie obejrzałem całości.

Napisałem:

> Bardzo dobrze, że policja rozgoniła tych pajaców! Ludzie giną dziesiątkami z braku powietrza. Kończą się miejsca w szpitalach. Lekarze są przepracowani, a antycovidowcy robią sobie jaja z pogrzebu!!!

Dostałem nawet jedno polubienie tego komentarza.

Szybko dostałem odpowiedź:

> W szpitalach nie ma miejsc, przez wydzielone miejsca dla covidowcow, ktore są puste (od 100 zł za łóżko dla szpitala za covidiana). Lekarze są przepracowani przyjmowaniem prywatnie pacjentów (od 150 zł wizyta w Krakowie, w prywatnych gabinetach wirus nie zaraża). Zakład pogrzebowe narzekaja na niską ilość pogrzebów (gdzie te koronatrupy?) Policjant robi to co mu każą aby nie stracić pracy...

Ta odpowiedź ma aż 7 polubień. Oznacza to, że publiczność bardziej zgadza się z tym, niż z tym co napisałem wcześniej.

Odpisałem:

> Jeśli twoim celem jest zapewnić pracę dla zakładów pogrzebowych, to... chodź bez maseczki :) A może wypadki drogowe są konspiracją, nie covid? Jeśli tyle ludzi ginie na drogach, to dlaczego zakłady pogrzebowe ciągle są puste, hę? Może przepisy drogowe trzeba zlikwidować.

Rozumiem dlaczego ktoś napisał, że łóżka w szpitalach są puste. Cytat z [Gazety Wrocławskiej][wroclawska]:

> Tymczasem z oficjalnych statystyk urzędu marszałkowskiego wynika, że na Koszarowej jest jeszcze około 40 wolnych łóżek. Skąd taka różnica? Jak tłumaczy Simon, urzędnicy liczą wszystkie łóżka w szpitalu. - Tymczasem część z nich jest niedostępna. Jeśli pojawia się osoba podejrzana o zakażenie, kładziemy ją na 2 – 3 osobowej sali. Dwa łóżka są wyłączone. W statystykach one ciągle są dostępne, my nie możemy ich wykorzystać - tłumaczy ordynator.

Wygląda na to, że część łóżek musi stać pusta, a mój oponent po prostu nie znał przyczyny.

Nie rozumiem za to argumentu z zakładami pogrzebowymi. No i co, że narzekają na niską ilość pogrzebów?

Czy celem antycovidowców jest rozwiązanie „problemu” małej liczby pogrzebów?

Identycznego argumentu możnaby użwać przeciwko przepisom drogowym:

> Zlikwidujmy przepisy drogowe, bo zakłady porgzebowe narzekają na niską ilość pogrzebów.

Zasady BHP w pracy:

> Zlikwidujmy BHP, bo zakłady pogrzebowe narzekają na niską ilość pogrzebów.

Przemoc domowa:

> Promujmy przemoc domową, bo zakłady pogrzebowe narzekają na niską ilość pogrzebów.

Nie robiłem zaawasnowachy statystyk dotyczących dziennej ilośći zmarłych, ale parę rzeczy mogę wyliczyć na szybko.

Według strony [koronawirus u nas][koronawirus] umiera 2,44% zakażonych.

Jeżeli jest 0,32% zakażonych, to ilość zmarłych można wyliczyć według tego wzoru:

> 1/(.0032*0.0244)

Wyszło mi, że do tej pory zmarł 1 na 12807 mieszkańców Polski.

Zauważyłem, że procentowy udział zmarłych wśród zakażonych spada, ale jeśli mimo wszystko utrzyma się na poziomie 2,44%, a tempo wzrostu zakażeń będzie się podwajać co 6,2 dnia, to:

Za 5 dni będzie 1 zmarły na 9787 mieszkańców Polski.

Za 15 dni będzie 1 zmarły na 4585 mieszkańców Polski.

Za 31 dni będzie 1 zmarły na 928 mieszkańców Polski.

Za 52 dni będzie 1 zmarły na 92 mieszkańców Polski.

## Podsumowanie

W sklepie zostałem zaatakowany między innymi za to, że noszę maseczkę. Mój napastnik mógł nie wiedzieć, że tego dnia pierwszy raz liczba zmarłych z powodu koronawirusa wyniosła kilkadziesiąt, więc wtedy jeszcze nie mogłem użyć tego argumentu.

Nie wydarzyło się też tam wystarczająco dużo abym chciał o tym napisać artykuł. Nie mam co cytować. Nie mam nagrania.

Kilka dni później znalazłem jednak nagranie z ciekawej akcji policji na proteście we Wrocławiu. Wziąłem udział w dyskusji i mam teraz co cytować. Mam też opisany wyżej program przeprowadzający symulację.

Ciekaw jestem czy za 10-20 dni antycovidowcy nadal będą narzekali na małą ilość pogrzebów.

Żałuję, że media prezentują pojęcie *wypłaszczenia krzywej*, które dla mnie nic nie znaczy, a nie prezestują *funkcji wykładniczej* i *masy krytycznej*, które mają znaczenie przy wielkościach narastających lawinowo. Może wtedy nie musiałbym opisywać tego tak szczegółowo w tym artykule.

Ilość ofiar wypadków samochodowych nie narasta wykładniczo, bo jedna ofiara nie zaraża kolejnych ofiar. Mimo to ciekaw jestem dlaczego antycovidowcy nie stosują swojej własnej logiki do ruchu drogowego:

> Puste zakłady pogrzebowe. Puste łóżka szpitalne. Wniosek: Za bardzo restrykcyjne przepisy drogowe.

Myślałem, że celem obostrzeń – nie ich wadą – jest utrzymanie liczby pogrzebów na niskim poziomie.

Martwi mnie to, że antycovidowcy nie używają argumentów. Nie spotkałem się z programem napisanym przez antycovidowca, który przeprowadzałby symulację alternatywną dla mojej. Antycovidowiec potrafi powiedzieć, że jest niska ilość pogrzebów, ale ja chcę konkretów, na przykład:

> 10 tysięcy zachorowań dziennie – akceptowalne i niskie.

> 100 zmarłych dziennie – akceptowalna i niska liczba pogrzebów

> Ilość dziennich zachorowań podwajana co tydzień – akceptowalna i niska

Ile dokładnie jest gotów zaakceptować antycovidowiec?

[koronawirus]: https://koronawirusunas.pl/
[wroclawska]: https://gazetawroclawska.pl/szpital-przy-koszarowej-u-kresu-wytrzymalosci-lekarze-wywracaja-sie-ze-zmeczenia/ar/c1-15225380
