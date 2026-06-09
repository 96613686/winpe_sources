# Microsoft.VisualStudio.Setup.LayoutConstants::.cctor

- ea: `0x14ad0`
- end: `0x14b53`
- name: `Microsoft.VisualStudio.Setup.LayoutConstants::.cctor`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0x14ad0`: `Catalog.json`
- `0x14ada`: `Catalog_cleaned.json`
- `0x14ae4`: `ChannelManifest.json`
- `0x14aee`: `Response.json`
- `0x14af8`: `Response.template.json`
- `0x14b02`: `Layout.json`
- `0x14b0c`: `vs_installer.opc`
- `0x14b3e`: `UseLatestInstaller`
- `0x14b48`: `Layout.vsconfig`

## pseudocode

```c

```

## disassembly

```asm
0x14ad0  ldstr    aCatalogJson// "Catalog.json"
0x14ad5  stsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::CatalogFileName
0x14ada  ldstr    aCatalogCleaned// "Catalog_cleaned.json"
0x14adf  stsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::CleanedCatalogFileName
0x14ae4  ldstr    aChannelmanifes_4// "ChannelManifest.json"
0x14ae9  stsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::ChannelManifestFileName
0x14aee  ldstr    aResponseJson// "Response.json"
0x14af3  stsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::ResponseFileName
0x14af8  ldstr    aResponseTempla// "Response.template.json"
0x14afd  stsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::ResponseTemplateFileName
0x14b02  ldstr    aLayoutJson// "Layout.json"
0x14b07  stsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::LayoutSettingsFile
0x14b0c  ldstr    aVsInstallerOpc_0// "vs_installer.opc"
0x14b11  stsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::InstallerOPCFile
0x14b16  ldstr    aVsSetupExe// "vs_setup.exe"
0x14b1b  stsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::BootstrapperStaticName
0x14b20  ldstr    aArchive// "Archive"
0x14b25  stsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::ArchiveFolder
0x14b2a  ldstr    aVsBootstrapper// "vs_bootstrapper_ceip"
0x14b2f  stsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::CeipEnvironmentVariable
0x14b34  ldstr    aNeutral// "neutral"
0x14b39  stsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::NeutralLanguage
0x14b3e  ldstr    aUselatestinsta// "UseLatestInstaller"
0x14b43  stsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::UseLatestInstallerCommand
0x14b48  ldstr    aLayoutVsconfig// "Layout.vsconfig"
0x14b4d  stsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::VSConfigFileName
0x14b52  ret
```
