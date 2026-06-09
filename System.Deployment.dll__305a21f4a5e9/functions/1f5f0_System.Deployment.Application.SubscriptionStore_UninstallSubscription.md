# System.Deployment.Application.SubscriptionStore::UninstallSubscription

- ea: `0x1f5f0`
- end: `0x1f67b`
- name: `System.Deployment.Application.SubscriptionStore::UninstallSubscription`
- size: `139`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0xabd0`
- `0x12a70`
- `0x1f1c0`

## callees

- `0xda60`
- `0xe3d0`
- `0x1d6f0`
- `0x1de90`
- `0x1ece0`
- `0x1eee0`
- `0x1ef20`
- `0x1f5f0`
- `0x1fba0`
- `0x1fc60`
- `0x1ffc0`
- `0x20070`
- `0x23c30`
- `0x24b30`

## pseudocode

```c

```

## disassembly

```asm
0x1f5f0  ldarg.0
0x1f5f1  ldarg.1
0x1f5f2  call     instance class [mscorlib]System.IDisposable System.Deployment.Application.SubscriptionStore::AcquireSubscriptionWriterLock(class System.Deployment.Application.SubscriptionState subState)
0x1f5f7  stloc.0
0x1f5f8  ldarg.0
0x1f5f9  ldarg.1
0x1f5fa  call     instance void System.Deployment.Application.SubscriptionStore::CheckInstalledAndShellVisible(class System.Deployment.Application.SubscriptionState subState)
0x1f5ff  ldarg.1
0x1f600  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentApplicationManifest()
0x1f605  brfalse.s loc_1F656
0x1f607  ldnull
0x1f608  stloc.1
0x1f609  ldarg.1
0x1f60a  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0x1f60f  brfalse.s loc_1F62F
0x1f611  ldarg.1
0x1f612  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0x1f617  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x1f61c  brfalse.s loc_1F62F
0x1f61e  ldarg.1
0x1f61f  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0x1f624  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x1f629  callvirt instance string System.Deployment.Application.Manifest.Description::get_Product()
0x1f62e  stloc.1
0x1f62f  ldloc.1
0x1f630  brtrue.s loc_1F63E
0x1f632  ldarg.1
0x1f633  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f638  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_Name()
0x1f63d  stloc.1
0x1f63e  ldarg.1
0x1f63f  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f644  ldarg.1
0x1f645  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentApplicationManifest()
0x1f64a  ldloc.1
0x1f64b  call     void System.Deployment.Application.ShellExposure::RemoveShellExtensions(class System.Deployment.Application.DefinitionIdentity subId, class System.Deployment.Application.Manifest.AssemblyManifest appManifest, string productName)
0x1f650  ldarg.1
0x1f651  call     void System.Deployment.Application.ShellExposure::RemovePins(class System.Deployment.Application.SubscriptionState subState)
0x1f656  ldarg.0
0x1f657  ldfld    class System.Deployment.Application.ComponentStore System.Deployment.Application.SubscriptionStore::_compStore
0x1f65c  ldarg.1
0x1f65d  callvirt instance void System.Deployment.Application.ComponentStore::RemoveSubscription(class System.Deployment.Application.SubscriptionState subState)
0x1f662  ldarg.1
0x1f663  call     void System.Deployment.Application.SubscriptionStore::RemoveSubscriptionExposure(class System.Deployment.Application.SubscriptionState subState)
0x1f668  ldarg.1
0x1f669  call     void System.Deployment.Application.SubscriptionStore::OnDeploymentRemoved(class System.Deployment.Application.SubscriptionState subState)
0x1f66e  leave.s  loc_1F67A
0x1f670  ldloc.0
0x1f671  brfalse.s loc_1F679
0x1f673  ldloc.0
0x1f674  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f679  endfinally
0x1f67a  ret
```
