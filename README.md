# Linkpool Ci Challenge

Mit dem kleinen Linkpool Projekt sind wir jetzt in der Lage via Hugo unterschiedliche Repräsentationen des Contents zu erzeugen. Das ist schon mal toll. Wir wollen mit dem Projekt am Ende isomorphes Rendering realisieren und der Dozent hat sich in den Kopf gesetzt, den Content via GitHub pflegbar zu machen und via Github.io bereit zu stellen.

Leider kann Github.io nur Jekyll generieren. Da wir aber Hugo als Static Page Generator im Einsatz haben, müssen wir den Build Prozess auslagern. Und schon sind wir mitten im Thema Continuous Integration.

Bei der konkreten Challenge geht es darum, einen Prozess zu implementieren, in dem via [Travis-CI](https://travis-ci.org/) automatisiert ein Build vollzogen (und später auch mal getestet) wird und dann die ausgespielten Inhalte auf der zugehörigen GitHub.io Seite zugänglich gemacht werden.

Mal in Pseudocode gesprochen:

```
onPush@github.com/repo
  create Environment
  hugo --destination docs
  git add .
  git commit -m "created content build {Buildnumber}"
  git push origin master

```

Alles klar?
