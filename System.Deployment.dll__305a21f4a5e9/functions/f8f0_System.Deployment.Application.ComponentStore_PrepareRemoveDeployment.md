# System.Deployment.Application.ComponentStore::PrepareRemoveDeployment

- ea: `0xf8f0`
- end: `0xf930`
- name: `System.Deployment.Application.ComponentStore::PrepareRemoveDeployment`
- size: `64`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0xe200`
- `0xf860`

## callees

- `0xd620`
- `0xd880`
- `0xf1a0`
- `0xf8f0`
- `0xf990`
- `0xf9d0`
- `0x1ed20`
- `0x284a0`
- `0x28620`

## pseudocode

```c

```

## disassembly

```asm
0xf8f0  ldarg.3
0xf8f1  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.DefinitionAppId::ToDeploymentAppId()
0xf8f6  stloc.0
0xf8f7  ldarg.2
0xf8f8  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsShellVisible()
0xf8fd  brfalse.s loc_F90A
0xf8ff  ldarg.0
0xf900  ldarg.1
0xf901  ldloc.0
0xf902  ldc.i4.0
0xf903  call     instance void System.Deployment.Application.ComponentStore::PrepareInstallUninstallDeployment(class StoreTransactionContext storeTxn, class System.Deployment.Application.DefinitionAppId deployAppId, bool isInstall)
0xf908  br.s     loc_F913
0xf90a  ldarg.0
0xf90b  ldarg.1
0xf90c  ldloc.0
0xf90d  ldc.i4.0
0xf90e  call     instance void System.Deployment.Application.ComponentStore::PreparePinUnpinDeployment(class StoreTransactionContext storeTxn, class System.Deployment.Application.DefinitionAppId deployAppId, bool isPin)
0xf913  ldarg.0
0xf914  ldarg.1
0xf915  ldarg.3
0xf916  ldnull
0xf917  call     instance void System.Deployment.Application.ComponentStore::PrepareSetDeploymentProperties(class StoreTransactionContext storeTxn, class System.Deployment.Application.DefinitionAppId appId, class System.Deployment.Application.CommitApplicationParams commitParams)
0xf91c  ldarg.1
0xf91d  callvirt instance class ScavengeContext StoreTransactionContext::get_ScavengeContext()
0xf922  ldloc.0
0xf923  ldarg.2
0xf924  callvirt instance void ScavengeContext::AddDeploymentToUnpin(class System.Deployment.Application.DefinitionAppId deployAppId, class System.Deployment.Application.SubscriptionState subState)
0xf929  ldarg.3
0xf92a  call     void System.Deployment.Application.ApplicationTrust::RemoveCachedTrust(class System.Deployment.Application.DefinitionAppId appId)
0xf92f  ret
```
