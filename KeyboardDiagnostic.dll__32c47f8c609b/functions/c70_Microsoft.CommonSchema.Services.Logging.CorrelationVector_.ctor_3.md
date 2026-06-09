# Microsoft.CommonSchema.Services.Logging.CorrelationVector::.ctor_3

- ea: `0xc70`
- end: `0xc8c`
- name: `Microsoft.CommonSchema.Services.Logging.CorrelationVector::.ctor_3`
- size: `28`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xb60`
- `0xba0`
- `0xc60`

## pseudocode

```c

```

## disassembly

```asm
0xc70  ldarg.0
0xc71  call     instance void [mscorlib]System.Object::.ctor()
0xc76  ldarg.0
0xc77  ldarg.3
0xc78  stfld    valuetype CorrelationVectorVersion Microsoft.CommonSchema.Services.Logging.CorrelationVector::version
0xc7d  ldarg.0
0xc7e  ldarg.1
0xc7f  stfld    string Microsoft.CommonSchema.Services.Logging.CorrelationVector::correlationVectorBase
0xc84  ldarg.0
0xc85  ldarg.2
0xc86  stfld    int32 Microsoft.CommonSchema.Services.Logging.CorrelationVector::lastExtension
0xc8b  ret
```
