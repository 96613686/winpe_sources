# System.Deployment.Application.SubscriptionStore::UninstallCustomHostSpecifiedSubscription

- ea: `0x1f720`
- end: `0x1f766`
- name: `System.Deployment.Application.SubscriptionStore::UninstallCustomHostSpecifiedSubscription`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x16060`
- `0x1f1c0`

## callees

- `0xe3d0`
- `0x1ee80`
- `0x1f720`
- `0x1fbb0`
- `0x1fc60`
- `0x20070`
- `0x23020`

## string_xrefs

- `0x1f737`: `Ex_CannotCallUninstallCustomAddIn`

## pseudocode

```c

```

## disassembly

```asm
0x1f720  ldarg.0
0x1f721  ldarg.1
0x1f722  call     instance class [mscorlib]System.IDisposable System.Deployment.Application.SubscriptionStore::AcquireSubscriptionWriterLock(class System.Deployment.Application.SubscriptionState subState)
0x1f727  stloc.0
0x1f728  ldarg.1
0x1f729  call     void System.Deployment.Application.SubscriptionStore::CheckInstalled(class System.Deployment.Application.SubscriptionState subState)
0x1f72e  ldarg.1
0x1f72f  callvirt instance valuetype System.Deployment.Application.AppType System.Deployment.Application.SubscriptionState::get_appType()
0x1f734  ldc.i4.3
0x1f735  beq.s    loc_1F747
0x1f737  ldstr    aExCannotcallun_0// "Ex_CannotCallUninstallCustomAddIn"
0x1f73c  call     string System.Deployment.Application.Resources::GetString(string s)
0x1f741  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1f746  throw
0x1f747  ldarg.0
0x1f748  ldfld    class System.Deployment.Application.ComponentStore System.Deployment.Application.SubscriptionStore::_compStore
0x1f74d  ldarg.1
0x1f74e  callvirt instance void System.Deployment.Application.ComponentStore::RemoveSubscription(class System.Deployment.Application.SubscriptionState subState)
0x1f753  ldarg.1
0x1f754  call     void System.Deployment.Application.SubscriptionStore::OnDeploymentRemoved(class System.Deployment.Application.SubscriptionState subState)
0x1f759  leave.s  loc_1F765
0x1f75b  ldloc.0
0x1f75c  brfalse.s loc_1F764
0x1f75e  ldloc.0
0x1f75f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f764  endfinally
0x1f765  ret
```
