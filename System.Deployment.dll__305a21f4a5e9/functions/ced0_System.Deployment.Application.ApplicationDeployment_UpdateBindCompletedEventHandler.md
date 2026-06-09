# System.Deployment.Application.ApplicationDeployment::UpdateBindCompletedEventHandler

- ea: `0xced0`
- end: `0xcfc3`
- name: `System.Deployment.Application.ApplicationDeployment::UpdateBindCompletedEventHandler`
- size: `243`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0xced0`
- `0xcfd0`
- `0xd120`
- `0xd200`
- `0xd2e0`
- `0x10d00`
- `0x10d40`
- `0x10d80`
- `0x11240`
- `0x12650`
- `0x12670`
- `0x14ba0`
- `0x1f8b0`

## pseudocode

```c

```

## disassembly

```asm
0xced0  ldnull
0xced1  stloc.0
0xced2  ldnull
0xced3  stloc.1
0xced4  ldc.i4.0
0xced5  stloc.2
0xced6  ldstr    aFulltrust_0// "FullTrust"
0xcedb  newobj   instance void [mscorlib]System.Security.NamedPermissionSet::.ctor(string)
0xcee0  call     instance void [mscorlib]System.Security.PermissionSet::Assert()
0xcee5  ldarg.1
0xcee6  castclass System.Deployment.Application.DeploymentManager
0xceeb  stloc.1
0xceec  ldarg.2
0xceed  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xcef2  brtrue   loc_CF90
0xcef7  ldarg.2
0xcef8  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xcefd  brtrue   loc_CF90
0xcf02  ldarg.0
0xcf03  ldloc.1
0xcf04  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0xcf09  call     instance class System.Deployment.Application.UpdateCheckInfo System.Deployment.Application.ApplicationDeployment::DetermineUpdateCheckResult(class System.Deployment.Application.ActivationDescription actDesc)
0xcf0e  stloc.3
0xcf0f  ldloc.3
0xcf10  callvirt instance bool System.Deployment.Application.UpdateCheckInfo::get_UpdateAvailable()
0xcf15  brfalse.s loc_CF48
0xcf17  ldloc.1
0xcf18  callvirt instance void System.Deployment.Application.DeploymentManager::DeterminePlatformRequirements()
0xcf1d  newobj   instance void System.Deployment.Application.TrustParams::.ctor()
0xcf22  stloc.s  4
0xcf24  ldloc.s  4
0xcf26  ldc.i4.1
0xcf27  callvirt instance void System.Deployment.Application.TrustParams::set_NoPrompt(bool value)
0xcf2c  ldloc.1
0xcf2d  ldloc.s  4
0xcf2f  callvirt instance void System.Deployment.Application.DeploymentManager::DetermineTrust(class System.Deployment.Application.TrustParams trustParams)
0xcf34  leave.s  loc_CF48
0xcf36  pop
0xcf37  ldloc.1
0xcf38  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0xcf3d  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdateInPKTGroup
0xcf42  brtrue.s loc_CF46
0xcf44  rethrow
0xcf46  leave.s  loc_CF48
0xcf48  ldarg.0
0xcf49  ldloc.3
0xcf4a  ldloc.1
0xcf4b  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0xcf50  call     instance void System.Deployment.Application.ApplicationDeployment::ProcessUpdateCheckResult(class System.Deployment.Application.UpdateCheckInfo info, class System.Deployment.Application.ActivationDescription actDesc)
0xcf55  ldloc.3
0xcf56  callvirt instance bool System.Deployment.Application.UpdateCheckInfo::get_UpdateAvailable()
0xcf5b  brfalse.s loc_CF65
0xcf5d  ldc.i4.1
0xcf5e  stloc.2
0xcf5f  ldloc.1
0xcf60  callvirt instance void System.Deployment.Application.DeploymentManager::SynchronizeAsync()
0xcf65  ldloc.1
0xcf66  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0xcf6b  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdateInPKTGroup
0xcf70  brfalse.s loc_CF97
0xcf72  ldarg.0
0xcf73  ldarg.0
0xcf74  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationDeployment::_subStore
0xcf79  ldloc.1
0xcf7a  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0xcf7f  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xcf84  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0xcf89  stfld    class System.Deployment.Application.SubscriptionState System.Deployment.Application.ApplicationDeployment::_subState
0xcf8e  br.s     loc_CF97
0xcf90  ldarg.2
0xcf91  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xcf96  stloc.0
0xcf97  leave.s  loc_CFC2
0xcf99  stloc.s  5
0xcf9b  ldloc.s  5
0xcf9d  call     bool System.Deployment.Application.ExceptionUtility::IsHardException(class [mscorlib]System.Exception exception)
0xcfa2  brfalse.s loc_CFA6
0xcfa4  rethrow
0xcfa6  ldloc.s  5
0xcfa8  stloc.0
0xcfa9  leave.s  loc_CFC2
0xcfab  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0xcfb0  ldloc.2
0xcfb1  brtrue.s loc_CFC1
0xcfb3  ldarg.0
0xcfb4  ldloc.1
0xcfb5  ldloc.0
0xcfb6  ldarg.2
0xcfb7  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xcfbc  call     instance void System.Deployment.Application.ApplicationDeployment::EndUpdateAsync(class System.Deployment.Application.DeploymentManager dm, class [mscorlib]System.Exception error, bool cancelled)
0xcfc1  endfinally
0xcfc2  ret
```
