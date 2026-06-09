# System.Deployment.Application.ApplicationActivator::PerformDeploymentActivation

- ea: `0xae50`
- end: `0xb16f`
- name: `System.Deployment.Application.ApplicationActivator::PerformDeploymentActivation`
- size: `799`
- prototype: ``
- caller_count: `2`
- callee_count: `33`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xaca0`
- `0xad70`

## callees

- `0xae50`
- `0xb170`
- `0xb2f0`
- `0xb490`
- `0xb6d0`
- `0xb960`
- `0xc1b0`
- `0xc200`
- `0xc2b0`
- `0xc2c0`
- `0x13110`
- `0x13480`
- `0x146f0`
- `0x14b40`
- `0x17910`
- `0x17cc0`
- `0x17cd0`
- `0x17d40`
- `0x1ed40`
- `0x1ef20`
- `0x1f0b0`
- `0x1f170`
- `0x1f7a0`
- `0x1f8b0`
- `0x20b30`
- `0x21cb0`
- `0x21e00`
- `0x23020`
- `0x23ca0`
- `0x23fd0`
- `0x24b30`
- `0x24b90`
- `0x28360`

## string_xrefs

- `0xaee3`: `Activating through deployment manifest.`
- `0xaeed`: `Start processing deployment manifest.`
- `0xaf7f`: `PhaseLog_ProcessingDeploymentManifestComplete`
- `0xaf8e`: `Processing of deployment manifest has successfully completed.`
- `0xafff`: `Could not find application in store. Continue with downloading application manifest.`
- `0xb015`: `PhaseLog_InstallationComplete`
- `0xb024`: `Installation of application has successfully completed.`
- `0xb06d`: `Activation_DisallowUrlActivationMessageAfterInstall`
- `0xb077`: `Activation_DisallowUrlActivationCaptionAfterInstall`

## pseudocode

```c

