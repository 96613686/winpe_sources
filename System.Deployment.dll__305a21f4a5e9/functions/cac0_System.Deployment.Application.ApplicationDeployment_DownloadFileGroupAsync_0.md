# System.Deployment.Application.ApplicationDeployment::DownloadFileGroupAsync_0

- ea: `0xcac0`
- end: `0xcb0f`
- name: `System.Deployment.Application.ApplicationDeployment::DownloadFileGroupAsync_0`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0xcab0`

## callees

- `0xcac0`
- `0xcc10`
- `0x10e40`
- `0x1ecd0`
- `0x1ed40`
- `0x23020`

## string_xrefs

- `0xcaf1`: `Ex_DownloadGroupAfterUpdate`

## pseudocode

```c

```

## disassembly

```asm
0xcac0  ldarg.1
0xcac1  brtrue.s loc_CACE
0xcac3  ldstr    aGroupname// "groupName"
0xcac8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xcacd  throw
0xcace  ldarg.0
0xcacf  ldfld    class System.Deployment.Application.SubscriptionState System.Deployment.Application.ApplicationDeployment::_subState
0xcad4  callvirt instance void System.Deployment.Application.SubscriptionState::Invalidate()
0xcad9  ldarg.0
0xcada  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.ApplicationDeployment::_fullAppId
0xcadf  ldarg.0
0xcae0  ldfld    class System.Deployment.Application.SubscriptionState System.Deployment.Application.ApplicationDeployment::_subState
0xcae5  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0xcaea  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xcaef  brtrue.s loc_CB01
0xcaf1  ldstr    aExDownloadgrou// "Ex_DownloadGroupAfterUpdate"
0xcaf6  call     string System.Deployment.Application.Resources::GetString(string s)
0xcafb  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xcb00  throw
0xcb01  ldarg.0
0xcb02  call     instance class System.Deployment.Application.DeploymentManager System.Deployment.Application.ApplicationDeployment::get_SyncGroupDeploymentManager()
0xcb07  ldarg.1
0xcb08  ldarg.2
0xcb09  callvirt instance void System.Deployment.Application.DeploymentManager::SynchronizeAsync(string groupName, object userState)
0xcb0e  ret
```
