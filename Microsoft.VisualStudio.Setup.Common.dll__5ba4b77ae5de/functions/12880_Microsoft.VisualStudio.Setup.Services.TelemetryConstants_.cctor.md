# Microsoft.VisualStudio.Setup.Services.TelemetryConstants::.cctor

- ea: `0x12880`
- end: `0x13ed9`
- name: `Microsoft.VisualStudio.Setup.Services.TelemetryConstants::.cctor`
- size: `5721`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x13db1`: `extensions`
- `0x13069`: `InstallCatalogUri`
- `0x12911`: `updateDownloadComplete`
- `0x12925`: `updateDownloadTotalSize`
- `0x12939`: `updateDownloadedSize`
- `0x1294d`: `updateDownloadVersion`
- `0x12975`: `InstallFailedPackageCount`
- `0x12989`: `UninstallFailedPackageCount`
- `0x129ed`: `InstallPathChanged`
- `0x12add`: `ChannelsPath`
- `0x12af1`: `ChannelsId`
- `0x12b05`: `ChannelsUri`
- `0x12b19`: `ComponentId`
- `0x12bcd`: `UpdateFromVS`
- `0x12c09`: `SharedWillowInstallSessionId`
- `0x12c81`: `create-public-client-app-builder`
- `0x12d21`: `report-widowsupdateprogress`
- `0x12d71`: `HasUpdate`
- `0x12dc1`: `IsUpdateCheckOnly`
- `0x12e39`: `UpdateVersion`
- `0x12e75`: `updateconfiguration`
- `0x12e89`: `updateconfiguration-perinstance`
- `0x12f79`: `Catalog.Uri`
- `0x12fdd`: `NewChannelManifestVersion`
- `0x12ff1`: `OldChannelManifestVersion`
- `0x13019`: `EngineUpdateRequired`
- `0x1302d`: `InstallChannelUri`
- `0x13041`: `InstallChannelDownloaded`
- `0x13055`: `InstallChannelManifestVersion`
- `0x1307d`: `ChannelUpdateDisabled`
- `0x13091`: `ManifestUpdate`
- `0x130a5`: `ReadyForManifestDownload`
- `0x130b9`: `FinishedManifestDownload`
- `0x130cd`: `WasManifestModified`
- `0x131bd`: `CatalogManifestType`
- `0x131d1`: `CatalogManifestVersion`
- `0x1320d`: `install.`
- `0x13235`: `.MSIZap`
- `0x13249`: `.MSIZapDisabled`
- `0x13415`: `ManifestId`
- `0x134a1`: `FinalUri`
- `0x13505`: `WebClientDownloadCompleted`
- `0x135a5`: `BearerTokenNull`
- `0x137d5`: `WindowsUpdateStopFailed`
- `0x137e9`: `WindowsUpdateStartFailed`
- `0x13861`: `InstallBusyPrompt`
- `0x13a69`: `componentsAdded`
- `0x13a7d`: `componentsInstalled`
- `0x13a91`: `downloadtheninstall`
- `0x13ab9`: `installsessionid`
- `0x13acd`: `installWhileDownloading`
- `0x13b09`: `nocache`
- `0x13b1d`: `noupdateinstaller`
- `0x13b6d`: `previewupdate`
- `0x13ba9`: `updatefromvs`
- `0x13be5`: `workloadsInstalled`
- `0x13bf9`: `install-product`
- `0x13c0d`: `elevated-install-product`
- `0x13c35`: `deletepackagesfromcache`
- `0x13c49`: `successdeletedcount`
- `0x13c5d`: `faileddeletedcount`
- `0x13c71`: `delete-installershortcut-error`
- `0x13c85`: `create-installershortcut-error`
- `0x13c99`: `write-userdata-error`
- `0x13d39`: `latest-installer-feed-download-error`
- `0x13d4d`: `test-msi-error`
- `0x13d75`: `export-installationconfiguration`
- `0x13d89`: `componentsCount`
- `0x13d9d`: `extensionsCount`
- `0x13dc5`: `failedExtensionsCount`
- `0x13e65`: `persistedCommandsExist`
- `0x13e79`: `commandsQueuedP1`
- `0x13e8d`: `commandsQueuedP2`
- `0x13ea1`: `commandsQueuedP3`
- `0x13eb5`: `totalCommandsInState`

## pseudocode

```c

