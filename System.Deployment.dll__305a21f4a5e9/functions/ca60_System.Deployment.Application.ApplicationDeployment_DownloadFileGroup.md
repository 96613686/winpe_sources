# System.Deployment.Application.ApplicationDeployment::DownloadFileGroup

- ea: `0xca60`
- end: `0xcaae`
- name: `System.Deployment.Application.ApplicationDeployment::DownloadFileGroup`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0xca60`
- `0xcc10`
- `0x10ec0`
- `0x1ecd0`
- `0x1ed40`
- `0x23020`

## string_xrefs

- `0xca91`: `Ex_DownloadGroupAfterUpdate`

## pseudocode

```c

```

## disassembly

```asm
0xca60  ldarg.1
0xca61  brtrue.s loc_CA6E
0xca63  ldstr    aGroupname// "groupName"
0xca68  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xca6d  throw
0xca6e  ldarg.0
0xca6f  ldfld    class System.Deployment.Application.SubscriptionState System.Deployment.Application.ApplicationDeployment::_subState
0xca74  callvirt instance void System.Deployment.Application.SubscriptionState::Invalidate()
0xca79  ldarg.0
0xca7a  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.ApplicationDeployment::_fullAppId
0xca7f  ldarg.0
0xca80  ldfld    class System.Deployment.Application.SubscriptionState System.Deployment.Application.ApplicationDeployment::_subState
0xca85  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0xca8a  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xca8f  brtrue.s loc_CAA1
0xca91  ldstr    aExDownloadgrou// "Ex_DownloadGroupAfterUpdate"
0xca96  call     string System.Deployment.Application.Resources::GetString(string s)
0xca9b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xcaa0  throw
0xcaa1  ldarg.0
0xcaa2  call     instance class System.Deployment.Application.DeploymentManager System.Deployment.Application.ApplicationDeployment::get_SyncGroupDeploymentManager()
0xcaa7  ldarg.1
0xcaa8  callvirt instance void System.Deployment.Application.DeploymentManager::Synchronize(string groupName)
0xcaad  ret
```
