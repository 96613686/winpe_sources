# System.Deployment.Application.DeploymentServiceCom::MaintainSubscriptionInternal

- ea: `0x12a70`
- end: `0x12e0c`
- name: `System.Deployment.Application.DeploymentServiceCom::MaintainSubscriptionInternal`
- size: `924`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x12a00`

## callees

- `0x12a70`
- `0x12ee0`
- `0x12f90`
- `0x17640`
- `0x17660`
- `0x178a0`
- `0x17c60`
- `0x17c80`
- `0x17cc0`
- `0x17d50`
- `0x17d90`
- `0x17e00`
- `0x18f20`
- `0x1d5f0`
- `0x1ecf0`
- `0x1eec0`
- `0x1eee0`
- `0x1efa0`
- `0x1f550`
- `0x1f5f0`
- `0x1fba0`
- `0x21bb0`
- `0x21c60`
- `0x21cb0`
- `0x21d40`
- `0x228d0`
- `0x23020`
- `0x23c30`
- `0x23c50`
- `0x23ca0`
- `0x24b30`

## string_xrefs

- `0x12aa3`: `ErrorMessage_GenericLinkUrlMessage`
- `0x12cb3`: `Uninstall_FailedMsg`
- `0x12a82`: `Maintain_Completed`
- `0x12c3c`: `Rollback_Exception`
- `0x12c44`: `Rollback_Completed`
- `0x12c4c`: `Rollback_Failed`
- `0x12c54`: `Rollback_FailedMsg`
- `0x12c6d`: `UI_RollbackCompletedMsg`
- `0x12c77`: `UI_RollbackCompletedTitle`
- `0x12c9b`: `Uninstall_Exception`
- `0x12ca3`: `Uninstall_Completed`
- `0x12cab`: `Uninstall_Failed`
- `0x12cce`: `MaintainLogMsg_UninstallFailed`

## pseudocode

```c

