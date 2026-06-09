# System.Deployment.Application.SubscriptionStore::RollbackSubscription

- ea: `0x1f550`
- end: `0x1f5ef`
- name: `System.Deployment.Application.SubscriptionStore::RollbackSubscription`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update`

## callers

- `0x12a70`

## callees

- `0xda60`
- `0xe420`
- `0x146f0`
- `0x1d6f0`
- `0x1ece0`
- `0x1eec0`
- `0x1eee0`
- `0x1ef20`
- `0x1f550`
- `0x1fba0`
- `0x1fc60`
- `0x1ffb0`
- `0x20070`
- `0x23020`
- `0x23c30`
- `0x24b30`

## string_xrefs

- `0x1f568`: `Ex_SubNoRollbackDeployment`

## pseudocode

```c

```

## disassembly

```asm
0x1f550  ldarg.0
0x1f551  ldarg.1
0x1f552  call     instance class [mscorlib]System.IDisposable System.Deployment.Application.SubscriptionStore::AcquireSubscriptionWriterLock(class System.Deployment.Application.SubscriptionState subState)
0x1f557  stloc.0
0x1f558  ldarg.0
0x1f559  ldarg.1
0x1f55a  call     instance void System.Deployment.Application.SubscriptionStore::CheckInstalledAndShellVisible(class System.Deployment.Application.SubscriptionState subState)
0x1f55f  ldarg.1
0x1f560  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_RollbackDeployment()
0x1f565  brtrue.s loc_1F578
0x1f567  ldc.i4.8
0x1f568  ldstr    aExSubnorollbac// "Ex_SubNoRollbackDeployment"
0x1f56d  call     string System.Deployment.Application.Resources::GetString(string s)
0x1f572  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x1f577  throw
0x1f578  ldarg.1
0x1f579  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentApplicationManifest()
0x1f57e  brfalse.s loc_1F5C9
0x1f580  ldnull
0x1f581  stloc.1
0x1f582  ldarg.1
0x1f583  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0x1f588  brfalse.s loc_1F5A8
0x1f58a  ldarg.1
0x1f58b  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0x1f590  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x1f595  brfalse.s loc_1F5A8
0x1f597  ldarg.1
0x1f598  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0x1f59d  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x1f5a2  callvirt instance string System.Deployment.Application.Manifest.Description::get_Product()
0x1f5a7  stloc.1
0x1f5a8  ldloc.1
0x1f5a9  brtrue.s loc_1F5B7
0x1f5ab  ldarg.1
0x1f5ac  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f5b1  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_Name()
0x1f5b6  stloc.1
0x1f5b7  ldarg.1
0x1f5b8  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f5bd  ldarg.1
0x1f5be  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentApplicationManifest()
0x1f5c3  ldloc.1
0x1f5c4  call     void System.Deployment.Application.ShellExposure::RemoveShellExtensions(class System.Deployment.Application.DefinitionIdentity subId, class System.Deployment.Application.Manifest.AssemblyManifest appManifest, string productName)
0x1f5c9  ldarg.0
0x1f5ca  ldfld    class System.Deployment.Application.ComponentStore System.Deployment.Application.SubscriptionStore::_compStore
0x1f5cf  ldarg.1
0x1f5d0  callvirt instance void System.Deployment.Application.ComponentStore::RollbackSubscription(class System.Deployment.Application.SubscriptionState subState)
0x1f5d5  ldarg.0
0x1f5d6  ldarg.1
0x1f5d7  call     instance void System.Deployment.Application.SubscriptionStore::UpdateSubscriptionExposure(class System.Deployment.Application.SubscriptionState subState)
0x1f5dc  ldarg.1
0x1f5dd  call     void System.Deployment.Application.SubscriptionStore::OnDeploymentRemoved(class System.Deployment.Application.SubscriptionState subState)
0x1f5e2  leave.s  loc_1F5EE
0x1f5e4  ldloc.0
0x1f5e5  brfalse.s loc_1F5ED
0x1f5e7  ldloc.0
0x1f5e8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f5ed  endfinally
0x1f5ee  ret
```
