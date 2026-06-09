# Microsoft.BIServer.BIService.BIService::HandleServiceConfigUpdateFailure

- ea: `0xdf0`
- end: `0xe42`
- name: `Microsoft.BIServer.BIService.BIService::HandleServiceConfigUpdateFailure`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x3030`

## callees

- `0xd70`
- `0xdf0`

## string_xrefs

- `0xe1a`: `Failed to get latest service config, retrying in {0} seconds. Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0xdf0  ldarg.0
0xdf1  call     instance int32 Microsoft.BIServer.BIService.BIService::CalculateDelay()
0xdf6  stloc.0
0xdf7  ldloc.0
0xdf8  brtrue.s loc_E02
0xdfa  ldsfld   int32 Microsoft.BIServer.BIService.BIService::ReadConfigStartDelay
0xdff  stloc.0
0xe00  br.s     loc_E0E
0xe02  ldloc.0
0xe03  ldsfld   int32 Microsoft.BIServer.BIService.BIService::ReadConfigMaxDelay
0xe08  beq.s    loc_E0E
0xe0a  ldloc.0
0xe0b  ldc.i4.2
0xe0c  mul
0xe0d  stloc.0
0xe0e  ldsfld   int32 Microsoft.BIServer.BIService.BIService::ReadConfigAttemptCount
0xe13  ldc.i4.1
0xe14  add
0xe15  stsfld   int32 Microsoft.BIServer.BIService.BIService::ReadConfigAttemptCount
0xe1a  ldstr    aFailedToGetLat// "Failed to get latest service config, re"...
0xe1f  ldc.i4.2
0xe20  newarr   [mscorlib]System.Object
0xe25  dup
0xe26  ldc.i4.0
0xe27  ldloc.0
0xe28  box      [mscorlib]System.Int32
0xe2d  stelem.ref
0xe2e  dup
0xe2f  ldc.i4.1
0xe30  ldarg.1
0xe31  stelem.ref
0xe32  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0xe37  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xe3c  stsfld   valuetype [mscorlib]System.DateTime Microsoft.BIServer.BIService.BIService::ReadConfigLastTryTime
0xe41  ret
```
