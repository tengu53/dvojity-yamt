---
layout: post
title: Jak na rychlou přípravu typu v Jekyllu a Netlify
date: 2020-12-10 00:00:23
author: Edgar Walden
tags: [Werkzeug]
image: type.jpg
---
O generátorech statických webů jsem se poprvé dočetl nejspíš na webu Maxiorel.cz. Honza Polzer takto udělal jeden web pomocí generátoru Hugo. Tvořit přímo statické webové stránky bez nutnosti dalších technologií na serveru (PHP, MySQL) mi už tehdy přišlo docela cool. Mám rád jednoduché věci, které dělají to co mají a nic méně ale i nic více. Třeba proto tento post píšu v **geditu** a ne třeba ve Wordu. Právě proto mě myšlenka generovat statické stránky docela zaujala. Takovýto web je také super rychlý a taky nehacknutelný (no aspoň myslím).

Generátorů statických webů je spousta. Ty které jsem jen tak letmo viděl pracují přibližně na podobném principu:

1. Nainstalujete potřebný generátor
2. Někde něco nakonfigurujete, aby systém věděl, jak se bude web jmenovat atd.
3. Někam připravíte obsah - většinou v nějak formátovaném textu + obrázky
4. Spustíte generátor
5. V nějakém výstupním adresáři pak najdete vygenerovaný web, který pak někde publikujete.

Mezi nejpoužívanější generátory statických webů patří [Jekyll](https://jekyllrb.com/), napsaný v jazyce Ruby a využívá systém knihoven kódu - gems. Pokud se budete chtít s Jekyllem kamarádit trochu víc, chtě nechtě do toho trochu zabřednete, ale není to na škodu. Každopádně práce s Jekyllem je docela jednoduchá. Musíte nejdřív nainstalovat jazyk Ruby. V Ubuntu zadáte:

    sudo apt-get install ruby-full build-essential zlib1g-dev

A pak ještě v souboru .bashrc nastavíte cestu k adresáři, do něhož se budou přidávat jednotlivé gems:

    echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
    echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
    echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
    source ~/.bashrc

Ve Windows na to existuje instalátor. Pak už v terminálu zadáte:

    gem install jekyll bundler

A můžete se do toho pustit.

Ale cílem textu není ani tak poskytovat návod k Jekyllu. Na webu je spousta tutoriálů a běžně zručný člověk to bez problémů zvládne. Spíš mě zajímají výhody této technologie a pracovní workflow.

## Wordpress je mnohdy zbytečný

Nedávno jsem se nachomýtl k přípravě malého webu pro jednu instituci. Šlo o jednoduchý jednostránkový web s pár informacemi, trochou textů a obrázky. Ani se nepočítalo s tím, že by obsah na webu nějak závratně přibýval, a když už, šlo by spíš jen o drobné updaty typu změny kontaktních údajů atd. Web byl řešen na Wordpressu s jakýmsi docela komplikovaným pluginem. Výsledkem byl sicefunkční, ale značně pomalý web, přičemž jsme nevyužili hlavních výhod Wordpressu (správa autorů, správa obsahu, diskuse atd.), ale naopak jsme web zatížili nevýhodami Wordpressu, jako je dlouhé načítání stránek, hacknutelnost, potřeba updatů atd. V době, kdy vyhledávače značně preferují rychlost načítání webu, to rozhodně nebylo nejlepší řešení.

Naopak dobrý generátor statických webů by zde byl mnohem vhodnější. Vytvoří totiž samotné stránky, které pak server zobrazuje, bez nutnosti dotazů do databáze, šablonovacího systému atd. 



