# System.Deployment.Application.DeploymentServiceCom::CleanOnlineAppCacheInternal

- ea: `0x12e70`
- end: `0x12eb9`
- name: `System.Deployment.Application.DeploymentServiceCom::CleanOnlineAppCacheInternal`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x12a50`

## callees

- `0x12e70`
- `0x17640`
- `0x17660`
- `0x17c60`
- `0x17cc0`
- `0x1f0b0`
- `0x1f190`
- `0x23020`

## string_xrefs

- `0x12e87`: `Ex_CleanOnlineAppCache`
- `0x12e9c`: `CleanOnlineCache_Failed`
- `0x12ea3`: `CleanOnlineCache_Completed`

## pseudocode

```c

```

## disassembly

```asm
0x12e70  ldc.i4.0
0x12e71  stloc.0
0x12e72  call     class LogIdentity System.Deployment.Application.Logger::StartCurrentThreadLogging()
0x12e77  pop
0x12e78  call     class System.Deployment.Application.SubscriptionStore System.Deployment.Application.SubscriptionStore::get_CurrentUser()
0x12e7d  callvirt instance void System.Deployment.Application.SubscriptionStore::CleanOnlineAppCache()
0x12e82  ldc.i4.1
0x12e83  stloc.0
0x12e84  leave.s  loc_12EB8
0x12e86  stloc.1
0x12e87  ldstr    aExCleanonlinea// "Ex_CleanOnlineAppCache"
0x12e8c  call     string System.Deployment.Application.Resources::GetString(string s)
0x12e91  ldloc.1
0x12e92  call     void System.Deployment.Application.Logger::AddErrorInformation(string message, class [mscorlib]System.Exception exception)
0x12e97  rethrow
0x12e99  ldloc.0
0x12e9a  brtrue.s loc_12EA3
0x12e9c  ldstr    aCleanonlinecac// "CleanOnlineCache_Failed"
0x12ea1  br.s     loc_12EA8
0x12ea3  ldstr    aCleanonlinecac_0// "CleanOnlineCache_Completed"
0x12ea8  call     string System.Deployment.Application.Resources::GetString(string s)
0x12ead  call     void System.Deployment.Application.Logger::AddPhaseInformation(string message)
0x12eb2  call     void System.Deployment.Application.Logger::EndCurrentThreadLogging()
0x12eb7  endfinally
0x12eb8  ret
```
