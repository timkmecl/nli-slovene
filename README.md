# Logično sklepanje v naravnem jeziku za slovenščino z velikimi jezikovnimi modeli

Avtor: Tim Kmecl

Mentor: prof. dr. Marko Robnik Šikonja

---

Ta repozitorij vsebuje kodo, uporabljeno pri diplomskem delu, prevedeno podatkovno množico in povezave do naučenih modelov.

## Podatkovne množice

V direktoriju [`datasets/test_prevajalnikov/`](datasets/test_prevajalnikov/) so v treh poddirektorijih prevodi istih 1500 primerov iz učne in po 600 iz validacijske in testne množice ESNLI, strojno prevedeni z Google Prevajalnikom, prevajalnikom DeepL in [NeMo iz projekta RSDO](https://www.clarin.si/repository/xmlui/handle/11356/1736).

### ESNLIsi

Strojni prevod podatkovne množice [ESNLI](https://github.com/OanaMariaCamburu/e-SNLI)  (50.000 primerov iz učne množice, po 3.000 iz validacijske in testne, in podmnožici 4.000 oziroma 600 primerov iz učne oziroma validacijske) v slovenščino z uporabo Google Translate API so v direktoriju [`datasets/ESNLIsi/`](datasets/ESNLIsi/). Vsak primer vsebuje ID primera, razred, izvirne angleške premiso, hipotezo in razlage ter strojne prevode premise, hipoteze in prve razlage.

## Modeli

- [*SloBERTa-SINLI*](https://huggingface.co/timkmecl/sloberta-sinli) - Model [SloBERTa](https://huggingface.co/EMBEDDIA/sloberta), prilagojen na množici [SI-NLI](https://www.clarin.si/repository/xmlui/handle/11356/1707)

- [*SloBERTa-ESNLI*](https://huggingface.co/timkmecl/sloberta-esnli) - Model SloBERTa, prilagojen na ESNLIsi

- [*SloBERTa-ESNLI-SINLI*](https://huggingface.co/timkmecl/sloberta-esnli-sinli) - Model SloBERTa, prilagojen na ESNLIsi in nato na SI-NLI

## Napovedi

Generirane razlage za testno množico ESNLIsi s tremi modeli SloT5, prilagojeni na razlagah iz ESNLIsi, so v direktoriju [`napovedi/razlage`](napovedi/razlage/). Datoteke so poimenovane po modelu, ki jih je generiral. V datoteki [`explanations_sample_graded.tsv`](napovedi/razlage/explanations_sample_graded.tsv) je vzorec 50 primerov, na katerem smo razlage ocenili.

Napovedi različnih modelov na testni množici SI-NLI so v direktoriju [`napovedi/sinli`](napovedi/sinli/). Datoteke so poimenovane po modelu, ki je napovedoval, in vsebujejo njihove neobdelane izhode (prvi stolpec implikacija, drugi nevtralni in tretji kontradikcija).