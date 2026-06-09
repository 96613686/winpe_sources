# System.Deployment.Application.SubscriptionStore::CheckInstalled

- ea: `0x1fbb0`
- end: `0x1fbca`
- name: `System.Deployment.Application.SubscriptionStore::CheckInstalled`
- size: `26`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1f1c0`
- `0x1f680`
- `0x1f720`
- `0x1f7a0`
- `0x1fba0`

## callees

- `0x146f0`
- `0x1ed00`
- `0x1fbb0`
- `0x23020`

## string_xrefs

- `0x1fbb9`: `Ex_SubNotInstalled`

## pseudocode

```c

```

## disassembly

```asm
0x1fbb0  ldarg.0
0x1fbb1  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsInstalled()
0x1fbb6  brtrue.s loc_1FBC9
0x1fbb8  ldc.i4.8
0x1fbb9  ldstr    aExSubnotinstal// "Ex_SubNotInstalled"
0x1fbbe  call     string System.Deployment.Application.Resources::GetString(string s)
0x1fbc3  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x1fbc8  throw
0x1fbc9  ret
```
