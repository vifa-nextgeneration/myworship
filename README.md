### Obtain ProPresenter Support Files
1. Download this repository as a ZIP file [here](https://github.com/vifa-nextgeneration/ProPresenter/archive/refs/heads/ApartemenRobinson.zip).
2. Decompress the `ProPresenter-ApartemenRobinson.zip` file using an archive manager.
3. Rename the `ProPresenter-ApartemenRobinson` folder to `ProPresenter`.
### Utilize ProPresenter Support Files
1. Launch the ProPresenter program at least once after a clean Windows installation.
2. Complete the "Welcome To ProPresenter" first-launch wizard using the default options.
3. Close the ProPresenter program.
4. Delete the default `ProPresenter` folder located in `C:\Users\NXGN\Documents`.
5. Move the previously renamed `ProPresenter` folder to `C:\Users\NXGN\Documents`.
### Restore `desktop.ini` System File Attribute
Fourteen folders contain a `desktop.ini` file responsible for folder icons. To ensure Windows recognizes this file, perform the following steps for each occurrence:
1. Open the `desktop.ini` file in Notepad. Press the <kbd>Space</kbd> key once, followed by the <kbd>Backspace</kbd> key.
2. Open the Properties of the containing folder. Go to the "Customize" tab, then click "Change Icon" and click "OK".
3. Simultaneously press the <kbd>Enter</kbd> key in the Properties window and the <kbd>Ctrl</kbd>+<kbd>S</kbd> key in the Notepad window.
### Enable NTFS Long Paths
Some folder names exceed the length supported by the default Windows configuration. To enable support for such folders, save the following code as a `.reg` file and open it:
  ```
  Windows Registry Editor Version 5.00

  [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\FileSystem]
  "LongPathsEnabled"=dword:00000001
  ```
  > Tip: Restart your computer for the change to take effect.
### Enable Microsoft PowerPoint Maximum Resolution Save Behavior
The default Microsoft Office configuration only saves PPTX documents as images up to 1920 × 1080 resolution. To save PPTX documents as images (`.jpeg` recommended) with the maximum resolution possible, save the following code as a `.reg` file and open it:
  ```
  Windows Registry Editor Version 5.00

  [HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\16.0\PowerPoint\Options]
  "ExportBitmapResolution"=dword:000003e8
  ```
  > Tip: Relaunch Microsoft PowerPoint for the change to take effect.
### Configure Adobe Acrobat Maximum Resolution Save Settings
The default Adobe Acrobat settings only save PDF documents as images up to 1920 × 1080 resolution. To save PDF documents as images (`.jpeg` recommended) with the maximum resolution possible, configure the save settings as follows:
<table><tr><th colspan="2">File Settings</th></tr><tr><td>Grayscale</td><td>JPEG (Quality : Maximum)</td></tr><tr><td>Color</td><td>JPEG (Quality : Maximum)</td></tr><tr><td>Format</td><td>Progressive (5 Scans)</td></tr><tr><th colspan="2">Color Management</th></tr><tr><td>RGB</td><td>Embed profile</td></tr><tr><td>CMYK</td><td>Off</td></tr><tr><td>Grayscale</td><td>Off</td></tr><tr><td>Other</td><td>Not applicable</td></tr><tr><th colspan="2">Conversion</th></tr><tr><td>Colorspace</td><td>Color: RGB</td></tr><tr><td>Resolution</td><td>819 pixels/inch</td></tr></table>

> Tip: If the save fails, switch the Resolution to 600 pixels/inch first by choosing from the dropdown menu. Then, change it back to the Resolution of 819 pixels/inch by manually typing it.
### Recreate Testing Images
On the `Added Manually\02 Playlists\01 🖼️ Backgrounds\04 🚧 Testing` folder `black.png` and `white.png` must be created manually. With the color of `#000000` and `#ffffff` respectively.
### Batch Scripts Usage
|`MediaExport.cmd`|`MediaImport.cmd`|
|-|-|
|Empties the `Media\Assets` folder by moving each media file into the respective `Added Manually` subfolders.|Populates the `Media\Assets` folder by moving each media file out of the respective `Added Manually` subfolders.|
### Remarks
- All `.lnk` and `.url` files are safe to delete in an active production environment, as they do not affect availability.
- All [Releases](https://github.com/vifa-nextgeneration/ProPresenter/releases) contain archive files with media larger than 100 MiB.
