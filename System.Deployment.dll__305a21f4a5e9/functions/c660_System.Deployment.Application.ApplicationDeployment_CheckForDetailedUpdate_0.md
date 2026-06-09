# System.Deployment.Application.ApplicationDeployment::CheckForDetailedUpdate_0

- ea: `0xc660`
- end: `0xc711`
- name: `System.Deployment.Application.ApplicationDeployment::CheckForDetailedUpdate_0`
- size: `177`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0xc650`
- `0xc730`

## callees

- `0xc660`
- `0xcbe0`
- `0xd120`
- `0xd200`
- `0xd2e0`
- `0x10c80`
- `0x10d00`
- `0x10d40`
- `0x111c0`
- `0x11240`
- `0x12650`
- `0x12670`
- `0x23020`

## pseudocode

```c

```

## disassembly

```asm
0xc660  ldstr    aFulltrust_0// "FullTrust"
0xc665  newobj   instance void [mscorlib]System.Security.NamedPermissionSet::.ctor(string)
0xc66a  call     instance void [mscorlib]System.Security.PermissionSet::Demand()
0xc66f  ldarg.0
0xc670  ldflda   int32 System.Deployment.Application.ApplicationDeployment::_guard
0xc675  ldc.i4.2
0xc676  ldc.i4.0
0xc677  call     int32 [mscorlib]System.Threading.Interlocked::CompareExchange(int32&, int32, int32)
0xc67c  brfalse.s loc_C68E
0xc67e  ldstr    aExSingleoperat// "Ex_SingleOperation"
0xc683  call     string System.Deployment.Application.Resources::GetString(string s)
0xc688  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xc68d  throw
0xc68e  ldarg.0
0xc68f  ldc.i4.0
0xc690  stfld    bool System.Deployment.Application.ApplicationDeployment::_cancellationPending
0xc695  ldnull
0xc696  stloc.0
0xc697  ldarg.0
0xc698  call     instance class System.Deployment.Application.DeploymentManager System.Deployment.Application.ApplicationDeployment::CreateDeploymentManager()
0xc69d  stloc.1
0xc69e  ldloc.1
0xc69f  callvirt instance class [mscorlib]System.ActivationContext System.Deployment.Application.DeploymentManager::Bind()
0xc6a4  pop
0xc6a5  ldarg.0
0xc6a6  ldloc.1
0xc6a7  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0xc6ac  call     instance class System.Deployment.Application.UpdateCheckInfo System.Deployment.Application.ApplicationDeployment::DetermineUpdateCheckResult(class System.Deployment.Application.ActivationDescription actDesc)
0xc6b1  stloc.0
0xc6b2  ldloc.0
0xc6b3  callvirt instance bool System.Deployment.Application.UpdateCheckInfo::get_UpdateAvailable()
0xc6b8  brfalse.s loc_C6E8
0xc6ba  ldloc.1
0xc6bb  callvirt instance void System.Deployment.Application.DeploymentManager::DeterminePlatformRequirements()
0xc6c0  newobj   instance void System.Deployment.Application.TrustParams::.ctor()
0xc6c5  stloc.2
0xc6c6  ldloc.2
0xc6c7  ldc.i4.1
0xc6c8  callvirt instance void System.Deployment.Application.TrustParams::set_NoPrompt(bool value)
0xc6cd  ldloc.1
0xc6ce  ldloc.2
0xc6cf  callvirt instance void System.Deployment.Application.DeploymentManager::DetermineTrust(class System.Deployment.Application.TrustParams trustParams)
0xc6d4  leave.s  loc_C6E8
0xc6d6  pop
0xc6d7  ldloc.1
0xc6d8  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0xc6dd  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdateInPKTGroup
0xc6e2  brtrue.s loc_C6E6
0xc6e4  rethrow
0xc6e6  leave.s  loc_C6E8
0xc6e8  ldarg.1
0xc6e9  brfalse.s loc_C6F8
0xc6eb  ldarg.0
0xc6ec  ldloc.0
0xc6ed  ldloc.1
0xc6ee  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0xc6f3  call     instance void System.Deployment.Application.ApplicationDeployment::ProcessUpdateCheckResult(class System.Deployment.Application.UpdateCheckInfo info, class System.Deployment.Application.ActivationDescription actDesc)
0xc6f8  leave.s  loc_C70F
0xc6fa  ldloc.1
0xc6fb  callvirt instance void System.Deployment.Application.DeploymentManager::Dispose()
0xc700  endfinally
0xc701  ldarg.0
0xc702  ldflda   int32 System.Deployment.Application.ApplicationDeployment::_guard
0xc707  ldc.i4.0
0xc708  call     int32 [mscorlib]System.Threading.Interlocked::Exchange(int32&, int32)
0xc70d  pop
0xc70e  endfinally
0xc70f  ldloc.0
0xc710  ret
```
