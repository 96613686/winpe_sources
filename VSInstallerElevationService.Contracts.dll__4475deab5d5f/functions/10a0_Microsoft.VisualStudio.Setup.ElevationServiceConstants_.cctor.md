# Microsoft.VisualStudio.Setup.ElevationServiceConstants::.cctor

- ea: `0x10a0`
- end: `0x10dd`
- name: `Microsoft.VisualStudio.Setup.ElevationServiceConstants::.cctor`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x10a0`: `VSInstallerElevationService.exe`
- `0x10aa`: `Visual Studio Installer Elevation Service`
- `0x10b4`: `This service is responsible for elevating the Visual Studio Installer.`
- `0x10be`: `SOFTWARE\Microsoft\VisualStudio\Setup\VSInstallerElevationService`
- `0x10d2`: `VSInstallerElevationService`

## pseudocode

```c

```

## disassembly

```asm
0x10a0  ldstr    aVsinstallerele// "VSInstallerElevationService.exe"
0x10a5  stsfld   string Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceExeName
0x10aa  ldstr    aVisualStudioIn// "Visual Studio Installer Elevation Servi"...
0x10af  stsfld   string Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceDisplayName
0x10b4  ldstr    aThisServiceIsR// "This service is responsible for elevati"...
0x10b9  stsfld   string Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceDescription
0x10be  ldstr    aSoftwareMicros// "SOFTWARE\\Microsoft\\VisualStudio\\Setu"...
0x10c3  stsfld   string Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceRegistryKey
0x10c8  ldstr    aPipename_0// "PipeName"
0x10cd  stsfld   string Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServicePipeNameRegistryValue
0x10d2  ldstr    aVsinstallerele_0// "VSInstallerElevationService"
0x10d7  stsfld   string Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceName
0x10dc  ret
```