```

## disassembly

```asm
0x12880  ldstr    aVsSetupengine_0// "vs/setupengine/"
0x12885  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::EVENTPREFIX
0x1288a  ldstr    aVsSetupengine_1// "VS.SetupEngine."
0x1288f  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12894  ldstr    aVsWillow// "vs/willow/"
0x12899  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::WILLOWEVENTPREFIX
0x1289e  ldstr    aVsWillow_0// "vs.willow."
0x128a3  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::WILLOWPROPERTYPREFIX
0x128a8  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x128ad  ldstr    aWarning// "Warning"
0x128b2  call     string [mscorlib]System.String::Concat(string, string)
0x128b7  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::WARNINGPROPERTY
0x128bc  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x128c1  ldstr    aFaultlocation// "FaultLocation"
0x128c6  call     string [mscorlib]System.String::Concat(string, string)
0x128cb  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x128d0  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x128d5  ldstr    aFaulttype// "FaultType"
0x128da  call     string [mscorlib]System.String::Concat(string, string)
0x128df  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x128e4  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x128e9  ldstr    aFaultdescripti// "FaultDescription"
0x128ee  call     string [mscorlib]System.String::Concat(string, string)
0x128f3  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTDESCRIPTIONPROPERTY
0x128f8  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x128fd  ldstr    aPerformance// "performance"
0x12902  call     string [mscorlib]System.String::Concat(string, string)
0x12907  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PERFORMANCEPROPERTY
0x1290c  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12911  ldstr    aUpdatedownload// "updateDownloadComplete"
0x12916  call     string [mscorlib]System.String::Concat(string, string)
0x1291b  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SESSIONUPDATEDOWNLOADCOMPLETEPROPERTY
0x12920  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12925  ldstr    aUpdatedownload_0// "updateDownloadTotalSize"
0x1292a  call     string [mscorlib]System.String::Concat(string, string)
0x1292f  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SESSIONUPDATEDOWNLOADTOTALSIZEPROPERTY
0x12934  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12939  ldstr    aUpdatedownload_1// "updateDownloadedSize"
0x1293e  call     string [mscorlib]System.String::Concat(string, string)
0x12943  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SESSIONUPDATEDOWNLOADSIZEPROPERTY
0x12948  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x1294d  ldstr    aUpdatedownload_2// "updateDownloadVersion"
0x12952  call     string [mscorlib]System.String::Concat(string, string)
0x12957  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SESSIONUPDATEDOWNLOADVERSIONPROPERTY
0x1295c  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12961  ldstr    aDownloadfailed// "DownloadFailedPackageCount"
0x12966  call     string [mscorlib]System.String::Concat(string, string)
0x1296b  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SESSIONDOWNLOADFAILPROPERTY
0x12970  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12975  ldstr    aInstallfailedp// "InstallFailedPackageCount"
0x1297a  call     string [mscorlib]System.String::Concat(string, string)
0x1297f  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SESSIONINSTALLFAILPROPERTY
0x12984  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12989  ldstr    aUninstallfaile// "UninstallFailedPackageCount"
0x1298e  call     string [mscorlib]System.String::Concat(string, string)
0x12993  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SESSIONUNINSTALLFAILPROPERTY
0x12998  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x1299d  ldstr    aSkippedpackage// "SkippedPackageCount"
0x129a2  call     string [mscorlib]System.String::Concat(string, string)
0x129a7  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SESSIONSKIPPEDFAILPROPERTY
0x129ac  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x129b1  ldstr    aFailedworkload// "FailedWorkloads"
0x129b6  call     string [mscorlib]System.String::Concat(string, string)
0x129bb  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SESSIONFAILEDWORKLOADSPROPERTY
0x129c0  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x129c5  ldstr    aAlphapackscoun// "AlphaPacksCount"
0x129ca  call     string [mscorlib]System.String::Concat(string, string)
0x129cf  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SESSIONALPHAPACKSCOUNT
0x129d4  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x129d9  ldstr    aIncontainer// "InContainer"
0x129de  call     string [mscorlib]System.String::Concat(string, string)
0x129e3  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SESSIONINCONTAINER
0x129e8  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x129ed  ldstr    aInstallpathcha// "InstallPathChanged"
0x129f2  call     string [mscorlib]System.String::Concat(string, string)
0x129f7  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::INSTALLATIONPATHCHANGED
0x129fc  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12a01  ldstr    aConnectioncost// "ConnectionCost"
0x12a06  call     string [mscorlib]System.String::Concat(string, string)
0x12a0b  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::CONNECTIONCOST
0x12a10  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12a15  ldstr    aOperationmode// "OperationMode"
0x12a1a  call     string [mscorlib]System.String::Concat(string, string)
0x12a1f  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SESSIONOPERATIONMODE
0x12a24  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12a29  ldstr    aConcurrentdown// "ConcurrentDownloads"
0x12a2e  call     string [mscorlib]System.String::Concat(string, string)
0x12a33  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SESSIONCONCURRENTDOWNLOADS
0x12a38  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12a3d  ldstr    aAggregatedownl// "AggregateDownloadWaitTime"
0x12a42  call     string [mscorlib]System.String::Concat(string, string)
0x12a47  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SESSIONAGGREGATEDOWNLOADWAITTIME
0x12a4c  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12a51  ldstr    aId// "Id"
0x12a56  call     string [mscorlib]System.String::Concat(string, string)
0x12a5b  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDID
0x12a60  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12a65  ldstr    aBranch_1// "Branch"
0x12a6a  call     string [mscorlib]System.String::Concat(string, string)
0x12a6f  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDBRANCH
0x12a74  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12a79  ldstr    aEngineversion// "EngineVersion"
0x12a7e  call     string [mscorlib]System.String::Concat(string, string)
0x12a83  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDENGINEVERSION
0x12a88  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12a8d  ldstr    aEngineassembly// "EngineAssemblyName"
0x12a92  call     string [mscorlib]System.String::Concat(string, string)
0x12a97  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDENGINEASSEMBLY
0x12a9c  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12aa1  ldstr    aBuildnumber// "BuildNumber"
0x12aa6  call     string [mscorlib]System.String::Concat(string, string)
0x12aab  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDBUILDNUMBER
0x12ab0  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12ab5  ldstr    aProductversion// "ProductVersion"
0x12aba  call     string [mscorlib]System.String::Concat(string, string)
0x12abf  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDPRODUCTVERSION
0x12ac4  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12ac9  ldstr    aWorkloads// "Workloads"
0x12ace  call     string [mscorlib]System.String::Concat(string, string)
0x12ad3  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDWORKLOADS
0x12ad8  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12add  ldstr    aChannelspath// "ChannelsPath"
0x12ae2  call     string [mscorlib]System.String::Concat(string, string)
0x12ae7  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDCHANNELSPATH
0x12aec  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12af1  ldstr    aChannelsid// "ChannelsId"
0x12af6  call     string [mscorlib]System.String::Concat(string, string)
0x12afb  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDCHANNELSID
0x12b00  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12b05  ldstr    aChannelsuri// "ChannelsUri"
0x12b0a  call     string [mscorlib]System.String::Concat(string, string)
0x12b0f  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDCHANNELSURI
0x12b14  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12b19  ldstr    aComponentid// "ComponentId"
0x12b1e  call     string [mscorlib]System.String::Concat(string, string)
0x12b23  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDCOMPONENTID
0x12b28  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12b2d  ldstr    aProductuniquei// "ProductUniqueId"
0x12b32  call     string [mscorlib]System.String::Concat(string, string)
0x12b37  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDPRODUCTID
0x12b3c  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12b41  ldstr    aInstanceid// "InstanceId"
0x12b46  call     string [mscorlib]System.String::Concat(string, string)
0x12b4b  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDINSTALLID
0x12b50  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12b55  ldstr    aCurrentoperati// "CurrentOperation"
0x12b5a  call     string [mscorlib]System.String::Concat(string, string)
0x12b5f  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDOPERATION
0x12b64  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12b69  ldstr    aPackageparents// "PackageParents"
0x12b6e  call     string [mscorlib]System.String::Concat(string, string)
0x12b73  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PARENTSPROPERTY
0x12b78  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12b7d  ldstr    aAncestorworklo// "AncestorWorkloads"
0x12b82  call     string [mscorlib]System.String::Concat(string, string)
0x12b87  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ANCESTORWORKLOADSPROPERTY
0x12b8c  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12b91  ldstr    aReboottype// "RebootType"
0x12b96  call     string [mscorlib]System.String::Concat(string, string)
0x12b9b  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::REBOOTREQUESTED
0x12ba0  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12ba5  ldstr    aNoweb// "NoWeb"
0x12baa  call     string [mscorlib]System.String::Concat(string, string)
0x12baf  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::NOWEB
0x12bb4  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12bb9  ldstr    aForce// "Force"
0x12bbe  call     string [mscorlib]System.String::Concat(string, string)
0x12bc3  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FORCE
0x12bc8  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12bcd  ldstr    aUpdatefromvs// "UpdateFromVS"
0x12bd2  call     string [mscorlib]System.String::Concat(string, string)
0x12bd7  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::UPDATEFROMVS
0x12bdc  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12be1  ldstr    aKeepdownloaded// "KeepDownloadedPayloads"
0x12be6  call     string [mscorlib]System.String::Concat(string, string)
0x12beb  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::KEEPDOWNLOADEDPAYLOADS
0x12bf0  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12bf5  ldstr    aUserrequestedo// "UserRequestedOperation"
0x12bfa  call     string [mscorlib]System.String::Concat(string, string)
0x12bff  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::USERREQUESTEDOPERATION
0x12c04  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12c09  ldstr    aSharedwillowin// "SharedWillowInstallSessionId"
0x12c0e  call     string [mscorlib]System.String::Concat(string, string)
0x12c13  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDWILLOWINSTALLSESSIONID
0x12c18  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::EVENTPREFIX
0x12c1d  ldstr    aOperation// "operation"
0x12c22  call     string [mscorlib]System.String::Concat(string, string)
0x12c27  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::INSTANCEOPERATIONEVENT
0x12c2c  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::EVENTPREFIX
0x12c31  ldstr    aChannelOperati// "channel-operation"
0x12c36  call     string [mscorlib]System.String::Concat(string, string)
0x12c3b  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::CHANNELOPERATIONEVENT
0x12c40  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::EVENTPREFIX
0x12c45  ldstr    aPackageOperati// "package-operation"
0x12c4a  call     string [mscorlib]System.String::Concat(string, string)
0x12c4f  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEOPERATIONEVENT
0x12c54  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::EVENTPREFIX
0x12c59  ldstr    aAuthenticateUs// "authenticate-user"
0x12c5e  call     string [mscorlib]System.String::Concat(string, string)
0x12c63  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::AUTHENTICATIONOPERATIONEVENT
0x12c68  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::EVENTPREFIX
0x12c6d  ldstr    aRecordAuthenti// "record-authentication-state"
0x12c72  call     string [mscorlib]System.String::Concat(string, string)
0x12c77  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::RECORDAUTHENTICATIONSTATEEVENT
0x12c7c  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::EVENTPREFIX
0x12c81  ldstr    aCreatePublicCl// "create-public-client-app-builder"
0x12c86  call     string [mscorlib]System.String::Concat(string, string)
0x12c8b  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::CREATEPUBLICCLIENTAPPBUILDER
0x12c90  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::EVENTPREFIX
0x12c95  ldstr    aBuildDependenc// "build-dependency-graph"
0x12c9a  call     string [mscorlib]System.String::Concat(string, string)
0x12c9f  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BUILDDEPENDENCYGRAPHEVENT
0x12ca4  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::EVENTPREFIX
0x12ca9  ldstr    aLoad// "load"
0x12cae  call     string [mscorlib]System.String::Concat(string, string)
0x12cb3  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::LOADCATALOGEVENT
0x12cb8  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::EVENTPREFIX
0x12cbd  ldstr    aDetectVsinstan// "detect-vsinstance"
0x12cc2  call     string [mscorlib]System.String::Concat(string, string)
0x12cc7  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::VSCURRENTINSTANCERUNNINGEVENT
0x12ccc  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::EVENTPREFIX
0x12cd1  ldstr    aVsrelatedproce// "vsrelatedprocessrunning"
0x12cd6  call     string [mscorlib]System.String::Concat(string, string)
0x12cdb  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::VSRELATEDPROCESSRUNNINGEVENT
0x12ce0  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::EVENTPREFIX
0x12ce5  ldstr    aVsrebootrequir// "vsrebootrequired"
0x12cea  call     string [mscorlib]System.String::Concat(string, string)
0x12cef  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::REBOOTREQUIREDEVENT
0x12cf4  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::EVENTPREFIX
0x12cf9  ldstr    aRunNgenactivit// "run-ngenactivities"
0x12cfe  call     string [mscorlib]System.String::Concat(string, string)
0x12d03  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::NGENACTIVITIESRUNNINGEVENT
0x12d08  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::EVENTPREFIX
0x12d0d  ldstr    aAddRemotechann// "add-remotechannel"
0x12d12  call     string [mscorlib]System.String::Concat(string, string)
0x12d17  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ADDREMOTECHANNELOPERATIONEVENT
0x12d1c  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::EVENTPREFIX
0x12d21  ldstr    aReportWidowsup// "report-widowsupdateprogress"
0x12d26  call     string [mscorlib]System.String::Concat(string, string)
0x12d2b  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::REPORTWINDOWSUPDATEPROGRESSEVENT
0x12d30  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::EVENTPREFIX
0x12d35  ldstr    aBackgrounddown_0// "backgrounddownload"
0x12d3a  call     string [mscorlib]System.String::Concat(string, string)
0x12d3f  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADEVENT
0x12d44  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::EVENTPREFIX
0x12d49  ldstr    aBackgrounddown_1// "backgrounddownload-perinstance"
0x12d4e  call     string [mscorlib]System.String::Concat(string, string)
0x12d53  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADPERINSTANCEEVENT
0x12d58  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADEVENT
0x12d5d  ldstr    aUnhandledexcep// "/UnhandledExceptionThrown"
0x12d62  call     string [mscorlib]System.String::Concat(string, string)
0x12d67  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADUNHANDLEDEXCEPTIONTHROWNEVENT
0x12d6c  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12d71  ldstr    aHasupdate// "HasUpdate"
0x12d76  call     string [mscorlib]System.String::Concat(string, string)
0x12d7b  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADHASUPDATE
0x12d80  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12d85  ldstr    aActivityid// "ActivityId"
0x12d8a  call     string [mscorlib]System.String::Concat(string, string)
0x12d8f  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADACTIVITYID
0x12d94  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12d99  ldstr    aIschildprocess// "IsChildProcess"
0x12d9e  call     string [mscorlib]System.String::Concat(string, string)
0x12da3  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADISCHILD
0x12da8  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12dad  ldstr    aIsnocancel// "IsNoCancel"
0x12db2  call     string [mscorlib]System.String::Concat(string, string)
0x12db7  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADNOCANCEL
0x12dbc  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12dc1  ldstr    aIsupdatechecko// "IsUpdateCheckOnly"
0x12dc6  call     string [mscorlib]System.String::Concat(string, string)
0x12dcb  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADISUPDATECHECKONLY
0x12dd0  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12dd5  ldstr    aExiterrorcode// "ExitErrorCode"
0x12dda  call     string [mscorlib]System.String::Concat(string, string)
0x12ddf  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADEXITERRORCODE
0x12de4  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12de9  ldstr    aInstanceid// "InstanceId"
0x12dee  call     string [mscorlib]System.String::Concat(string, string)
0x12df3  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADINSTANCEINSTANCEID
0x12df8  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12dfd  ldstr    aChannelid// "ChannelId"
0x12e02  call     string [mscorlib]System.String::Concat(string, string)
0x12e07  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADINSTANCECHANNELID
0x12e0c  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12e11  ldstr    aProductid// "ProductId"
0x12e16  call     string [mscorlib]System.String::Concat(string, string)
0x12e1b  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADINSTANCEPRODUCTID
0x12e20  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12e25  ldstr    aCurrentversion// "CurrentVersion"
0x12e2a  call     string [mscorlib]System.String::Concat(string, string)
0x12e2f  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADINSTANCECURRENTVERSION
0x12e34  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12e39  ldstr    aUpdateversion// "UpdateVersion"
0x12e3e  call     string [mscorlib]System.String::Concat(string, string)
0x12e43  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADINSTANCEUPDATEVERSION
0x12e48  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PROPERTYPREFIX
0x12e4d  ldstr    aPreviouslydown// "PreviouslyDownloadedSize"
0x12e52  call     string [mscorlib]System.String::Concat(string, string)
0x12e57  stsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADINSTANCEPREVIOUSDLSIZE
  ... truncated ...
```
