# Microsoft.CommonSchema.Services.Logging.CorrelationVector::.ctor_0

- ea: `0xc00`
- end: `0xc21`
- name: `Microsoft.CommonSchema.Services.Logging.CorrelationVector::.ctor_0`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbf0`

## callees

- `0xe00`

## pseudocode

```c

```

## disassembly

```asm
0xc00  ldarg.0
0xc01  call     instance void [mscorlib]System.Object::.ctor()
0xc06  ldarg.0
0xc07  ldarg.1
0xc08  stfld    valuetype CorrelationVectorVersion Microsoft.CommonSchema.Services.Logging.CorrelationVector::version
0xc0d  ldarg.0
0xc0e  ldc.i4.0
0xc0f  stfld    int32 Microsoft.CommonSchema.Services.Logging.CorrelationVector::lastExtension
0xc14  ldarg.0
0xc15  ldarg.0
0xc16  call     instance string Microsoft.CommonSchema.Services.Logging.CorrelationVector::GetUniqueValue()
0xc1b  stfld    string Microsoft.CommonSchema.Services.Logging.CorrelationVector::correlationVectorBase
0xc20  ret
```
