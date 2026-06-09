# System.Deployment.Application.SubscriptionStore::CheckOnlineShellVisibleConflict

- ea: `0x1fd60`
- end: `0x1fd87`
- name: `System.Deployment.Application.SubscriptionStore::CheckOnlineShellVisibleConflict`
- size: `39`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1f9c0`
- `0x1fad0`

## callees

- `0x146f0`
- `0x1ed20`
- `0x1fd60`
- `0x23020`
- `0x23fe0`
- `0x24b90`

## string_xrefs

- `0x1fd76`: `Ex_OnlineAlreadyShellVisible`

## pseudocode

```c

```

## disassembly

```asm
0x1fd60  ldarg.1
0x1fd61  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x1fd66  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_Install()
0x1fd6b  brtrue.s loc_1FD86
0x1fd6d  ldarg.0
0x1fd6e  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsShellVisible()
0x1fd73  brfalse.s loc_1FD86
0x1fd75  ldc.i4.8
0x1fd76  ldstr    aExOnlinealread// "Ex_OnlineAlreadyShellVisible"
0x1fd7b  call     string System.Deployment.Application.Resources::GetString(string s)
0x1fd80  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x1fd85  throw
0x1fd86  ret
```
