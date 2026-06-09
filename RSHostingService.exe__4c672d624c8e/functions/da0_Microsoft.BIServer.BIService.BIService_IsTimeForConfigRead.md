# Microsoft.BIServer.BIService.BIService::IsTimeForConfigRead

- ea: `0xda0`
- end: `0xdc6`
- name: `Microsoft.BIServer.BIService.BIService::IsTimeForConfigRead`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3030`

## callees

- `0xd70`

## pseudocode

```c

```

## disassembly

```asm
0xda0  ldarg.0
0xda1  call     instance int32 Microsoft.BIServer.BIService.BIService::CalculateDelay()
0xda6  stloc.0
0xda7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xdac  ldsfld   valuetype [mscorlib]System.DateTime Microsoft.BIServer.BIService.BIService::ReadConfigLastTryTime
0xdb1  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xdb6  stloc.1
0xdb7  ldloca.s 1
0xdb9  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0xdbe  ldloc.0
0xdbf  conv.r8
0xdc0  clt.un
0xdc2  ldc.i4.0
0xdc3  ceq
0xdc5  ret
```
