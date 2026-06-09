# System.Deployment.Application.ApplicationActivator::DownloadApplication

- ea: `0xba90`
- end: `0xbfd9`
- name: `System.Deployment.Application.ApplicationActivator::DownloadApplication`
- size: `1353`
- prototype: ``
- caller_count: `1`
- callee_count: `51`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0xb960`

## callees

- `0xba90`
- `0xc1b0`
- `0xc220`
- `0xc270`
- `0xc2a0`
- `0xd530`
- `0xd720`
- `0xd880`
- `0xd8a0`
- `0x13500`
- `0x13720`
- `0x146f0`
- `0x14700`
- `0x14b40`
- `0x14d60`
- `0x179b0`
- `0x17c60`
- `0x17cc0`
- `0x17cd0`
- `0x17d40`
- `0x1ba20`
- `0x1ed00`
- `0x1ed40`
- `0x1efe0`
- `0x1f800`
- `0x1faf0`
- `0x1fc90`
- `0x1fd20`
- `0x201e0`
- `0x20220`
- `0x20a60`
- `0x21bd0`
- `0x21da0`
- `0x21e00`
- `0x21ee0`
- `0x228d0`
- `0x23020`
- `0x23c30`
- `0x23c50`
- `0x23c80`
- `0x23dc0`
- `0x23dd0`
- `0x23de0`
- `0x23fe0`
- `0x24970`
- `0x249d0`
- `0x24b30`
- `0x24b90`
- `0x24d10`
- `0x24f90`

## string_xrefs

- `0xbaaa`: `Start processing application manifest.`
- `0xbb64`: `PhaseLog_ProcessingApplicationManifestComplete`
- `0xbb73`: `Processing of application manifest has successfully completed.`
- `0xbc44`: `EffectiveCertificatePublicKeyToken has changed between versions: subState.EffectiveCertificatePublicKeyToken=`
- `0xbc4f`: `,actDesc.EffectiveCertificatePublicKeyToken=`
- `0xbc64`: `Removing the cached trust decision for CurrentBind.`
- `0xbd65`: `Ex_FileExtensionNotSupported`
- `0xbd8e`: `PhaseLog_PlatformDetectAndTrustGrantComplete`
- `0xbd9d`: `Request of trust and detection of platform is complete.`
- `0xbdff`: `UI_ProgressTitleRequiredUpdate`
- `0xbe2f`: `UI_ProgressTitleUpdate`
- `0xbe9b`: `UI_ProgressTitleInstall`
- `0xbfac`: `PhaseLog_DownloadDependenciesComplete`

## pseudocode

```c

