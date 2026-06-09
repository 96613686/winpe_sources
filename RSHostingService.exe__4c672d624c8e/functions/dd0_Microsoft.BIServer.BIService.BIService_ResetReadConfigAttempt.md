# Microsoft.BIServer.BIService.BIService::ResetReadConfigAttempt

- ea: `0xdd0`
- end: `0xde1`
- name: `Microsoft.BIServer.BIService.BIService::ResetReadConfigAttempt`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3030`

## pseudocode

```c

```

## disassembly

```asm
0xdd0  ldc.i4.0
0xdd1  stsfld   int32 Microsoft.BIServer.BIService.BIService::ReadConfigAttemptCount
0xdd6  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xddb  stsfld   valuetype [mscorlib]System.DateTime Microsoft.BIServer.BIService.BIService::ReadConfigLastTryTime
0xde0  ret
```
