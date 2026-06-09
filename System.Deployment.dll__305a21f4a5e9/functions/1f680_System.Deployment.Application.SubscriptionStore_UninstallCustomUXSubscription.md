# System.Deployment.Application.SubscriptionStore::UninstallCustomUXSubscription

- ea: `0x1f680`
- end: `0x1f717`
- name: `System.Deployment.Application.SubscriptionStore::UninstallCustomUXSubscription`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x16030`
- `0x1f1c0`

## callees

- `0xda60`
- `0xe3d0`
- `0x1d6f0`
- `0x1ece0`
- `0x1ee80`
- `0x1eee0`
- `0x1ef20`
- `0x1f680`
- `0x1fbb0`
- `0x1fc60`
- `0x20070`
- `0x23020`
- `0x23c30`
- `0x24b30`

## string_xrefs

- `0x1f697`: `Ex_CannotCallUninstallCustomUXApplication`

## pseudocode

```c

```

## disassembly

```asm
0x1f680  ldarg.0
0x1f681  ldarg.1
0x1f682  call     instance class [mscorlib]System.IDisposable System.Deployment.Application.SubscriptionStore::AcquireSubscriptionWriterLock(class System.Deployment.Application.SubscriptionState subState)
0x1f687  stloc.0
0x1f688  ldarg.1
0x1f689  call     void System.Deployment.Application.SubscriptionStore::CheckInstalled(class System.Deployment.Application.SubscriptionState subState)
0x1f68e  ldarg.1
0x1f68f  callvirt instance valuetype System.Deployment.Application.AppType System.Deployment.Application.SubscriptionState::get_appType()
0x1f694  ldc.i4.4
0x1f695  beq.s    loc_1F6A7
0x1f697  ldstr    aExCannotcallun// "Ex_CannotCallUninstallCustomUXApplicati"...
0x1f69c  call     string System.Deployment.Application.Resources::GetString(string s)
0x1f6a1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1f6a6  throw
0x1f6a7  ldarg.1
0x1f6a8  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentApplicationManifest()
0x1f6ad  brfalse.s loc_1F6F8
0x1f6af  ldnull
0x1f6b0  stloc.1
0x1f6b1  ldarg.1
0x1f6b2  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0x1f6b7  brfalse.s loc_1F6D7
0x1f6b9  ldarg.1
0x1f6ba  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0x1f6bf  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x1f6c4  brfalse.s loc_1F6D7
0x1f6c6  ldarg.1
0x1f6c7  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0x1f6cc  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x1f6d1  callvirt instance string System.Deployment.Application.Manifest.Description::get_Product()
0x1f6d6  stloc.1
0x1f6d7  ldloc.1
0x1f6d8  brtrue.s loc_1F6E6
0x1f6da  ldarg.1
0x1f6db  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f6e0  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_Name()
0x1f6e5  stloc.1
0x1f6e6  ldarg.1
0x1f6e7  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f6ec  ldarg.1
0x1f6ed  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentApplicationManifest()
0x1f6f2  ldloc.1
0x1f6f3  call     void System.Deployment.Application.ShellExposure::RemoveShellExtensions(class System.Deployment.Application.DefinitionIdentity subId, class System.Deployment.Application.Manifest.AssemblyManifest appManifest, string productName)
0x1f6f8  ldarg.0
0x1f6f9  ldfld    class System.Deployment.Application.ComponentStore System.Deployment.Application.SubscriptionStore::_compStore
0x1f6fe  ldarg.1
0x1f6ff  callvirt instance void System.Deployment.Application.ComponentStore::RemoveSubscription(class System.Deployment.Application.SubscriptionState subState)
0x1f704  ldarg.1
0x1f705  call     void System.Deployment.Application.SubscriptionStore::OnDeploymentRemoved(class System.Deployment.Application.SubscriptionState subState)
0x1f70a  leave.s  loc_1F716
0x1f70c  ldloc.0
0x1f70d  brfalse.s loc_1F715
0x1f70f  ldloc.0
0x1f710  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f715  endfinally
0x1f716  ret
```
