# Microsoft.VisualStudio.Setup.RemoteSettingsConstants::.cctor

- ea: `0xb840`
- end: `0xb931`
- name: `Microsoft.VisualStudio.Setup.RemoteSettingsConstants::.cctor`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0xb840`: `RemoteSettings_Installer.json`
- `0xb854`: `Installer\Features`
- `0xb85e`: `Installer\Variables`
- `0xb8b8`: `UpdateCheckOnlyFailureLogLimit`
- `0xb8fe`: `DisableElevationService`
- `0xb908`: `DisableMsiZap`
- `0xb912`: `ConfigExtensions`
- `0xb91c`: `NgenCommand`

## pseudocode

```c

```

## disassembly

```asm
0xb840  ldstr    aRemotesettings// "RemoteSettings_Installer.json"
0xb845  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::RemoteSettingsFileName
0xb84a  ldstr    aVsSetupengine// "vs-setupengine"
0xb84f  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::EngineExeName
0xb854  ldstr    aInstallerFeatu// "Installer\\Features"
0xb859  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::FeaturesPath
0xb85e  ldstr    aInstallerVaria// "Installer\\Variables"
0xb863  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::VariablesPath
0xb868  ldstr    aBackgrounddown// "BackgroundDownload"
0xb86d  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::BackgroundDownload
0xb872  ldstr    aBatterypercent// "BatteryPercentage"
0xb877  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::BatteryPercentage
0xb87c  ldstr    aDiskspaceperce// "DiskSpacePercentageRemaining"
0xb881  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::DiskSpacePercentageRemaining
0xb886  ldstr    aDiskspacesizer// "DiskSpaceSizeRemaining"
0xb88b  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::DiskSpaceSizeRemaining
0xb890  ldstr    aSuccessloglimi// "SuccessLogLimit"
0xb895  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::SuccessLogLimit
0xb89a  ldstr    aErrorloglimit// "ErrorLogLimit"
0xb89f  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::ErrorLogLimit
0xb8a4  ldstr    aCancelloglimit// "CancelLogLimit"
0xb8a9  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::CancelLogLimit
0xb8ae  ldstr    aPrecheckfailur// "PrecheckFailureLogLimit"
0xb8b3  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::PrecheckFailureLogLimit
0xb8b8  ldstr    aUpdatecheckonl// "UpdateCheckOnlyFailureLogLimit"
0xb8bd  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::UpdateCheckOnlyFailureLogLimit
0xb8c2  ldstr    aConcurrentdown// "ConcurrentDownloads"
0xb8c7  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::ConcurrentDownloads
0xb8cc  ldstr    aNotenoughspace// "NotEnoughSpaceErrorBytes"
0xb8d1  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::NotEnoughSpaceErrorBytes
0xb8d6  ldstr    aNotenoughspace_0// "NotEnoughSpaceErrorPercent"
0xb8db  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::NotEnoughSpaceErrorPercent
0xb8e0  ldstr    aTelemetrysampl// "TelemetrySamplingPercentage"
0xb8e5  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::TelemetrySamplingPercentage
0xb8ea  ldstr    aIfmodifiedsinc// "IfModifiedSince"
0xb8ef  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::IfModifiedSinceKey
0xb8f4  ldstr    aAuthentication// "Authentication"
0xb8f9  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::AuthenticationKey
0xb8fe  ldstr    aDisableelevati// "DisableElevationService"
0xb903  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::DisableElevationService
0xb908  ldstr    aDisablemsizap// "DisableMsiZap"
0xb90d  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::DisableMsiZap
0xb912  ldstr    aConfigextensio// "ConfigExtensions"
0xb917  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::ConfigExtensions
0xb91c  ldstr    aNgencommand// "NgenCommand"
0xb921  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::NgenCommand
0xb926  ldstr    aEnablehybridba// "EnableHybridBackgroundDownload"
0xb92b  stsfld   string Microsoft.VisualStudio.Setup.RemoteSettingsConstants::EnableHybridBackgroundDownload
0xb930  ret
```
