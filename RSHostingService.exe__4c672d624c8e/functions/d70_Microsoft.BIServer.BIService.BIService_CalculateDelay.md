# Microsoft.BIServer.BIService.BIService::CalculateDelay

- ea: `0xd70`
- end: `0xd98`
- name: `Microsoft.BIServer.BIService.BIService::CalculateDelay`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xda0`
- `0xdf0`

## pseudocode

```c

```

## disassembly

```asm
0xd70  ldsfld   int32 Microsoft.BIServer.BIService.BIService::ReadConfigStartDelay
0xd75  ldc.r8   2.0
0xd7e  ldsfld   int32 Microsoft.BIServer.BIService.BIService::ReadConfigAttemptCount
0xd83  ldc.i4.1
0xd84  sub
0xd85  conv.r8
0xd86  call     float64 [mscorlib]System.Math::Pow(float64, float64)
0xd8b  conv.i4
0xd8c  mul
0xd8d  ldsfld   int32 Microsoft.BIServer.BIService.BIService::ReadConfigMaxDelay
0xd92  call     int32 [mscorlib]System.Math::Min(int32, int32)
0xd97  ret
```
