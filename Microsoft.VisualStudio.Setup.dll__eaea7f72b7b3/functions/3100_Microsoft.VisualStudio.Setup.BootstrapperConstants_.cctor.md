# Microsoft.VisualStudio.Setup.BootstrapperConstants::.cctor

- ea: `0x3100`
- end: `0x3197`
- name: `Microsoft.VisualStudio.Setup.BootstrapperConstants::.cctor`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x310a`: `vs_installer`
- `0x311e`: `autoSelfUpdateMinVersion`
- `0x3128`: `vs_installer.version.json`
- `0x3132`: `Microsoft Visual Studio\Installer`
- `0x3146`: `vs_installer.exe`
- `0x3150`: `Microsoft Visual Studio\VSUpdater`
- `0x315a`: `VSUpdaterBootstrapper.exe`
- `0x3178`: `user.json`
- `0x3182`: `resources\app\ServiceHub\Services\Microsoft.VisualStudio.Setup.Service`
- `0x318c`: `Microsoft.VisualStudio.Installer`

## pseudocode

```c

```

## disassembly

```asm
0x3100  ldstr    aResourcesAppLa// "resources\\app\\layout"
0x3105  stsfld   string Microsoft.VisualStudio.Setup.BootstrapperConstants::CliRelativePath
0x310a  ldstr    aVsInstaller// "vs_installer"
0x310f  stsfld   string Microsoft.VisualStudio.Setup.BootstrapperConstants::SetupProcessName
0x3114  ldstr    aRootcertcreati// "rootCertCreationFailed"
0x3119  stsfld   string Microsoft.VisualStudio.Setup.BootstrapperConstants::RootCertCreationFail
0x311e  ldstr    aAutoselfupdate// "autoSelfUpdateMinVersion"
0x3123  stsfld   string Microsoft.VisualStudio.Setup.BootstrapperConstants::AutoSelfUpdateMinVersion
0x3128  ldstr    aVsInstallerVer// "vs_installer.version.json"
0x312d  stsfld   string Microsoft.VisualStudio.Setup.BootstrapperConstants::VsInstallerVersionFilename
0x3132  ldstr    aMicrosoftVisua_0// "Microsoft Visual Studio\\Installer"
0x3137  stsfld   string Microsoft.VisualStudio.Setup.BootstrapperConstants::InstallerSubDirectory
0x313c  ldstr    aSetupExe// "setup.exe"
0x3141  stsfld   string Microsoft.VisualStudio.Setup.BootstrapperConstants::InstallerFileName
0x3146  ldstr    aVsInstallerExe// "vs_installer.exe"
0x314b  stsfld   string Microsoft.VisualStudio.Setup.BootstrapperConstants::LegacyInstallerFileName
0x3150  ldstr    aMicrosoftVisua_1// "Microsoft Visual Studio\\VSUpdater"
0x3155  stsfld   string Microsoft.VisualStudio.Setup.BootstrapperConstants::VSUpdaterSubDirectory
0x315a  ldstr    aVsupdaterboots// "VSUpdaterBootstrapper.exe"
0x315f  stsfld   string Microsoft.VisualStudio.Setup.BootstrapperConstants::VSUpdaterFileName
0x3164  ldstr    aCancelPrompt// "Cancel Prompt"
0x3169  stsfld   string Microsoft.VisualStudio.Setup.BootstrapperConstants::PromptWarnName
0x316e  ldstr    aVisualStudioSe// "Visual Studio Setup"
0x3173  stsfld   string Microsoft.VisualStudio.Setup.BootstrapperConstants::UserSettingsSubDirectory
0x3178  ldstr    aUserJson// "user.json"
0x317d  stsfld   string Microsoft.VisualStudio.Setup.BootstrapperConstants::UserSettingsFileName
0x3182  ldstr    aResourcesAppSe// "resources\\app\\ServiceHub\\Services\\M"...
0x3187  stsfld   string Microsoft.VisualStudio.Setup.BootstrapperConstants::RelativeEnginePath
0x318c  ldstr    aMicrosoftVisua_2// "Microsoft.VisualStudio.Installer"
0x3191  stsfld   string Microsoft.VisualStudio.Setup.BootstrapperConstants::LegacyInstallerAppUserModelId
0x3196  ret
```
