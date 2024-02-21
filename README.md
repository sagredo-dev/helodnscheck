# helodnschek

`qmail-spp helodnscheck` plugin which denies clients with one of these particular DNS failures:
- HELO/EHLOs domains with an invalid syntax. Random strings but also typing errors like sagredo..eu will be banned.
- fake HELO/EHLOs containing one of our domains, when RELAYCLIENT is NOT set and the HELO/EHLO matches one of our IPs. You can safely turn on this one.
- not solving HELO/EHLOs domains (no A record). You'll get some false positive if you turn this on, as clients whose administrator forgot to add the A record will be banned.
- clients whose remote IP doesn't match the A record. This is completely against RFC-821.

## More info
You can read more info and ask for support [here](https://notes.sagredo.eu/en/qmail-notes-185/denying-bad-dns-heloehlos-255.html).

## Credits 
I derived this program from an [original work of Perolo Silantico, Jason Frisvold with modifications by Ren Bing](https://qmail-spp.sourceforge.net/plugins/details/?id=33).