```

## disassembly

```asm
0xae50  ldnull
0xae51  stloc.0
0xae52  ldstr    aPerformdeploym// "PerformDeploymentActivation called."
0xae57  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0xae5c  ldnull
0xae5d  stloc.1
0xae5e  ldnull
0xae5f  stloc.2
0xae60  ldc.i4.0
0xae61  stloc.3
0xae62  ldarg.0
0xae63  call     class System.Deployment.Application.SubscriptionStore System.Deployment.Application.SubscriptionStore::get_CurrentUser()
0xae68  stfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xae6d  ldarg.0
0xae6e  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xae73  callvirt instance void System.Deployment.Application.SubscriptionStore::RefreshStorePointer()
0xae78  ldnull
0xae79  ldarg.s  7
0xae7b  ldind.ref
0xae7c  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0xae81  brfalse.s loc_AE87
0xae83  ldarg.s  7
0xae85  ldarg.1
0xae86  stind.ref
0xae87  ldc.i4.0
0xae88  stloc.s  5
0xae8a  ldarg.3
0xae8b  brfalse.s loc_AEB6
0xae8d  ldstr    aActivatingThro// "Activating through file association."
0xae92  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xae97  ldc.i4.1
0xae98  stloc.s  5
0xae9a  ldarg.0
0xae9b  ldarg.1
0xae9c  ldarg.3
0xae9d  ldarg.s  4
0xae9f  ldarg.s  6
0xaea1  ldloca.s 0
0xaea3  call     instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.ApplicationActivator::ProcessOrFollowExtension(class [System]System.Uri associatedFile, string textualSubId, string deploymentProviderUrlFromExtension, string& errorPageUrl, [out] class System.Deployment.Application.TempFile& deployFile)
0xaea8  stloc.s  4
0xaeaa  ldloc.s  4
0xaeac  brtrue   loc_AFB7
0xaeb1  leave    loc_B16E
0xaeb6  ldarg.2
0xaeb7  brfalse.s loc_AEE3
0xaeb9  ldstr    aActivatingThro_0// "Activating through shortcut."
0xaebe  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xaec3  ldarg.1
0xaec4  callvirt instance string [System]System.Uri::get_LocalPath()
0xaec9  stloc.1
0xaeca  ldarg.0
0xaecb  ldloc.1
0xaecc  ldarg.s  6
0xaece  ldloca.s 0
0xaed0  call     instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.ApplicationActivator::ProcessOrFollowShortcut(string shortcutFile, string& errorPageUrl, [out] class System.Deployment.Application.TempFile& deployFile)
0xaed5  stloc.s  4
0xaed7  ldloc.s  4
0xaed9  brtrue   loc_AFB7
0xaede  leave    loc_B16E
0xaee3  ldstr    aActivatingThro_1// "Activating through deployment manifest."
0xaee8  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xaeed  ldstr    aStartProcessin// "Start processing deployment manifest."
0xaef2  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xaef7  ldarg.0
0xaef8  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xaefd  ldarg.s  7
0xaeff  ldloca.s 0
0xaf01  ldloca.s 6
0xaf03  ldnull
0xaf04  ldnull
0xaf05  call     class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.DownloadManager::DownloadDeploymentManifestBypass(class System.Deployment.Application.SubscriptionStore subStore, class [System]System.Uri& sourceUri, [out] class System.Deployment.Application.TempFile& tempFile, [out] class System.Deployment.Application.SubscriptionState& subState, class System.Deployment.Application.IDownloadNotification notification, class System.Deployment.Application.DownloadOptions options)
0xaf0a  stloc.s  7
0xaf0c  ldarg.s  5
0xaf0e  brfalse.s loc_AF20
0xaf10  ldloc.0
0xaf11  brfalse.s loc_AF20
0xaf13  ldarg.s  5
0xaf15  ldloc.0
0xaf16  callvirt instance string System.Deployment.Application.TempFile::get_Path()
0xaf1b  callvirt instance void BrowserSettings::Validate(string manifestPath)
0xaf20  ldloc.s  7
0xaf22  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0xaf27  brfalse.s loc_AF38
0xaf29  ldarg.s  6
0xaf2b  ldloc.s  7
0xaf2d  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0xaf32  callvirt instance string System.Deployment.Application.Manifest.Description::get_ErrorReportUrl()
0xaf37  stind.ref
0xaf38  newobj   instance void System.Deployment.Application.ActivationDescription::.ctor()
0xaf3d  stloc.s  4
0xaf3f  ldloc.s  6
0xaf41  brfalse.s loc_AF71
0xaf43  ldnull
0xaf44  stloc.1
0xaf45  ldloc.s  4
0xaf47  ldloc.s  6
0xaf49  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentApplicationManifest()
0xaf4e  ldnull
0xaf4f  ldnull
0xaf50  callvirt instance void System.Deployment.Application.ActivationDescription::SetApplicationManifest(class System.Deployment.Application.Manifest.AssemblyManifest manifest, class [System]System.Uri manifestUri, string manifestPath)
0xaf55  ldloc.s  4
0xaf57  ldloc.s  6
0xaf59  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0xaf5e  stfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.CommitApplicationParams::AppId
0xaf63  ldstr    aRunningFromThe// "Running from the store. Bypass further "...
0xaf68  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xaf6d  ldc.i4.1
0xaf6e  stloc.3
0xaf6f  br.s     loc_AF78
0xaf71  ldloc.0
0xaf72  callvirt instance string System.Deployment.Application.TempFile::get_Path()
0xaf77  stloc.1
0xaf78  ldloc.s  7
0xaf7a  call     void System.Deployment.Application.Logger::SetDeploymentManifest(class System.Deployment.Application.Manifest.AssemblyManifest deploymentManifest)
0xaf7f  ldstr    aPhaselogProces// "PhaseLog_ProcessingDeploymentManifestCo"...
0xaf84  call     string System.Deployment.Application.Resources::GetString(string s)
0xaf89  call     void System.Deployment.Application.Logger::AddPhaseInformation(string message)
0xaf8e  ldstr    aProcessingOfDe// "Processing of deployment manifest has s"...
0xaf93  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xaf98  ldloc.s  4
0xaf9a  ldloc.s  7
0xaf9c  ldarg.s  7
0xaf9e  ldind.ref
0xaf9f  ldloc.1
0xafa0  callvirt instance void System.Deployment.Application.ActivationDescription::SetDeploymentManifest(class System.Deployment.Application.Manifest.AssemblyManifest manifest, class [System]System.Uri manifestUri, string manifestPath)
0xafa5  ldloc.s  4
0xafa7  ldc.i4.0
0xafa8  stfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdate
0xafad  ldloc.s  4
0xafaf  ldc.i4.1
0xafb0  callvirt instance void System.Deployment.Application.ActivationDescription::set_ActType(valuetype System.Deployment.Application.ActivationType value)
0xafb5  ldarg.1
0xafb6  stloc.2
0xafb7  ldarg.0
0xafb8  ldfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xafbd  callvirt instance bool System.Deployment.Application.UserInterface::SplashCancelled()
0xafc2  brfalse.s loc_AFCA
0xafc4  newobj   instance void System.Deployment.Application.DownloadCancelledException::.ctor()
0xafc9  throw
0xafca  ldloc.s  4
0xafcc  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xafd1  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xafd6  brfalse  loc_B153
0xafdb  ldc.i4.0
0xafdc  stloc.s  8
0xafde  ldarg.0
0xafdf  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xafe4  ldloc.s  4
0xafe6  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xafeb  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0xaff0  stloc.s  9
0xaff2  ldarg.0
0xaff3  ldloc.s  4
0xaff5  ldloc.s  9
0xaff7  call     instance void System.Deployment.Application.ApplicationActivator::CheckDeploymentProviderValidity(class System.Deployment.Application.ActivationDescription actDesc, class System.Deployment.Application.SubscriptionState subState)
0xaffc  ldloc.3
0xaffd  brtrue.s loc_B030
0xafff  ldstr    aCouldNotFindAp// "Could not find application in store. Co"...
0xb004  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb009  ldarg.0
0xb00a  ldloca.s 9
0xb00c  ldloc.s  4
0xb00e  call     instance bool System.Deployment.Application.ApplicationActivator::InstallApplication(class System.Deployment.Application.SubscriptionState& subState, class System.Deployment.Application.ActivationDescription actDesc)
0xb013  stloc.s  8
0xb015  ldstr    aPhaselogInstal// "PhaseLog_InstallationComplete"
0xb01a  call     string System.Deployment.Application.Resources::GetString(string s)
0xb01f  call     void System.Deployment.Application.Logger::AddPhaseInformation(string message)
0xb024  ldstr    aInstallationOf// "Installation of application has success"...
0xb029  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb02e  br.s     loc_B03D
0xb030  ldarg.0
0xb031  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xb036  ldloc.s  9
0xb038  callvirt instance void System.Deployment.Application.SubscriptionStore::SetLastCheckTimeToNow(class System.Deployment.Application.SubscriptionState subState)
0xb03d  ldloc.s  4
0xb03f  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xb044  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xb049  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_DisallowUrlActivation()
0xb04e  brfalse.s loc_B0AF
0xb050  ldarg.2
0xb051  brtrue.s loc_B0AF
0xb053  ldarg.1
0xb054  callvirt instance bool [System]System.Uri::get_IsFile()
0xb059  brfalse.s loc_B063
0xb05b  ldarg.1
0xb05c  callvirt instance bool [System]System.Uri::get_IsUnc()
0xb061  brfalse.s loc_B0AF
0xb063  ldloc.s  8
0xb065  brfalse.s loc_B08B
0xb067  ldarg.0
0xb068  ldfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xb06d  ldstr    aActivationDisa// "Activation_DisallowUrlActivationMessage"...
0xb072  call     string System.Deployment.Application.Resources::GetString(string s)
0xb077  ldstr    aActivationDisa_0// "Activation_DisallowUrlActivationCaption"...
0xb07c  call     string System.Deployment.Application.Resources::GetString(string s)
0xb081  callvirt instance void System.Deployment.Application.UserInterface::ShowMessage(string message, string caption)
0xb086  leave    loc_B16E
0xb08b  ldarg.0
0xb08c  ldfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xb091  ldstr    aActivationDisa_1// "Activation_DisallowUrlActivationMessage"
0xb096  call     string System.Deployment.Application.Resources::GetString(string s)
0xb09b  ldstr    aActivationDisa_2// "Activation_DisallowUrlActivationCaption"
0xb0a0  call     string System.Deployment.Application.Resources::GetString(string s)
0xb0a5  callvirt instance void System.Deployment.Application.UserInterface::ShowMessage(string message, string caption)
0xb0aa  leave    loc_B16E
0xb0af  ldloc.s  5
0xb0b1  brfalse.s loc_B0D3
0xb0b3  ldarg.0
0xb0b4  ldloc.s  4
0xb0b6  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.CommitApplicationParams::AppId
0xb0bb  ldloc.s  4
0xb0bd  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0xb0c2  ldarg.1
0xb0c3  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xb0c8  ldc.i4.1
0xb0c9  call     instance void System.Deployment.Application.ApplicationActivator::Activate(class System.Deployment.Application.DefinitionAppId appId, class System.Deployment.Application.Manifest.AssemblyManifest appManifest, string activationParameter, bool useActivationParameter)
0xb0ce  leave    loc_B16E
0xb0d3  ldarg.2
0xb0d4  brfalse.s loc_B136
0xb0d6  ldnull
0xb0d7  stloc.s  0xA
0xb0d9  ldloc.1
0xb0da  ldc.i4.s 0x7C
0xb0dc  ldc.i4.0
0xb0dd  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32)
0xb0e2  stloc.s  0xB
0xb0e4  ldloc.s  0xB
0xb0e6  ldc.i4.0
0xb0e7  ble.s    loc_B101
0xb0e9  ldloc.s  0xB
0xb0eb  ldc.i4.1
0xb0ec  add
0xb0ed  ldloc.1
0xb0ee  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb0f3  bge.s    loc_B101
0xb0f5  ldloc.1
0xb0f6  ldloc.s  0xB
0xb0f8  ldc.i4.1
0xb0f9  add
0xb0fa  callvirt instance string [mscorlib]System.String::Substring(int32)
0xb0ff  stloc.s  0xA
0xb101  ldloc.s  0xA
0xb103  brtrue.s loc_B11D
0xb105  ldarg.0
0xb106  ldloc.s  4
0xb108  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.CommitApplicationParams::AppId
0xb10d  ldloc.s  4
0xb10f  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0xb114  ldnull
0xb115  ldc.i4.0
0xb116  call     instance void System.Deployment.Application.ApplicationActivator::Activate(class System.Deployment.Application.DefinitionAppId appId, class System.Deployment.Application.Manifest.AssemblyManifest appManifest, string activationParameter, bool useActivationParameter)
0xb11b  leave.s  loc_B16E
0xb11d  ldarg.0
0xb11e  ldloc.s  4
0xb120  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.CommitApplicationParams::AppId
0xb125  ldloc.s  4
0xb127  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0xb12c  ldloc.s  0xA
0xb12e  ldc.i4.1
0xb12f  call     instance void System.Deployment.Application.ApplicationActivator::Activate(class System.Deployment.Application.DefinitionAppId appId, class System.Deployment.Application.Manifest.AssemblyManifest appManifest, string activationParameter, bool useActivationParameter)
0xb134  leave.s  loc_B16E
0xb136  ldarg.0
0xb137  ldloc.s  4
0xb139  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.CommitApplicationParams::AppId
0xb13e  ldloc.s  4
0xb140  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0xb145  ldloc.2
0xb146  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xb14b  ldc.i4.0
0xb14c  call     instance void System.Deployment.Application.ApplicationActivator::Activate(class System.Deployment.Application.DefinitionAppId appId, class System.Deployment.Application.Manifest.AssemblyManifest appManifest, string activationParameter, bool useActivationParameter)
0xb151  leave.s  loc_B16E
0xb153  ldc.i4.1
0xb154  ldstr    aExNotdeploymen// "Ex_NotDeploymentOrShortcut"
0xb159  call     string System.Deployment.Application.Resources::GetString(string s)
0xb15e  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0xb163  throw
0xb164  ldloc.0
0xb165  brfalse.s loc_B16D
0xb167  ldloc.0
0xb168  callvirt instance void System.Deployment.Application.DisposableBase::Dispose()
0xb16d  endfinally
0xb16e  ret
```
