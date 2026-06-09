# Microsoft.ReportingServices.Library.ConnectionManager::Init

- ea: `0x3140`
- end: `0x3169`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::Init`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x3060`
- `0x3140`
- `0x32e0`
- `0x32f0`
- `0x3360`

## pseudocode

```c

```

## disassembly

```asm
0x3140  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::get_IsInitialized()
0x3145  brtrue.s loc_3168
0x3147  ldnull
0x3148  stloc.0
0x3149  newobj   instance void Microsoft.ReportingServices.Library.ConnectionManager::.ctor()
0x314e  stloc.0
0x314f  ldloc.0
0x3150  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x3155  ldloc.0
0x3156  ldc.i4.1
0x3157  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::VerifyConnection([opt] bool initializeEncryption)
0x315c  leave.s  loc_3168
0x315e  ldloc.0
0x315f  brfalse.s loc_3167
0x3161  ldloc.0
0x3162  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x3167  endfinally
0x3168  ret
```