```

## disassembly

```asm
0x12a70  ldc.i4.0
0x12a71  stloc.0
0x12a72  ldc.i4.4
0x12a73  newarr   [mscorlib]System.String
0x12a78  dup
0x12a79  ldc.i4.0
0x12a7a  ldstr    aMaintainExcept// "Maintain_Exception"
0x12a7f  stelem.ref
0x12a80  dup
0x12a81  ldc.i4.1
0x12a82  ldstr    aMaintainComple// "Maintain_Completed"
0x12a87  stelem.ref
0x12a88  dup
0x12a89  ldc.i4.2
0x12a8a  ldstr    aMaintainFailed// "Maintain_Failed"
0x12a8f  stelem.ref
0x12a90  dup
0x12a91  ldc.i4.3
0x12a92  ldstr    aMaintainFailed_0// "Maintain_FailedMsg"
0x12a97  stelem.ref
0x12a98  stloc.1
0x12a99  ldc.i4.0
0x12a9a  stloc.2
0x12a9b  ldnull
0x12a9c  stloc.3
0x12a9d  ldc.i4.0
0x12a9e  stloc.s  4
0x12aa0  ldc.i4.0
0x12aa1  stloc.s  5
0x12aa3  ldstr    aErrormessageGe_0// "ErrorMessage_GenericLinkUrlMessage"
0x12aa8  call     string System.Deployment.Application.Resources::GetString(string s)
0x12aad  stloc.s  6
0x12aaf  ldnull
0x12ab0  stloc.s  7
0x12ab2  ldnull
0x12ab3  stloc.s  8
0x12ab5  call     class LogIdentity System.Deployment.Application.Logger::StartCurrentThreadLogging()
0x12aba  pop
0x12abb  ldarg.1
0x12abc  call     void System.Deployment.Application.Logger::SetTextualSubscriptionIdentity(string textualIdentity)
0x12ac1  newobj   instance void System.Deployment.Application.UserInterface::.ctor()
0x12ac6  stloc.s  9
0x12ac8  newobj   instance void System.Deployment.Application.MaintenanceInfo::.ctor()
0x12acd  stloc.s  0xA
0x12acf  newobj   instance void System.Deployment.Application.UserInterfaceInfo::.ctor()
0x12ad4  stloc.s  0xB
0x12ad6  ldstr    aPhaselogStoreq// "PhaseLog_StoreQueryForMaintenanceInfo"
0x12adb  call     string System.Deployment.Application.Resources::GetString(string s)
0x12ae0  call     void System.Deployment.Application.Logger::AddPhaseInformation(string message)
0x12ae5  ldarg.0
0x12ae6  ldarg.1
0x12ae7  call     instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.DeploymentServiceCom::GetSubscriptionState(string textualSubId)
0x12aec  stloc.s  0xC
0x12aee  ldloc.s  0xC
0x12af0  callvirt instance class System.Deployment.Application.SubscriptionStore System.Deployment.Application.SubscriptionState::get_SubscriptionStore()
0x12af5  ldloc.s  0xC
0x12af7  callvirt instance void System.Deployment.Application.SubscriptionStore::CheckInstalledAndShellVisible(class System.Deployment.Application.SubscriptionState subState)
0x12afc  ldloc.s  0xC
0x12afe  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_RollbackDeployment()
0x12b03  brtrue.s loc_12B16
0x12b05  ldloc.s  0xA
0x12b07  dup
0x12b08  ldfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x12b0d  ldc.i4.4
0x12b0e  or
0x12b0f  stfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x12b14  br.s     loc_12B34
0x12b16  ldloc.s  0xA
0x12b18  dup
0x12b19  ldfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x12b1e  ldc.i4.1
0x12b1f  or
0x12b20  stfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x12b25  ldloc.s  0xA
0x12b27  dup
0x12b28  ldfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x12b2d  ldc.i4.2
0x12b2e  or
0x12b2f  stfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x12b34  ldloc.s  0xC
0x12b36  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0x12b3b  stloc.s  0xE
0x12b3d  ldloc.s  0xE
0x12b3f  brfalse.s loc_12B58
0x12b41  ldloc.s  0xE
0x12b43  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x12b48  brfalse.s loc_12B58
0x12b4a  ldloc.s  0xE
0x12b4c  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x12b51  callvirt instance string System.Deployment.Application.Manifest.Description::get_ErrorReportUrl()
0x12b56  stloc.s  8
0x12b58  ldloc.s  0xC
0x12b5a  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.SubscriptionState::get_EffectiveDescription()
0x12b5f  stloc.s  0xF
0x12b61  ldloc.s  0xB
0x12b63  ldloc.s  0xF
0x12b65  callvirt instance string System.Deployment.Application.Manifest.Description::get_Product()
0x12b6a  stfld    string System.Deployment.Application.UserInterfaceInfo::productName
0x12b6f  ldloc.s  0xB
0x12b71  ldloc.s  0xF
0x12b73  callvirt instance string System.Deployment.Application.Manifest.Description::get_SupportUrl()
0x12b78  stfld    string System.Deployment.Application.UserInterfaceInfo::supportUrl
0x12b7d  ldloc.s  0xB
0x12b7f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x12b84  ldstr    aUiMaintenancet// "UI_MaintenanceTitle"
0x12b89  call     string System.Deployment.Application.Resources::GetString(string s)
0x12b8e  ldc.i4.1
0x12b8f  newarr   [mscorlib]System.Object
0x12b94  dup
0x12b95  ldc.i4.0
0x12b96  ldloc.s  0xB
0x12b98  ldfld    string System.Deployment.Application.UserInterfaceInfo::productName
0x12b9d  stelem.ref
0x12b9e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12ba3  stfld    string System.Deployment.Application.UserInterfaceInfo::formTitle
0x12ba8  ldc.i4.1
0x12ba9  stloc.s  4
0x12bab  leave.s  loc_12BFB
0x12bad  stloc.s  0x10
0x12baf  ldc.i4.0
0x12bb0  stloc.s  4
0x12bb2  ldstr    aMaintainlogmsg// "MaintainLogMsg_FailedStoreLookup"
0x12bb7  call     string System.Deployment.Application.Resources::GetString(string s)
0x12bbc  ldloc.s  0x10
0x12bbe  call     void System.Deployment.Application.Logger::AddErrorInformation(string message, class [mscorlib]System.Exception exception)
0x12bc3  ldloc.s  0xA
0x12bc5  dup
0x12bc6  ldfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x12bcb  ldc.i4.4
0x12bcc  or
0x12bcd  stfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x12bd2  leave.s  loc_12BFB
0x12bd4  stloc.s  0x11
0x12bd6  ldc.i4.0
0x12bd7  stloc.s  4
0x12bd9  ldstr    aMaintainlogmsg// "MaintainLogMsg_FailedStoreLookup"
0x12bde  call     string System.Deployment.Application.Resources::GetString(string s)
0x12be3  ldloc.s  0x11
0x12be5  call     void System.Deployment.Application.Logger::AddErrorInformation(string message, class [mscorlib]System.Exception exception)
0x12bea  ldloc.s  0xA
0x12bec  dup
0x12bed  ldfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x12bf2  ldc.i4.4
0x12bf3  or
0x12bf4  stfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x12bf9  leave.s  loc_12BFB
0x12bfb  ldc.i4.0
0x12bfc  stloc.s  0xD
0x12bfe  ldloc.s  4
0x12c00  brfalse.s loc_12C15
0x12c02  ldloc.s  9
0x12c04  ldloc.s  0xB
0x12c06  ldloc.s  0xA
0x12c08  callvirt instance valuetype System.Deployment.Application.UserInterfaceModalResult System.Deployment.Application.UserInterface::ShowMaintenance(class System.Deployment.Application.UserInterfaceInfo info, class System.Deployment.Application.MaintenanceInfo maintenanceInfo)
0x12c0d  ldc.i4.1
0x12c0e  bne.un.s loc_12C20
0x12c10  ldc.i4.1
0x12c11  stloc.s  0xD
0x12c13  br.s     loc_12C20
0x12c15  ldloc.s  0xA
0x12c17  ldc.i4.4
0x12c18  stfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x12c1d  ldc.i4.1
0x12c1e  stloc.s  0xD
0x12c20  ldloc.s  0xD
0x12c22  brfalse  loc_12CF0
0x12c27  ldc.i4.1
0x12c28  stloc.2
0x12c29  ldloc.s  0xA
0x12c2b  ldfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x12c30  ldc.i4.2
0x12c31  and
0x12c32  brfalse.s loc_12C88
0x12c34  ldc.i4.4
0x12c35  newarr   [mscorlib]System.String
0x12c3a  dup
0x12c3b  ldc.i4.0
0x12c3c  ldstr    aRollbackExcept// "Rollback_Exception"
0x12c41  stelem.ref
0x12c42  dup
0x12c43  ldc.i4.1
0x12c44  ldstr    aRollbackComple// "Rollback_Completed"
0x12c49  stelem.ref
0x12c4a  dup
0x12c4b  ldc.i4.2
0x12c4c  ldstr    aRollbackFailed// "Rollback_Failed"
0x12c51  stelem.ref
0x12c52  dup
0x12c53  ldc.i4.3
0x12c54  ldstr    aRollbackFailed_0// "Rollback_FailedMsg"
0x12c59  stelem.ref
0x12c5a  stloc.1
0x12c5b  ldloc.s  0xC
0x12c5d  callvirt instance class System.Deployment.Application.SubscriptionStore System.Deployment.Application.SubscriptionState::get_SubscriptionStore()
0x12c62  ldloc.s  0xC
0x12c64  callvirt instance void System.Deployment.Application.SubscriptionStore::RollbackSubscription(class System.Deployment.Application.SubscriptionState subState)
0x12c69  ldc.i4.0
0x12c6a  stloc.2
0x12c6b  ldloc.s  9
0x12c6d  ldstr    aUiRollbackcomp// "UI_RollbackCompletedMsg"
0x12c72  call     string System.Deployment.Application.Resources::GetString(string s)
0x12c77  ldstr    aUiRollbackcomp_0// "UI_RollbackCompletedTitle"
0x12c7c  call     string System.Deployment.Application.Resources::GetString(string s)
0x12c81  callvirt instance void System.Deployment.Application.UserInterface::ShowMessage(string message, string caption)
0x12c86  br.s     loc_12CEE
0x12c88  ldloc.s  0xA
0x12c8a  ldfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x12c8f  ldc.i4.4
0x12c90  and
0x12c91  brfalse.s loc_12CEE
0x12c93  ldc.i4.4
0x12c94  newarr   [mscorlib]System.String
0x12c99  dup
0x12c9a  ldc.i4.0
0x12c9b  ldstr    aUninstallExcep// "Uninstall_Exception"
0x12ca0  stelem.ref
0x12ca1  dup
0x12ca2  ldc.i4.1
0x12ca3  ldstr    aUninstallCompl// "Uninstall_Completed"
0x12ca8  stelem.ref
0x12ca9  dup
0x12caa  ldc.i4.2
0x12cab  ldstr    aUninstallFaile_0// "Uninstall_Failed"
0x12cb0  stelem.ref
0x12cb1  dup
0x12cb2  ldc.i4.3
0x12cb3  ldstr    aUninstallFaile// "Uninstall_FailedMsg"
0x12cb8  stelem.ref
0x12cb9  stloc.1
0x12cba  ldloc.s  0xC
0x12cbc  callvirt instance class System.Deployment.Application.SubscriptionStore System.Deployment.Application.SubscriptionState::get_SubscriptionStore()
0x12cc1  ldloc.s  0xC
0x12cc3  callvirt instance void System.Deployment.Application.SubscriptionStore::UninstallSubscription(class System.Deployment.Application.SubscriptionState subState)
0x12cc8  ldc.i4.0
0x12cc9  stloc.2
0x12cca  leave.s  loc_12CEE
0x12ccc  stloc.s  0x12
0x12cce  ldstr    aMaintainlogmsg_0// "MaintainLogMsg_UninstallFailed"
0x12cd3  call     string System.Deployment.Application.Resources::GetString(string s)
0x12cd8  ldloc.s  0x12
0x12cda  call     void System.Deployment.Application.Logger::AddErrorInformation(string message, class [mscorlib]System.Exception exception)
0x12cdf  ldc.i4.1
0x12ce0  stloc.s  5
0x12ce2  ldloc.s  0xC
0x12ce4  call     void System.Deployment.Application.ShellExposure::RemoveSubscriptionShellExposure(class System.Deployment.Application.SubscriptionState subState)
0x12ce9  ldc.i4.0
0x12cea  stloc.s  5
0x12cec  leave.s  loc_12CEE
0x12cee  ldc.i4.1
0x12cef  stloc.0
0x12cf0  leave    loc_12E0B
0x12cf5  stloc.s  0x13
0x12cf7  ldloc.s  0x13
0x12cf9  ldloc.1
0x12cfa  ldc.i4.0
0x12cfb  ldelem.ref
0x12cfc  call     string System.Deployment.Application.Resources::GetString(string s)
0x12d01  ldc.i4.1
0x12d02  newarr   [mscorlib]System.Object
0x12d07  dup
0x12d08  ldc.i4.0
0x12d09  ldarg.1
0x12d0a  stelem.ref
0x12d0b  call     void System.Deployment.Application.Logger::AddErrorInformation(class [mscorlib]System.Exception exception, string messageFormat, object[] args)
0x12d10  ldloc.s  0x13
0x12d12  stloc.3
0x12d13  leave    loc_12E0B
0x12d18  ldloc.0
0x12d19  brtrue.s loc_12D20
0x12d1b  ldloc.1
0x12d1c  ldc.i4.2
0x12d1d  ldelem.ref
0x12d1e  br.s     loc_12D23
0x12d20  ldloc.1
0x12d21  ldc.i4.1
0x12d22  ldelem.ref
0x12d23  call     string System.Deployment.Application.Resources::GetString(string s)
0x12d28  ldc.i4.1
0x12d29  newarr   [mscorlib]System.Object
0x12d2e  dup
0x12d2f  ldc.i4.0
0x12d30  ldarg.1
0x12d31  stelem.ref
0x12d32  call     void System.Deployment.Application.Logger::AddPhaseInformation(string messageFormat, object[] args)
0x12d37  ldloc.s  0xA
0x12d39  ldfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x12d3e  ldc.i4.2
0x12d3f  and
0x12d40  ldc.i4.0
0x12d41  cgt.un
0x12d43  ldloc.2
0x12d44  and
0x12d45  brtrue.s loc_12D5E
0x12d47  ldloc.s  0xA
0x12d49  ldfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x12d4e  ldc.i4.4
0x12d4f  and
0x12d50  brfalse  loc_12DF9
0x12d55  ldloc.s  5
0x12d57  ldloc.2
  ... truncated ...
```
