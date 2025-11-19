# Fifine D6 Streamcontroller Icon Pack
Huge icon libraries converted from _.svg_ to _.png_ to use as custom button icons on [Fifine D6 Streamcontroller](https://fifinemicrophone.com/products/fifine-ampligame-d6) — more than 18k icons available in different colors fitting for any stream controller action.

## Icon Libraries Used
> [!NOTE]
> Libraries used are publicly available for download and have their licenses attached inside the pack

| Pack | Folder | Icons | Colors |
| --- | --- | --- | --- |
| [Material Design](https://github.com/Templarian/MaterialDesign) | `materialdesign` | 7447 | <a href="#"><img src="https://github.com/user-attachments/assets/55bfc76c-1ac0-497b-bddc-b6e51923ab4b" width="12" /></a><a href="#"><img src="https://github.com/user-attachments/assets/1fef8a72-85c7-4b68-97d4-9a36cdcfa296" width="12" /></a><a href="#"><img src="https://github.com/user-attachments/assets/982c4ebe-8e63-43e6-8a46-0c1839d2283e" width="12" /></a><a href="#"><img src="https://github.com/user-attachments/assets/aec85e5f-e39d-4270-8ebd-a7d3c6d9059d" width="12" /></a> |
| [Fluent UI System Icons](https://github.com/microsoft/fluentui-system-icons) | `fluentui` | 4984 | <a href="#"><img src="https://github.com/user-attachments/assets/55bfc76c-1ac0-497b-bddc-b6e51923ab4b" width="12" /></a><a href="#"><img src="https://github.com/user-attachments/assets/a886ce98-983c-4975-9718-5d40aafbf1f1" width="12" /></a> |
| [Boxicons](https://github.com/atisawd/boxicons) | `boxicons` | 3584 | <a href="#"><img src="https://github.com/user-attachments/assets/55bfc76c-1ac0-497b-bddc-b6e51923ab4b" width="12" /></a> |
| [Font Awesome Free](https://github.com/FortAwesome/Font-Awesome) | `fontawesome` | 1984 | <a href="#"><img src="https://github.com/user-attachments/assets/55bfc76c-1ac0-497b-bddc-b6e51923ab4b" width="12" /></a> |
| [HackerNoon's Pixel Icon Library](https://github.com/hackernoon/pixel-icon-library) | `pixeliconlibrary` | 450 | <a href="#"><img src="https://github.com/user-attachments/assets/55bfc76c-1ac0-497b-bddc-b6e51923ab4b" width="12" /></a> |
| Custom Test Icons | `calibrations` | 17 | <a href="#"><img src="https://github.com/user-attachments/assets/a886ce98-983c-4975-9718-5d40aafbf1f1" width="12" /></a> |

<br/>

## How to use it with Fifine D6?
1. Download the pack and place it wherever you want
2. Open Fifine Control Deck and then click on your desired button, then click on a cog below, context menu appears and then choose "Select Local File"
3. Search images in the explorer window using asterisks like `*folder*`

<br/>

## Why this pack exists?
I wanted all buttons on my D6 to look identical and functionally minimalistic, and this project achieves that by using huge experience of many talented teams that make gigantic icon packs and converting it into usable _.png_ files. All icons have consistent style, color, size, padding and format, so sometimes packs match pretty well between each other.<br/>
<br/>
Official icon packs presented in Fifine Control Deck are barely usable. Most of them are just random pictures or stolen packs, they have different unfitting icon resolutions ranging from 32x32 up to 500x500, some of them include _.gif_ versions even though D6 doesn't support _.gif_ playback on buttons, or even _.svg_ files which create a lot of artifacts when displayed on buttons. And most important — all of them are small collections of a couple of dozen of icons, and they lack icons for basic actions in Discord, OBS, Soundpad and all the other software you usually use with stream controllers.

<br/>

## How to make your own packs just like this one?
Basically all you need for an icon to look the best as possible on D6 is: 100x100 resolution, _.png_ format, no transparency — black background does the best. This way there is no rescaling happening and no transparency artifacts. If you want to convert some other _.svg_ pack you can use [ImageMagick](https://imagemagick.org/). After you install it you can manipulate images in bulk using Windows PowerShell:
> [!CAUTION]
> Before any image manipulations make backups of your assets to avoid losing them all

1. Move into the destination folder with _.svg_ files<br/>
`cd [svg-sources-path]`<br/>
2. Convert _.svg_ to 100x100 _.png_ file<br/>
`magick mogrify -background none -density 1000x1000 -resize 100x100 -format png *.svg`<br/>
3. Invert colors since most of them are black color and we need them to be white color<br/>
`magick mogrify -channel RGB -negate -format png *.png`<br/>
4. Rescale the icon inside the picture to have some space and give it a black background<br/>
`magick mogrify -scale 70x70 -gravity center -background black -extent 100x100 -format png *.png`<br/>
5. Move only converted icons into other folder for further use<br/>
`move "[source-image-path]*.png" "[destination-image-path]"`<br/>
_Additionally:_<br/>
_You can adjust brightness if icons weren't pure white or black color to make them so:_<br/>
`magick mogrify -level 15%,100%,0.90 -format png *.png`

<br/>

## To do
• Basic color variants for all monochrome icons in ~`materialdesign`~, `fluentui`, `boxicons`, `fontawesome`, `pixeliconlibrary` <br/>
• Desaturated variants for all multicolored icons in `fluentui\color`<br/>
• Restructure source `fluentui` size system to eliminate repeating icons basing from size x24 to get more icons for conversion<br/>
