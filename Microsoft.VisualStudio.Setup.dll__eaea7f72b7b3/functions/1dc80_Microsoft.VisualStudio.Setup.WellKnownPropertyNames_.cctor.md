# Microsoft.VisualStudio.Setup.WellKnownPropertyNames::.cctor

- ea: `0x1dc80`
- end: `0x1de1b`
- name: `Microsoft.VisualStudio.Setup.WellKnownPropertyNames::.cctor`
- size: `411`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0x1dc94`: `ChannelManifestId`
- `0x1dc9e`: `ChannelManifestBuildVersion`
- `0x1dcc6`: `UpdateRequiresInstallerUpdate`
- `0x1dcd0`: `HasUpdate`
- `0x1dd3e`: `AutoUpdate`
- `0x1dd5c`: `UpdateDownloadTotalSize`
- `0x1dd66`: `UpdateDownloadedSize`
- `0x1dd70`: `UpdateDownloadComplete`
- `0x1dd7a`: `UpdateDownloadVersion`
- `0x1dda2`: `LastInstallSize`
- `0x1ddac`: `LastInstallPackageCount`
- `0x1ddf2`: `RollbackExemptExtensions`
- `0x1ddfc`: `RemoveOos`
- `0x1de06`: `DisableRollback`
- `0x1de10`: `IncludeRecommended`

## pseudocode

```c

```

## disassembly

```asm
0x1dc80  ldstr    aChannelsuffix// "ChannelSuffix"
0x1dc85  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::ChannelSuffix
0x1dc8a  ldstr    aChanneltitle// "ChannelTitle"
0x1dc8f  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::ChannelTitle
0x1dc94  ldstr    aChannelmanifes_7// "ChannelManifestId"
0x1dc99  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::ChannelManifestId
0x1dc9e  ldstr    aChannelmanifes_8// "ChannelManifestBuildVersion"
0x1dca3  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::ChannelManifestBuildVersion
0x1dca8  ldstr    aChannelproduct_1// "ChannelProductVersion"
0x1dcad  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::ChannelProductVersion
0x1dcb2  ldstr    aChannelrelease// "ChannelReleasenoteUrl"
0x1dcb7  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::ChannelReleasenoteUrl
0x1dcbc  ldstr    aAdvertisedpack// "AdvertisedPackages"
0x1dcc1  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::AdvertisedPackages
0x1dcc6  ldstr    aUpdaterequires// "UpdateRequiresInstallerUpdate"
0x1dccb  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::UpdateRequiresInstallerUpdate
0x1dcd0  ldstr    aHasupdate// "HasUpdate"
0x1dcd5  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::HasUpdate
0x1dcda  ldstr    aDefaultprogram// "DefaultProgram"
0x1dcdf  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::DefaultProgram
0x1dce4  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.CommonExtensions::Nickname
0x1dce9  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::Nickname
0x1dcee  ldstr    aMigratefrom// "MigrateFrom"
0x1dcf3  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::MigrateFrom
0x1dcf8  ldstr    aProductdisplay// "ProductDisplayVersion"
0x1dcfd  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::ProductDisplayVersion
0x1dd02  ldstr    aProductkey// "ProductKey"
0x1dd07  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::ProductKey
0x1dd0c  ldstr    aProductsemanti// "ProductSemanticVersion"
0x1dd11  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::ProductSemanticVersion
0x1dd16  ldstr    aPlanfile// "PlanFile"
0x1dd1b  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::PlanFile
0x1dd20  ldstr    aAlphapackscoun// "AlphaPacksCount"
0x1dd25  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::AlphaPacksCount
0x1dd2a  ldstr    aCampaignid// "CampaignId"
0x1dd2f  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::CampaignId
0x1dd34  ldstr    aCanceled// "Canceled"
0x1dd39  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::Canceled
0x1dd3e  ldstr    aAutoupdate// "AutoUpdate"
0x1dd43  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::AutoUpdate
0x1dd48  ldstr    aOperationmode// "OperationMode"
0x1dd4d  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::OperationMode
0x1dd52  ldstr    aUseroperationm// "UserOperationMode"
0x1dd57  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::UserOperationMode
0x1dd5c  ldstr    aUpdatedownload// "UpdateDownloadTotalSize"
0x1dd61  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::UpdateDownloadTotalSize
0x1dd66  ldstr    aUpdatedownload_0// "UpdateDownloadedSize"
0x1dd6b  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::UpdateDownloadedSize
0x1dd70  ldstr    aUpdatedownload_1// "UpdateDownloadComplete"
0x1dd75  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::UpdateDownloadComplete
0x1dd7a  ldstr    aUpdatedownload_2// "UpdateDownloadVersion"
0x1dd7f  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::UpdateDownloadVersion
0x1dd84  ldstr    aBackgrounddown_1// "BackgroundDownloadDisabled"
0x1dd89  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::UserSettingKey
0x1dd8e  ldstr    aLastsuccessful// "LastSuccessfulCheckUTC"
0x1dd93  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::LastSuccessfulCheckUTC
0x1dd98  ldstr    aLastdownloadsi// "LastDownloadSize"
0x1dd9d  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::LastDownloadSize
0x1dda2  ldstr    aLastinstallsiz// "LastInstallSize"
0x1dda7  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::LastInstallSize
0x1ddac  ldstr    aLastinstallpac// "LastInstallPackageCount"
0x1ddb1  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::LastInstallPackageCount
0x1ddb6  ldstr    aLastselections// "LastSelectionState"
0x1ddbb  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::LastSelectionState
0x1ddc0  ldstr    aLastexecuteact// "LastExecuteAction"
0x1ddc5  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::LastExecuteAction
0x1ddca  ldstr    aLastuserreques// "LastUserRequestedAction"
0x1ddcf  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::LastUserRequestedAction
0x1ddd4  ldstr    aLastappliedpac// "LastAppliedPackageId"
0x1ddd9  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::LastAppliedPackageId
0x1ddde  ldstr    aLastoperations// "LastOperationState"
0x1dde3  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::LastOperationState
0x1dde8  ldstr    aIspredynamicen// "IsPreDynamicEndpoint"
0x1dded  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::IsPreDynamicEndpoint
0x1ddf2  ldstr    aRollbackexempt// "RollbackExemptExtensions"
0x1ddf7  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::RollbackExemptExtensions
0x1ddfc  ldstr    aRemoveoos// "RemoveOos"
0x1de01  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::RemoveOosProperty
0x1de06  ldstr    aDisablerollbac// "DisableRollback"
0x1de0b  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::DisableRollbackProperty
0x1de10  ldstr    aIncluderecomme// "IncludeRecommended"
0x1de15  stsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::IncludeRecommendedProperty
0x1de1a  ret
```
