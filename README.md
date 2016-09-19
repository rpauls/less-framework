# LESS-framework
A basic less framework inspired by [PureCSS](http://purecss.io/).

## GRID
The framework contains a responsive (mobile-first) 12-column grid.

__Breakpoints__

| Screen | Size _(rem)_ | Size _(px)_ | Variable name |
| --- | --- | --- | --- |
| Smartphone _(sm)_ | 35.5rem | ~ 568px | `@smartphone-viewport-width` |
| Tablet _(md)_ | 48rem | ~ 768px | `@tablet-viewport-width` |
| Desktop _(lg)_ | 64rem | ~ 1024px | `@desktop-viewport-width` |
| Larger | 80rem | ~ 1280px | `@larger-viewport-width` |

All Breakpoints can be adjusted through the `_variables.less`.

__Grid HTML Markup__
Das Grid baut sich aus drei Typen verschachtelter Basis-Blockelemente auf. Das Container-Element, die Grid-Zeile, sowie die Grid-Spalte.

```html
<div class="container">

    <div class="g-row pb-15">
        <div class="g-col-sm-12">
            // CONTENT
        </div>
    </div>
</div>
```

__Grid Container__
Die CSS-Klasse `.container` besitzt eine fixierte Maximalbreite _(_`@container-width`_)_, ein horizontales Padding _(_`@col-offset`_)_ und wird automatisch horizontal zentriert.
Soll das Container_Element die gesamte Breite _(100%)_ einnehmen, so steht die CSS-Klasse `.container-full` zur Verfügung, welche lediglich ein horizontales Padding  _(_`@col-offset`_)_ besitzt.


__Grid Spalten__
Eine Grid-Spalte muss mindestens die CSS-Klasse für die kleinste Displayauslösung _(sm)_ innehaben, kann dann entsprechend um weitere CSS-Klassen für größere Displayauflösung  ergänzt werden.


_Minimales Markup:_
```html
    <div class="g-col-sm-12">
        //CONTENT
    </div>
```

_Optimales Markup:_
```html
    <div class="g-col-sm12 g-col-md-6 g-col-lg-3">
        // CONTENT
    </div>
```

| Small | Medium | Large |  
| --- | --- | --- |
| `g-col-sm-1` | `g-col-md-1` | `g-col-lg-1` |
| `g-col-sm-2` | `g-col-md-2` | `g-col-lg-2` |
| `g-col-sm-3` | `g-col-md-3` | `g-col-lg-3` |
| `g-col-sm-4` | `g-col-md-4` | `g-col-lg-4` |
| `g-col-sm-5` | `g-col-md-5` | `g-col-lg-5` |
| `g-col-sm-6` | `g-col-md-6` | `g-col-lg-6` |
| `g-col-sm-7` | `g-col-md-7` | `g-col-lg-7` |
| `g-col-sm-8` | `g-col-md-8` | `g-col-lg-8` |
| `g-col-sm-9` | `g-col-md-9` | `g-col-lg-9` |
| `g-col-sm-10` | `g-col-md-10` | `g-col-lg-10` |
| `g-col-sm-11` | `g-col-md-11` | `g-col-lg-11` |
| `g-col-sm-12` | `g-col-md-12` | `g-col-lg-12` |

__Grid Spalten Offset__
Spalten lasen sich innerhalb einer Grid-Zeile mittels der Offset-Klassen verschieben um Abstände _(margin-left)_ zu erzeugen. Hierzu existieren für jede Spalten- und Screen-Größe entsprechende Offset-Klassen welche nach dem folgenden Schema aufgebaut sind:

```
    g-{breakpoint}-offset-{columns}
```

Somit ergibt sich für ein Beispielhaftes Offset auf Bildschirmen mit Desktop-Größe oder hoher sowie einer Breite von 2 Spalten folgende Offset-Klasse:
```
    g-lg-offset-2
```

---

## Unterstützende Klassen
Um den schnellen Aufbau eines sinnvolles HTML-Markups zu vereinfachen und unnötige Umwege über zusätzliche CSS-Definitionen zu vermeiden, existieren zahlreiche unterstüzende CSS-Klassen.

__Hidden Elements__
Elemente lassen sich abhängig von den aktuellen Breakpoints ausblenden.

| Small | Medium | Large |
| --- | --- | --- |
| `.hidden-sm` | `.hidden-md` | `.hidden-lg` |


__Vertikale Margins und Paddings__
Vertikale Innen- und Außenabstände von Elementen lassen sich durch das Verwenden der folgender CSS-Klassen beinflussen:

| Margin-Top | Margin-Bottom | Padding-Top | Padding-Bottom |
| --- | --- | --- | --- |
| `.mt-{size}` | `.mb-{size}` | `.pt_{size}` | `.pb-{size}` |

Die vordefinierten CSS-Klassen liegen mit 5px Differenzen zwischen dem geringsten Abstand von 5px bis zu einem höchsten Abstand von 50px.

__Keine Margins und Padding__
Innen- und Außenabstände von Elementen lassen sich durch die Verwendung folgender CSS-Klassen unterbinden:

| Margin | Padding | Direction |
| --- | --- | --- |
| `.no-marg` | `.no-padd` | Vertical & Horizontal |
| `.no-marg-v` | `.no-padd-v` | Vertical |
| `.no-marg-h` | `.no-padd-h` | Horizontal |

__Text Klassen__

| Font-Weight | Text-Decoration | Text-Transform | Text-Align |
| --- | --- | --- | --- |
| `.text-normal` | `.text-underline` | `.text-uppercase` | `.text-right` |
| `.text-bold` | `.text-overline` | `.text-lowercase` | `.text-center` |
| `.text-bolder` | `.text-linethrough` | `.text-capitalze` | `.text-left` |
| `.text-light` | `.text-none` |  |  |

__Responsive Image__
Die CSS-Klasse `.is-responsive` ermöglicht img-Elementen eine automatische Größenanpassung abhängig von der Bildschirmgröße und Bildschirmauflösung.

---

## FORM ELEMENTS
Alle Form-Einzelelemente benötigen einen umfassenden form-Block um fehlerfrei dargestellt zu werden. Dieser Form-Block sollte die CSS-Klassen `.forms`,  `.form-stack` und `.form-input-full` besitzen.

```html
<form class="forms form-stack form-input-full">
    //FORM CONTENT
</form>
```

__Input__
```html
<form class="forms form-stack">
    <label for="text1">Text input</label>
    <input type="text" id="text1">
</form>
```

__Select__ _(Dropdown)_
```html
<form class="forms form-stack">
    <label for="select1">Dropdown (Select) <span class="color-silver">*</span></label>
    <select class="form-dropdown" id="select1">
        <option>Opt #1</option>
        <option>Opt #2</option>
        <option>Opt #3</option>
    </select>
</form>
```

Es gilt beim select-Element zu beachten, das für Internet Explorer Version 9 und geringer folgendes Conditional-Statement in den Header der HTML-Dateien eingefügt werden sollte.
Dies umgeht einige fehlende CSS-Implementierungen im IE und sorgt für eine fehlerfreie Darstellung des Elements.


__Form Layout: Inline__
Wird für den umfassenden form-Block nur die CSS-Klasse `.forms` verwendet, so werden alle Form-Einzelelemente inline angeordnet.

__Form Layout: Stack__
Werden für den umfassenden form-Block die beiden CSS-Klassen `.forms` und `.form-stack` verwendet, so werden alle Form-Einzelelemente untereinander angeordnet.

__Grouped Inputs__
Input-Elemente können, in einem div-Container mit der CSS-Klasse `.form-group` eingefasst, zu einem vertikal zusammenhängenden Input-Block angeordnet werden.

__Input Breite__
Die CSS-Klasse `.form-input-full` ermöglicht es allen input-Elementen in einem form-Block eine Breite von 100% anzunehmen.

```html
<!--[if lt IE 10]>
    <style>
        select.form-dropdown {
            background-image: none !important;
            width: 100%;
            padding-right: 0px !important;
        }
    </style>
<![ENDIF]-->
```

---

## BUTTONS
The pre-defined button styles can be applied to button elements, as well as link elements (`<a>`).

```html
<button class="btn">Button text</button>
```

```html
<a class="btn">Button text</a>
```
__Farbgebung__
The color of the button elements can be influenced by the css class `btn-scondary` _(Background & Color)_.
LESS variables to edit the default colors can be found in the file `_variables.less`.
```html
<button class="btn btn-secondary">Button text</button>
```

__Maximale Breite__
The width of the button elements adjusts itself automatically based upon its content.
Using the css class `btn-width-full`, it is possible to set the width of a button element to the maximum available width _(100%)_.
```html
<button class="btn btn-width-full">Button text</button>
```

__Hover__
All buttons have a default Hover-Style.
Using the css class `.btn-hover`, the default Hover-Style can be used without a default hover event.

__Disabled__
All buttons have a default Disabled-Style.
Using the css class `.btn-disabled`, the default Disabled-Style can be used without a default disabled-Attribute.


---

## WEITERE ELEMENTE

__Divider with centered title__
```html
<div class="divider">
    <div class="divider-line"><h2>Divider with centered title</h2></div>
</div>
```

__Headings__

| Heading | Size |
| --- | --- |
| h1 | 36px |
| h2 | 30px |
| h3 | 24px |
| h4 | 18px |
| h5 | 14px |
| h6 | 12px |

---

## LESS DIRECTORY STRUCTURE
All LESS-Files are located within the directory `resources/css/`.

- `modules/` : Contains all definitions of Default-elements and the basic less framework.
    - `(...)`
- `partials/` : Contains all page- and content-specific definitions.
    - `_base.less` : Base definitions for all pages.
- `vendor/` : Contains external less files/libraries.
    - `_normalize.less` : [Normalize.css](https://necolas.github.io/normalize.css/) - Consistent browser independent rendering of html elements.
    - `_elements.less` : [LESS Elements](http://lesselements.com/) - LESS library containing helpful mixins.  
- `main.less` : Imports all individual less files, contains no direct definitions.