```

## disassembly

```asm
0xba90  ldc.i4.0
0xba91  stloc.0
0xba92  ldstr    aDownloadapplic// "DownloadApplication called."
0xba97  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0xba9c  ldarg.s  4
0xba9e  ldarg.0
0xba9f  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xbaa4  callvirt instance class System.Deployment.Application.TempDirectory System.Deployment.Application.SubscriptionStore::AcquireTempDirectory()
0xbaa9  stind.ref
0xbaaa  ldstr    aStartProcessin_1// "Start processing application manifest."
0xbaaf  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xbab4  ldarg.2
0xbab5  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xbaba  ldarg.s  4
0xbabc  ldind.ref
0xbabd  callvirt instance string System.Deployment.Application.TempDirectory::get_Path()
0xbac2  ldarg.2
0xbac3  ldfld    class [System]System.Uri System.Deployment.Application.CommitApplicationParams::DeploySourceUri
0xbac8  ldloca.s 1
0xbaca  ldloca.s 2
0xbacc  call     class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.DownloadManager::DownloadApplicationManifest(class System.Deployment.Application.Manifest.AssemblyManifest deploymentManifest, string targetDir, class [System]System.Uri deploymentUri, [out] class [System]System.Uri& appSourceUri, [out] string& appManifestPath)
0xbad1  stloc.3
0xbad2  ldarg.2
0xbad3  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xbad8  ldloc.3
0xbad9  call     void System.Deployment.Application.Manifest.AssemblyManifest::ReValidateManifestSignatures(class System.Deployment.Application.Manifest.AssemblyManifest depManifest, class System.Deployment.Application.Manifest.AssemblyManifest appManifest)
0xbade  ldloc.3
0xbadf  callvirt instance class System.Deployment.Application.Manifest.EntryPoint[] System.Deployment.Application.Manifest.AssemblyManifest::get_EntryPoints()
0xbae4  ldc.i4.0
0xbae5  ldelem.ref
0xbae6  callvirt instance bool System.Deployment.Application.Manifest.EntryPoint::get_HostInBrowser()
0xbaeb  brfalse.s loc_BAFF
0xbaed  ldc.i4.s 0x10
0xbaef  ldstr    aExHostinbrowse// "Ex_HostInBrowserAppNotSupported"
0xbaf4  call     string System.Deployment.Application.Resources::GetString(string s)
0xbaf9  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0xbafe  throw
0xbaff  ldloc.3
0xbb00  callvirt instance class System.Deployment.Application.Manifest.EntryPoint[] System.Deployment.Application.Manifest.AssemblyManifest::get_EntryPoints()
0xbb05  ldc.i4.0
0xbb06  ldelem.ref
0xbb07  callvirt instance bool System.Deployment.Application.Manifest.EntryPoint::get_CustomHostSpecified()
0xbb0c  brfalse.s loc_BB20
0xbb0e  ldc.i4.s 0x10
0xbb10  ldstr    aExCustomhostsp// "Ex_CustomHostSpecifiedAppNotSupported"
0xbb15  call     string System.Deployment.Application.Resources::GetString(string s)
0xbb1a  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0xbb1f  throw
0xbb20  ldloc.3
0xbb21  callvirt instance class System.Deployment.Application.Manifest.EntryPoint[] System.Deployment.Application.Manifest.AssemblyManifest::get_EntryPoints()
0xbb26  ldc.i4.0
0xbb27  ldelem.ref
0xbb28  callvirt instance bool System.Deployment.Application.Manifest.EntryPoint::get_CustomUX()
0xbb2d  brfalse.s loc_BB64
0xbb2f  ldarg.2
0xbb30  callvirt instance valuetype System.Deployment.Application.ActivationType System.Deployment.Application.ActivationDescription::get_ActType()
0xbb35  ldc.i4.1
0xbb36  beq.s    loc_BB52
0xbb38  ldarg.2
0xbb39  callvirt instance valuetype System.Deployment.Application.ActivationType System.Deployment.Application.ActivationDescription::get_ActType()
0xbb3e  ldc.i4.3
0xbb3f  beq.s    loc_BB52
0xbb41  ldarg.2
0xbb42  callvirt instance valuetype System.Deployment.Application.ActivationType System.Deployment.Application.ActivationDescription::get_ActType()
0xbb47  ldc.i4.2
0xbb48  beq.s    loc_BB52
0xbb4a  ldarg.2
0xbb4b  callvirt instance valuetype System.Deployment.Application.ActivationType System.Deployment.Application.ActivationDescription::get_ActType()
0xbb50  brtrue.s loc_BB64
0xbb52  ldc.i4.s 0x10
0xbb54  ldstr    aExCustomuxappn// "Ex_CustomUXAppNotSupported"
0xbb59  call     string System.Deployment.Application.Resources::GetString(string s)
0xbb5e  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0xbb63  throw
0xbb64  ldstr    aPhaselogProces_0// "PhaseLog_ProcessingApplicationManifestC"...
0xbb69  call     string System.Deployment.Application.Resources::GetString(string s)
0xbb6e  call     void System.Deployment.Application.Logger::AddPhaseInformation(string message)
0xbb73  ldstr    aProcessingOfAp// "Processing of application manifest has "...
0xbb78  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xbb7d  ldarg.2
0xbb7e  ldloc.3
0xbb7f  ldloc.1
0xbb80  ldloc.2
0xbb81  callvirt instance void System.Deployment.Application.ActivationDescription::SetApplicationManifest(class System.Deployment.Application.Manifest.AssemblyManifest manifest, class [System]System.Uri manifestUri, string manifestPath)
0xbb86  ldloc.3
0xbb87  call     void System.Deployment.Application.Logger::SetApplicationManifest(class System.Deployment.Application.Manifest.AssemblyManifest applicationManifest)
0xbb8c  ldarg.0
0xbb8d  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xbb92  ldarg.1
0xbb93  ldarg.2
0xbb94  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0xbb99  callvirt instance void System.Deployment.Application.SubscriptionStore::CheckCustomUXFlag(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.Manifest.AssemblyManifest application)
0xbb9e  ldarg.2
0xbb9f  ldarg.2
0xbba0  callvirt instance string System.Deployment.Application.ActivationDescription::ToAppCodebase()
0xbba5  ldc.i4.2
0xbba6  newarr   System.Deployment.Application.DefinitionIdentity
0xbbab  dup
0xbbac  ldc.i4.0
0xbbad  ldarg.2
0xbbae  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xbbb3  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0xbbb8  stelem.ref
0xbbb9  dup
0xbbba  ldc.i4.1
0xbbbb  ldarg.2
0xbbbc  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0xbbc1  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0xbbc6  stelem.ref
0xbbc7  newobj   instance void System.Deployment.Application.DefinitionAppId::.ctor(string codebase, class System.Deployment.Application.DefinitionIdentity[] idPath)
0xbbcc  stfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.CommitApplicationParams::AppId
0xbbd1  ldstr    aStartRequestOf// "Start request of trust and detection of"...
0xbbd6  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xbbdb  ldloc.3
0xbbdc  callvirt instance class System.Deployment.Application.Manifest.EntryPoint[] System.Deployment.Application.Manifest.AssemblyManifest::get_EntryPoints()
0xbbe1  ldc.i4.0
0xbbe2  ldelem.ref
0xbbe3  callvirt instance bool System.Deployment.Application.Manifest.EntryPoint::get_CustomUX()
0xbbe8  brfalse.s loc_BC0A
0xbbea  ldstr    aThisIsACustomu// "This is a CustomUX application. Calling"...
0xbbef  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xbbf4  ldarg.2
0xbbf5  ldarg.2
0xbbf6  callvirt instance class [mscorlib]System.ActivationContext System.Deployment.Application.ActivationDescription::ToActivationContext()
0xbbfb  call     class [mscorlib]System.Security.Policy.ApplicationTrust System.Deployment.Application.ApplicationTrust::PersistTrustWithoutEvaluation(class [mscorlib]System.ActivationContext actCtx)
0xbc00  stfld    class [mscorlib]System.Security.Policy.ApplicationTrust System.Deployment.Application.CommitApplicationParams::Trust
0xbc05  br       loc_BD18
0xbc0a  ldarg.0
0xbc0b  ldfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xbc10  callvirt instance void System.Deployment.Application.UserInterface::Hide()
0xbc15  ldarg.0
0xbc16  ldfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xbc1b  callvirt instance bool System.Deployment.Application.UserInterface::SplashCancelled()
0xbc20  brfalse.s loc_BC28
0xbc22  newobj   instance void System.Deployment.Application.DownloadCancelledException::.ctor()
0xbc27  throw
0xbc28  ldarg.1
0xbc29  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsInstalled()
0xbc2e  brfalse.s loc_BC79
0xbc30  ldarg.1
0xbc31  callvirt instance string System.Deployment.Application.SubscriptionState::get_EffectiveCertificatePublicKeyToken()
0xbc36  ldarg.2
0xbc37  callvirt instance string System.Deployment.Application.CommitApplicationParams::get_EffectiveCertificatePublicKeyToken()
0xbc3c  ldc.i4.4
0xbc3d  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xbc42  brtrue.s loc_BC79
0xbc44  ldstr    aEffectivecerti// "EffectiveCertificatePublicKeyToken has "...
0xbc49  ldarg.1
0xbc4a  callvirt instance string System.Deployment.Application.SubscriptionState::get_EffectiveCertificatePublicKeyToken()
0xbc4f  ldstr    aActdescEffecti// ",actDesc.EffectiveCertificatePublicKeyT"...
0xbc54  ldarg.2
0xbc55  callvirt instance string System.Deployment.Application.CommitApplicationParams::get_EffectiveCertificatePublicKeyToken()
0xbc5a  call     string [mscorlib]System.String::Concat(string, string, string, string)
0xbc5f  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xbc64  ldstr    aRemovingTheCac// "Removing the cached trust decision for "...
0xbc69  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xbc6e  ldarg.1
0xbc6f  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0xbc74  call     void System.Deployment.Application.ApplicationTrust::RemoveCachedTrust(class System.Deployment.Application.DefinitionAppId appId)
0xbc79  nop
0xbc7a  ldarg.2
0xbc7b  ldarg.1
0xbc7c  ldarg.2
0xbc7d  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xbc82  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xbc87  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_Install()
0xbc8c  ldarg.2
0xbc8d  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdate
0xbc92  ldarg.2
0xbc93  callvirt instance class [mscorlib]System.ActivationContext System.Deployment.Application.ActivationDescription::ToActivationContext()
0xbc98  call     class [mscorlib]System.Security.Policy.ApplicationTrust System.Deployment.Application.ApplicationTrust::RequestTrust(class System.Deployment.Application.SubscriptionState subState, bool isShellVisible, bool isUpdate, class [mscorlib]System.ActivationContext actCtx)
0xbc9d  stfld    class [mscorlib]System.Security.Policy.ApplicationTrust System.Deployment.Application.CommitApplicationParams::Trust
0xbca2  leave.s  loc_BD18
0xbca4  stloc.s  4
0xbca6  ldstr    aExDeterminetru// "Ex_DetermineTrustFailed"
0xbcab  call     string System.Deployment.Application.Resources::GetString(string s)
0xbcb0  ldloc.s  4
0xbcb2  call     void System.Deployment.Application.Logger::AddErrorInformation(string message, class [mscorlib]System.Exception exception)
0xbcb7  ldloc.s  4
0xbcb9  isinst   System.Deployment.Application.TrustNotGrantedException
0xbcbe  brtrue.s loc_BD16
0xbcc0  ldarg.2
0xbcc1  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0xbcc6  ldarg.2
0xbcc7  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xbccc  ldarg.s  4
0xbcce  ldind.ref
0xbccf  callvirt instance string System.Deployment.Application.TempDirectory::get_Path()
0xbcd4  call     void System.Deployment.Application.PlatformDetector::VerifyPlatformDependencies(class System.Deployment.Application.Manifest.AssemblyManifest appManifest, class System.Deployment.Application.Manifest.AssemblyManifest deployManifest, string tempDir)
0xbcd9  leave.s  loc_BD16
0xbcdb  stloc.s  5
0xbcdd  ldloc.s  5
0xbcdf  isinst   System.Deployment.Application.DependentPlatformMissingException
0xbce4  brfalse.s loc_BD14
0xbce6  ldc.i4.s 0x21
0xbce8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xbced  ldstr    aErrormessageTr// "ErrorMessage_TrustFailDependentPlatform"...
0xbcf2  call     string System.Deployment.Application.Resources::GetString(string s)
0xbcf7  ldc.i4.1
0xbcf8  newarr   [mscorlib]System.Object
0xbcfd  dup
0xbcfe  ldc.i4.0
0xbcff  ldloc.s  5
0xbd01  callvirt instance string [mscorlib]System.Exception::get_Message()
0xbd06  stelem.ref
0xbd07  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbd0c  ldloc.s  4
0xbd0e  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0xbd13  throw
0xbd14  leave.s  loc_BD16
0xbd16  rethrow
0xbd18  ldarg.0
0xbd19  ldarg.2
0xbd1a  ldfld    class [mscorlib]System.Security.Policy.ApplicationTrust System.Deployment.Application.CommitApplicationParams::Trust
0xbd1f  callvirt instance class [mscorlib]System.Security.Policy.PolicyStatement [mscorlib]System.Security.Policy.ApplicationTrust::get_DefaultGrantSet()
0xbd24  callvirt instance class [mscorlib]System.Security.PermissionSet [mscorlib]System.Security.Policy.PolicyStatement::get_PermissionSet()
0xbd29  callvirt instance bool [mscorlib]System.Security.PermissionSet::IsUnrestricted()
0xbd2e  stfld    bool System.Deployment.Application.ApplicationActivator::_fullTrust
0xbd33  ldstr    aFulltrust// "_fullTrust = "
0xbd38  ldarg.0
0xbd39  ldflda   bool System.Deployment.Application.ApplicationActivator::_fullTrust
0xbd3e  call     instance string [mscorlib]System.Boolean::ToString()
0xbd43  call     string [mscorlib]System.String::Concat(string, string)
0xbd48  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xbd4d  ldarg.0
0xbd4e  ldfld    bool System.Deployment.Application.ApplicationActivator::_fullTrust
0xbd53  brtrue.s loc_BD75
0xbd55  ldarg.2
0xbd56  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0xbd5b  callvirt instance class System.Deployment.Application.Manifest.FileAssociation[] System.Deployment.Application.Manifest.AssemblyManifest::get_FileAssociations()
0xbd60  ldlen
0xbd61  brfalse.s loc_BD75
0xbd63  ldc.i4.s 0x10
0xbd65  ldstr    aExFileextensio// "Ex_FileExtensionNotSupported"
0xbd6a  call     string System.Deployment.Application.Resources::GetString(string s)
0xbd6f  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0xbd74  throw
0xbd75  ldarg.2
0xbd76  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0xbd7b  ldarg.2
0xbd7c  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xbd81  ldarg.s  4
0xbd83  ldind.ref
0xbd84  callvirt instance string System.Deployment.Application.TempDirectory::get_Path()
0xbd89  call     void System.Deployment.Application.PlatformDetector::VerifyPlatformDependencies(class System.Deployment.Application.Manifest.AssemblyManifest appManifest, class System.Deployment.Application.Manifest.AssemblyManifest deployManifest, string tempDir)
0xbd8e  ldstr    aPhaselogPlatfo// "PhaseLog_PlatformDetectAndTrustGrantCom"...
0xbd93  call     string System.Deployment.Application.Resources::GetString(string s)
0xbd98  call     void System.Deployment.Application.Logger::AddPhaseInformation(string message)
0xbd9d  ldstr    aRequestOfTrust// "Request of trust and detection of platf"...
0xbda2  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xbda7  ldstr    aStartDownloadi// "Start downloading  and verifying depend"...
0xbdac  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xbdb1  ldarg.0
0xbdb2  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xbdb7  ldarg.1
0xbdb8  ldarg.2
0xbdb9  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.CommitApplicationParams::AppId
0xbdbe  ldarg.3
0xbdbf  callvirt instance bool System.Deployment.Application.SubscriptionStore::CheckAndReferenceApplication(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.DefinitionAppId appId, int64 transactionId)
0xbdc4  brtrue   loc_BFD7
0xbdc9  ldc.i4.1
0xbdca  stloc.0
0xbdcb  ldarg.2
0xbdcc  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.CommitApplicationParams::get_EffectiveDescription()
0xbdd1  stloc.s  6
0xbdd3  newobj   instance void System.Deployment.Application.UserInterfaceInfo::.ctor()
0xbdd8  stloc.s  7
0xbdda  ldloc.s  7
0xbddc  ldloc.s  6
0xbdde  callvirt instance string System.Deployment.Application.Manifest.Description::get_Product()
0xbde3  stfld    string System.Deployment.Application.UserInterfaceInfo::productName
0xbde8  ldarg.2
0xbde9  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdate
0xbdee  brfalse.s loc_BE55
0xbdf0  ldarg.2
0xbdf1  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsRequiredUpdate
0xbdf6  brfalse.s loc_BE28
0xbdf8  ldloc.s  7
0xbdfa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xbdff  ldstr    aUiProgresstitl// "UI_ProgressTitleRequiredUpdate"
0xbe04  call     string System.Deployment.Application.Resources::GetString(string s)
0xbe09  ldc.i4.1
0xbe0a  newarr   [mscorlib]System.Object
0xbe0f  dup
0xbe10  ldc.i4.0
0xbe11  ldloc.s  7
0xbe13  ldfld    string System.Deployment.Application.UserInterfaceInfo::productName
0xbe18  stelem.ref
0xbe19  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbe1e  stfld    string System.Deployment.Application.UserInterfaceInfo::formTitle
0xbe23  br       loc_BEBF
0xbe28  ldloc.s  7
0xbe2a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xbe2f  ldstr    aUiProgresstitl_0// "UI_ProgressTitleUpdate"
0xbe34  call     string System.Deployment.Application.Resources::GetString(string s)
0xbe39  ldc.i4.1
0xbe3a  newarr   [mscorlib]System.Object
0xbe3f  dup
0xbe40  ldc.i4.0
0xbe41  ldloc.s  7
  ... truncated ...
```
