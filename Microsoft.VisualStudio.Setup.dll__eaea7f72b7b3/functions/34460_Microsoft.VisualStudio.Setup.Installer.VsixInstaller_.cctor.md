# Microsoft.VisualStudio.Setup.Installer.VsixInstaller::.cctor

- ea: `0x34460`
- end: `0x34537`
- name: `Microsoft.VisualStudio.Setup.Installer.VsixInstaller::.cctor`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0x3446e`: `manifest.json`
- `0x34491`: `catalog.json`
- `0x344be`: `extension.vsixmanifest`

## pseudocode

```c

```

## disassembly

```asm
0x34460  ldc.i4.s 0x2F
0x34462  stsfld   char Microsoft.VisualStudio.Setup.Installer.VsixInstaller::AltDirectorySeparatorChar
0x34467  ldc.i4.s 0x5C
0x34469  stsfld   char Microsoft.VisualStudio.Setup.Installer.VsixInstaller::DirectorySeparatorChar
0x3446e  ldstr    aManifestJson// "manifest.json"
0x34473  stsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ManifestName
0x34478  ldsflda  char Microsoft.VisualStudio.Setup.Installer.VsixInstaller::AltDirectorySeparatorChar
0x3447d  call     instance string [mscorlib]System.Char::ToString()
0x34482  ldsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ManifestName
0x34487  call     string [mscorlib]System.String::Concat(string, string)
0x3448c  stsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ManifestPath
0x34491  ldstr    aCatalogJson_0// "catalog.json"
0x34496  stsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::CatalogName
0x3449b  ldsflda  char Microsoft.VisualStudio.Setup.Installer.VsixInstaller::AltDirectorySeparatorChar
0x344a0  call     instance string [mscorlib]System.Char::ToString()
0x344a5  ldsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::CatalogName
0x344aa  call     string [mscorlib]System.String::Concat(string, string)
0x344af  stsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::CatalogPath
0x344b4  ldsflda  char Microsoft.VisualStudio.Setup.Installer.VsixInstaller::AltDirectorySeparatorChar
0x344b9  call     instance string [mscorlib]System.Char::ToString()
0x344be  ldstr    aExtensionVsixm// "extension.vsixmanifest"
0x344c3  call     string [mscorlib]System.String::Concat(string, string)
0x344c8  stsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::VsixManifestPath
0x344cd  ldsflda  char Microsoft.VisualStudio.Setup.Installer.VsixInstaller::AltDirectorySeparatorChar
0x344d2  call     instance string [mscorlib]System.Char::ToString()
0x344d7  ldstr    aContents_0// "Contents"
0x344dc  ldsflda  char Microsoft.VisualStudio.Setup.Installer.VsixInstaller::AltDirectorySeparatorChar
0x344e1  call     instance string [mscorlib]System.Char::ToString()
0x344e6  call     string [mscorlib]System.String::Concat(string, string, string)
0x344eb  stsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::RootDirectory
0x344f0  ldstr    aCertificateinf// "CertificateInformation.dat"
0x344f5  stsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::CertificateInformationFileName
0x344fa  ldstr    asc_828F4// ","
0x344ff  stsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::CsvDelimeter
0x34504  ldstr    asc_8B518// "\""
0x34509  stsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::Quote
0x3450e  ldstr    aUrlassociation// "UrlAssociations"
0x34513  stsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::urlAssociationName
0x34518  ldstr    aFileassociatio// "FileAssociations"
0x3451d  stsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::fileAssociationName
0x34522  ldstr    aApplicationdes// "ApplicationDescription"
0x34527  stsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::applicationDescriptionName
0x3452c  ldstr    aApplicationnam// "ApplicationName"
0x34531  stsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::applicationName
0x34536  ret
```
