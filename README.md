# IDiS Designer

**IDiS Designer** (`I-DiS Editor.exe`) je návrhové prostredie firmy **Ineltech** na tvorbu a úpravu projektov
diagnostického a vizualizačného systému **IDiS**. Umožňuje navrhovať obrazovky (HMI), premenné, grafy,
udalosti a ďalšie prvky projektu, ktoré následne zobrazuje a vykonáva runtime aplikácia
[**IDiS RT**](https://github.com/tfeeee/Ineltech-IDiS) pripojená k zariadeniu.

Tento repozitár slúži na **distribúciu inštalačných balíkov a automatických aktualizácií** IDiS Designera
pre zaškolený personál.

## Hlavné funkcie

- návrh a editácia projektov a obrazoviek IDiS,
- definícia premenných, grafov, histórie a udalostí,
- príprava konfigurácie pre IDiS RT a spustenie projektu v runtime,
- automatická kontrola a inštalácia aktualizácií z GitHub Releases vrátane zoznamu zmien.

## Systémové požiadavky

- Windows 10 alebo novší (32-bitová aplikácia, beží aj na x64),
- administrátorské práva na inštaláciu,
- prístup na internet pre automatické aktualizácie a prípadné stiahnutie IDiS RT.

## Inštalácia

1. Otvorte stránku [Releases](https://github.com/tfeeee/Ineltech-IDiS_Designer/releases/latest).
2. Stiahnite súbor `IDiS-Designer-<verzia>-internal-setup.exe`.
   Voliteľne overte jeho kontrolný súčet podľa priloženého súboru `.sha256`.
3. Spustite inštalátor a postupujte podľa sprievodcu. Voliteľne môžete vytvoriť zástupcu na ploche.

Predvolený inštalačný priečinok: `C:\Program Files (x86)\Ineltech\IDiS`

### Vzťah k IDiS RT

IDiS RT je **samostatná aplikácia s vlastnou inštaláciou**. Inštalátor Designera:

- zistí, či je IDiS RT v počítači nainštalované a či má vyhovujúcu verziu,
- ak RT chýba alebo je staršie, stiahne zodpovedajúci release
  z [Ineltech-IDiS](https://github.com/tfeeee/Ineltech-IDiS/releases) a nainštaluje ho samostatne,
- existujúcu novšiu inštaláciu RT nemení.

Každá verzia Designera je viazaná na najvyššiu verziu RT, ktorá bola vydaná v čase vydania Designera.

## Automatické aktualizácie

Aktualizácie sa spúšťajú zo **systémového menu okna** aplikácie (kliknutie na ikonu v titulku okna
alebo `Alt+Medzerník`) položkou **„Skontrolovať aktualizácie...“**.

- Aplikácia porovná nainštalovanú verziu s najnovším releasom v tomto repozitári.
- Pred inštaláciou zobrazí **zoznam zmien (changelog)** novej verzie.
- Stiahnutý balík sa overí kontrolným súčtom SHA-256 a až potom sa spustí inštalácia.

Zoznam zmien každej verzie je tiež priložený pri releasi ako súbor `IDiS-Designer-<verzia>-changes.md`.

## Používateľské dáta

Nastavenia a dáta sa ukladajú pre každého používateľa Windows samostatne:

| Obsah | Umiestnenie |
|---|---|
| Nastavenia Designera | `%LOCALAPPDATA%\Ineltech\IDiS\Designer\InelTechEditor.ini` |
| Logy | `%LOCALAPPDATA%\Ineltech\IDiS\Designer\Logs` |
| Predvolený priečinok nových projektov | `%LOCALAPPDATA%\Ineltech\IDiS\Projects` |
| Stiahnuté aktualizácie | `%LOCALAPPDATA%\Ineltech\IDiS\Updates\Designer` |

Pri prvom spustení sa nastavenia zo staršej inštalácie (INI pri EXE súbore) jednorazovo skopírujú,
pôvodný súbor zostáva nezmenený. Existujúce projekty zostávajú na svojom pôvodnom mieste.

## Odinštalovanie

Cez **Nastavenia → Aplikácie** (alebo Ovládací panel) odinštalujte položku **IDiS Designer**.
IDiS RT sa odinštaluje samostatne. Používateľské dáta v `%LOCALAPPDATA%\Ineltech\IDiS` zostávajú zachované.

## Podpora

Aplikácia je určená pre interné použitie zaškoleným personálom. S problémami sa obracajte na
zodpovednú osobu vo firme Ineltech.
