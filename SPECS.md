sefpils
=======

Kode for SEFpils9000

Forside : header ascii art, statistikk, commandolinje, output felt. Tastekombinasjon for meny? Tastekombinasjon for kriting

Når tastekombinasjon for kriting er trykket, må passord også tastes inn for å registrere kjøp

Statistikk: antall solgte enheter siste 24timer. 10 Siste kjøp.

Kommandolinje : tar inn produktid, deretter bibsysnummer evt brukernavn - salg registreres. Når tastekombinasjon for kriting er trykket, må passord også tastes inn for å registrere kjøp. 


Output: skriver ut om transaksjonen var vellykket. Evt hva som gikk galt.


Meny: statistikk, legg til varer(admin), ny bruker, Skriv ut (admin)

  Statistikk:
	
Legg til varer: (krever admin login), tar inn produktnummer  og antall , switch dersom	det er en ny type vare, tar da inn også utsalgspris på varen og innkjøpspris

Ny bruker: Tar inn navn, brukernavn, bibsysnummer, epost, passord repeat passord

Skriv ut: (admin) Skriver ut oppsummering av alle salg siden siste utskrift 
	Totalt salg fra hvert produkt, total innkjøpspris, total inntekt , differanse.
	Liste over hvor mye styremedlemmer skylder fra kriting.
	Dato fra – til
	Burde kunne  generere txtfil/pdf sende på mail til leder/økonomiansvarlig

Fjern kriting: brukernavn/bibsys til kriteperson,  brukernavn/bibsys til annet styremedlem passord til annet styremedlem




Funksjoner(Notater):

Bruk overloaded funksjoner for å teste brukernavn/bibsys  egen admin funksjon for å teste admin 
	

Tabeller:

ProduktDB
------------------------------------------------------------------------------
Produktid	  |  Produktnr	| Produktnavn |	Beholdning  |	Innpris |	Utpris  |		
--------------------------------------------------------------------------------							
PRIMARY KEY |  INT(11)    | VARCHAR	    |  INT(11)	  | FLOAT	  | FLOAT   |
AUTO INC	  |             |             |             |         |         |
----------------------------------------------------------------------------------
TransaksjonerDB
--------------------------------------------------------------------------------
TransID	    |Type       |	Userid  |	Produktid |	Ant |	Dato      | Utskrevet |	
----------------------------------------------------------------------------------
            |	0 = salg, |         |           |     |           |           |
            | 1= krite, |         |           |     |           |           |
            |2 = påfyll |         |           |     |           |           |
--------------------------------------------------------------------------------------
PRIMARY KEY | INT       | INT     | INT       | INT | TIMESTAMP | Timestamp |
AUTO INC	  |           |         |	          |     |	          |	          |
-----------------------------------------------------------------------------------------
