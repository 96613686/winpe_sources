# System.Deployment.Application.DeploymentServiceCom::CheckForDeploymentUpdateInternal

- ea: `0x12e10`
- end: `0x12e69`
- name: `System.Deployment.Application.DeploymentServiceCom::CheckForDeploymentUpdateInternal`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x12a20`

## callees

- `0x12e10`
- `0x12ec0`
- `0x17640`
- `0x17660`
- `0x178a0`
- `0x17c60`
- `0x17cc0`
- `0x1ecf0`
- `0x1f8f0`
- `0x23020`

## string_xrefs

- `0x12e53`: `Upd_Completed`

## pseudocode

```c

```

## disassembly

```asm
0x12e10  ldc.i4.0
0x12e11  stloc.0
0x12e12  call     class LogIdentity System.Deployment.Application.Logger::StartCurrentThreadLogging()
0x12e17  pop
0x12e18  ldarg.1
0x12e19  call     void System.Deployment.Application.Logger::SetTextualSubscriptionIdentity(string textualIdentity)
0x12e1e  ldarg.0
0x12e1f  ldarg.1
0x12e20  call     instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.DeploymentServiceCom::GetShellVisibleSubscriptionState(string textualSubId)
0x12e25  stloc.1
0x12e26  ldloc.1
0x12e27  callvirt instance class System.Deployment.Application.SubscriptionStore System.Deployment.Application.SubscriptionState::get_SubscriptionStore()
0x12e2c  ldloc.1
0x12e2d  callvirt instance void System.Deployment.Application.SubscriptionStore::CheckForDeploymentUpdate(class System.Deployment.Application.SubscriptionState subState)
0x12e32  ldc.i4.1
0x12e33  stloc.0
0x12e34  leave.s  loc_12E68
0x12e36  stloc.2
0x12e37  ldstr    aUpdException// "Upd_Exception"
0x12e3c  call     string System.Deployment.Application.Resources::GetString(string s)
0x12e41  ldloc.2
0x12e42  call     void System.Deployment.Application.Logger::AddErrorInformation(string message, class [mscorlib]System.Exception exception)
0x12e47  leave.s  loc_12E68
0x12e49  ldloc.0
0x12e4a  brtrue.s loc_12E53
0x12e4c  ldstr    aUpdFailed// "Upd_Failed"
0x12e51  br.s     loc_12E58
0x12e53  ldstr    aUpdCompleted// "Upd_Completed"
0x12e58  call     string System.Deployment.Application.Resources::GetString(string s)
0x12e5d  call     void System.Deployment.Application.Logger::AddPhaseInformation(string message)
0x12e62  call     void System.Deployment.Application.Logger::EndCurrentThreadLogging()
0x12e67  endfinally
0x12e68  ret
```
