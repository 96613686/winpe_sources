# System.Deployment.Application.ApplicationDeployment::CheckForUpdateBindCompletedEventHandler

- ea: `0xcd50`
- end: `0xcec9`
- name: `System.Deployment.Application.ApplicationDeployment::CheckForUpdateBindCompletedEventHandler`
- size: `377`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0xcbd0`
- `0xcd50`
- `0xd120`
- `0xd200`
- `0xd2e0`
- `0xd2f0`
- `0xd300`
- `0xd310`
- `0xd320`
- `0xd370`
- `0xd3b0`
- `0x10d00`
- `0x10d40`
- `0x11120`
- `0x111a0`
- `0x111c0`
- `0x11240`
- `0x12650`
- `0x12670`
- `0x12690`
- `0x127e0`
- `0x14ba0`

## pseudocode

```c

```

## disassembly

```asm
0xcd50  ldnull
0xcd51  stloc.0
0xcd52  ldnull
0xcd53  stloc.1
0xcd54  ldc.i4.0
0xcd55  stloc.2
0xcd56  ldnull
0xcd57  stloc.3
0xcd58  ldc.i4.0
0xcd59  stloc.s  4
0xcd5b  ldnull
0xcd5c  stloc.s  5
0xcd5e  ldc.i4.0
0xcd5f  conv.i8
0xcd60  stloc.s  6
0xcd62  ldstr    aFulltrust_0// "FullTrust"
0xcd67  newobj   instance void [mscorlib]System.Security.NamedPermissionSet::.ctor(string)
0xcd6c  call     instance void [mscorlib]System.Security.PermissionSet::Assert()
0xcd71  ldarg.1
0xcd72  castclass System.Deployment.Application.DeploymentManager
0xcd77  stloc.1
0xcd78  ldarg.2
0xcd79  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xcd7e  brtrue   loc_CE14
0xcd83  ldarg.2
0xcd84  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xcd89  brtrue   loc_CE14
0xcd8e  ldarg.0
0xcd8f  ldloc.1
0xcd90  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0xcd95  call     instance class System.Deployment.Application.UpdateCheckInfo System.Deployment.Application.ApplicationDeployment::DetermineUpdateCheckResult(class System.Deployment.Application.ActivationDescription actDesc)
0xcd9a  stloc.s  7
0xcd9c  ldloc.s  7
0xcd9e  callvirt instance bool System.Deployment.Application.UpdateCheckInfo::get_UpdateAvailable()
0xcda3  brfalse.s loc_CDD6
0xcda5  ldloc.1
0xcda6  callvirt instance void System.Deployment.Application.DeploymentManager::DeterminePlatformRequirements()
0xcdab  newobj   instance void System.Deployment.Application.TrustParams::.ctor()
0xcdb0  stloc.s  8
0xcdb2  ldloc.s  8
0xcdb4  ldc.i4.1
0xcdb5  callvirt instance void System.Deployment.Application.TrustParams::set_NoPrompt(bool value)
0xcdba  ldloc.1
0xcdbb  ldloc.s  8
0xcdbd  callvirt instance void System.Deployment.Application.DeploymentManager::DetermineTrust(class System.Deployment.Application.TrustParams trustParams)
0xcdc2  leave.s  loc_CDD6
0xcdc4  pop
0xcdc5  ldloc.1
0xcdc6  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0xcdcb  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdateInPKTGroup
0xcdd0  brtrue.s loc_CDD4
0xcdd2  rethrow
0xcdd4  leave.s  loc_CDD6
0xcdd6  ldarg.0
0xcdd7  ldloc.s  7
0xcdd9  ldloc.1
0xcdda  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0xcddf  call     instance void System.Deployment.Application.ApplicationDeployment::ProcessUpdateCheckResult(class System.Deployment.Application.UpdateCheckInfo info, class System.Deployment.Application.ActivationDescription actDesc)
0xcde4  ldloc.s  7
0xcde6  callvirt instance bool System.Deployment.Application.UpdateCheckInfo::get_UpdateAvailable()
0xcdeb  brfalse.s loc_CE1B
0xcded  ldc.i4.1
0xcdee  stloc.2
0xcdef  ldloc.s  7
0xcdf1  callvirt instance class [mscorlib]System.Version System.Deployment.Application.UpdateCheckInfo::get_AvailableVersion()
0xcdf6  stloc.3
0xcdf7  ldloc.s  7
0xcdf9  callvirt instance bool System.Deployment.Application.UpdateCheckInfo::get_IsUpdateRequired()
0xcdfe  stloc.s  4
0xce00  ldloc.s  7
0xce02  callvirt instance class [mscorlib]System.Version System.Deployment.Application.UpdateCheckInfo::get_MinimumRequiredVersion()
0xce07  stloc.s  5
0xce09  ldloc.s  7
0xce0b  callvirt instance int64 System.Deployment.Application.UpdateCheckInfo::get_UpdateSizeBytes()
0xce10  stloc.s  6
0xce12  br.s     loc_CE1B
0xce14  ldarg.2
0xce15  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xce1a  stloc.0
0xce1b  leave    loc_CEC8
0xce20  stloc.s  9
0xce22  ldloc.s  9
0xce24  call     bool System.Deployment.Application.ExceptionUtility::IsHardException(class [mscorlib]System.Exception exception)
0xce29  brfalse.s loc_CE2D
0xce2b  rethrow
0xce2d  ldloc.s  9
0xce2f  stloc.0
0xce30  leave    loc_CEC8
0xce35  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0xce3a  ldarg.0
0xce3b  ldflda   int32 System.Deployment.Application.ApplicationDeployment::_guard
0xce40  ldc.i4.0
0xce41  call     int32 [mscorlib]System.Threading.Interlocked::Exchange(int32&, int32)
0xce46  pop
0xce47  ldloc.0
0xce48  ldarg.2
0xce49  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xce4e  ldnull
0xce4f  ldloc.2
0xce50  ldloc.3
0xce51  ldloc.s  4
0xce53  ldloc.s  5
0xce55  ldloc.s  6
0xce57  newobj   instance void System.Deployment.Application.CheckForUpdateCompletedEventArgs::.ctor(class [mscorlib]System.Exception error, bool cancelled, object userState, bool updateAvailable, class [mscorlib]System.Version availableVersion, bool isUpdateRequired, class [mscorlib]System.Version minimumRequiredVersion, int64 updateSize)
0xce5c  stloc.s  0xA
0xce5e  ldarg.0
0xce5f  call     instance class [System]System.ComponentModel.EventHandlerList System.Deployment.Application.ApplicationDeployment::get_Events()
0xce64  ldsfld   object System.Deployment.Application.ApplicationDeployment::checkForUpdateCompletedKey
0xce69  callvirt instance class [mscorlib]System.Delegate [System]System.ComponentModel.EventHandlerList::get_Item(object)
0xce6e  castclass System.Deployment.Application.CheckForUpdateCompletedEventHandler
0xce73  stloc.s  0xB
0xce75  ldloc.s  0xB
0xce77  brfalse.s loc_CE83
0xce79  ldloc.s  0xB
0xce7b  ldarg.0
0xce7c  ldloc.s  0xA
0xce7e  callvirt instance void System.Deployment.Application.CheckForUpdateCompletedEventHandler::Invoke(object sender, class System.Deployment.Application.CheckForUpdateCompletedEventArgs e)
0xce83  ldloc.1
0xce84  brfalse.s loc_CEC7
0xce86  ldloc.1
0xce87  ldarg.0
0xce88  ldftn    instance void System.Deployment.Application.ApplicationDeployment::CheckForUpdateProgressChangedEventHandler(object sender, class System.Deployment.Application.DeploymentProgressChangedEventArgs e)
0xce8e  newobj   instance void System.Deployment.Application.DeploymentProgressChangedEventHandler::.ctor(object object, native int method)
0xce93  callvirt instance void System.Deployment.Application.DeploymentManager::remove_ProgressChanged(class System.Deployment.Application.DeploymentProgressChangedEventHandler value)
0xce98  ldloc.1
0xce99  ldarg.0
0xce9a  ldftn    instance void System.Deployment.Application.ApplicationDeployment::CheckForUpdateBindCompletedEventHandler(object sender, class System.Deployment.Application.BindCompletedEventArgs e)
0xcea0  newobj   instance void System.Deployment.Application.BindCompletedEventHandler::.ctor(object object, native int method)
0xcea5  callvirt instance void System.Deployment.Application.DeploymentManager::remove_BindCompleted(class System.Deployment.Application.BindCompletedEventHandler value)
0xceaa  ldstr    aFulltrust_0// "FullTrust"
0xceaf  newobj   instance void [mscorlib]System.Security.NamedPermissionSet::.ctor(string)
0xceb4  call     instance void [mscorlib]System.Security.PermissionSet::Assert()
0xceb9  ldloc.1
0xceba  callvirt instance void System.Deployment.Application.DeploymentManager::Dispose()
0xcebf  leave.s  loc_CEC7
0xcec1  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0xcec6  endfinally
0xcec7  endfinally
0xcec8  ret
```
