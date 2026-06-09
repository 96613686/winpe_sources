# System.Deployment.Application.ApplicationDeployment::Update

- ea: `0xc850`
- end: `0xc939`
- name: `System.Deployment.Application.ApplicationDeployment::Update`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update`

## callees

- `0xc850`
- `0xcbe0`
- `0xd120`
- `0xd200`
- `0xd2e0`
- `0x10c80`
- `0x10d00`
- `0x10d40`
- `0x10de0`
- `0x111c0`
- `0x11240`
- `0x12650`
- `0x12670`
- `0x1f8b0`
- `0x23020`

## pseudocode

```c

```

## disassembly

```asm
0xc850  ldstr    aFulltrust_0// "FullTrust"
0xc855  newobj   instance void [mscorlib]System.Security.NamedPermissionSet::.ctor(string)
0xc85a  call     instance void [mscorlib]System.Security.PermissionSet::Demand()
0xc85f  ldarg.0
0xc860  ldflda   int32 System.Deployment.Application.ApplicationDeployment::_guard
0xc865  ldc.i4.2
0xc866  ldc.i4.0
0xc867  call     int32 [mscorlib]System.Threading.Interlocked::CompareExchange(int32&, int32, int32)
0xc86c  brfalse.s loc_C87E
0xc86e  ldstr    aExSingleoperat// "Ex_SingleOperation"
0xc873  call     string System.Deployment.Application.Resources::GetString(string s)
0xc878  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xc87d  throw
0xc87e  ldarg.0
0xc87f  ldc.i4.0
0xc880  stfld    bool System.Deployment.Application.ApplicationDeployment::_cancellationPending
0xc885  ldarg.0
0xc886  call     instance class System.Deployment.Application.DeploymentManager System.Deployment.Application.ApplicationDeployment::CreateDeploymentManager()
0xc88b  stloc.0
0xc88c  ldloc.0
0xc88d  callvirt instance class [mscorlib]System.ActivationContext System.Deployment.Application.DeploymentManager::Bind()
0xc892  pop
0xc893  ldarg.0
0xc894  ldloc.0
0xc895  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0xc89a  call     instance class System.Deployment.Application.UpdateCheckInfo System.Deployment.Application.ApplicationDeployment::DetermineUpdateCheckResult(class System.Deployment.Application.ActivationDescription actDesc)
0xc89f  stloc.1
0xc8a0  ldloc.1
0xc8a1  callvirt instance bool System.Deployment.Application.UpdateCheckInfo::get_UpdateAvailable()
0xc8a6  brfalse.s loc_C8D6
0xc8a8  ldloc.0
0xc8a9  callvirt instance void System.Deployment.Application.DeploymentManager::DeterminePlatformRequirements()
0xc8ae  newobj   instance void System.Deployment.Application.TrustParams::.ctor()
0xc8b3  stloc.2
0xc8b4  ldloc.2
0xc8b5  ldc.i4.1
0xc8b6  callvirt instance void System.Deployment.Application.TrustParams::set_NoPrompt(bool value)
0xc8bb  ldloc.0
0xc8bc  ldloc.2
0xc8bd  callvirt instance void System.Deployment.Application.DeploymentManager::DetermineTrust(class System.Deployment.Application.TrustParams trustParams)
0xc8c2  leave.s  loc_C8D6
0xc8c4  pop
0xc8c5  ldloc.0
0xc8c6  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0xc8cb  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdateInPKTGroup
0xc8d0  brtrue.s loc_C8D4
0xc8d2  rethrow
0xc8d4  leave.s  loc_C8D6
0xc8d6  ldarg.0
0xc8d7  ldloc.1
0xc8d8  ldloc.0
0xc8d9  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0xc8de  call     instance void System.Deployment.Application.ApplicationDeployment::ProcessUpdateCheckResult(class System.Deployment.Application.UpdateCheckInfo info, class System.Deployment.Application.ActivationDescription actDesc)
0xc8e3  ldloc.1
0xc8e4  callvirt instance bool System.Deployment.Application.UpdateCheckInfo::get_UpdateAvailable()
0xc8e9  brtrue.s loc_C8EF
0xc8eb  ldc.i4.0
0xc8ec  stloc.3
0xc8ed  leave.s  loc_C937
0xc8ef  ldloc.0
0xc8f0  callvirt instance void System.Deployment.Application.DeploymentManager::Synchronize()
0xc8f5  ldloc.0
0xc8f6  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0xc8fb  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdateInPKTGroup
0xc900  brfalse.s loc_C91E
0xc902  ldarg.0
0xc903  ldarg.0
0xc904  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationDeployment::_subStore
0xc909  ldloc.0
0xc90a  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0xc90f  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xc914  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0xc919  stfld    class System.Deployment.Application.SubscriptionState System.Deployment.Application.ApplicationDeployment::_subState
0xc91e  leave.s  loc_C935
0xc920  ldloc.0
0xc921  callvirt instance void System.Deployment.Application.DeploymentManager::Dispose()
0xc926  endfinally
0xc927  ldarg.0
0xc928  ldflda   int32 System.Deployment.Application.ApplicationDeployment::_guard
0xc92d  ldc.i4.0
0xc92e  call     int32 [mscorlib]System.Threading.Interlocked::Exchange(int32&, int32)
0xc933  pop
0xc934  endfinally
0xc935  ldc.i4.1
0xc936  ret
0xc937  ldloc.3
0xc938  ret
```
