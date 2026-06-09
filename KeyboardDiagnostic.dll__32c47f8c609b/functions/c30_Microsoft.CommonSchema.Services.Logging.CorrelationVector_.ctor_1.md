# Microsoft.CommonSchema.Services.Logging.CorrelationVector::.ctor_1

- ea: `0xc30`
- end: `0xc5f`
- name: `Microsoft.CommonSchema.Services.Logging.CorrelationVector::.ctor_1`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xc30  ldarg.0
0xc31  call     instance void [mscorlib]System.Object::.ctor()
0xc36  ldarg.0
0xc37  ldc.i4.1
0xc38  stfld    valuetype CorrelationVectorVersion Microsoft.CommonSchema.Services.Logging.CorrelationVector::version
0xc3d  ldarg.0
0xc3e  ldc.i4.0
0xc3f  stfld    int32 Microsoft.CommonSchema.Services.Logging.CorrelationVector::lastExtension
0xc44  ldarg.0
0xc45  ldarga.s 1
0xc47  call     instance unsigned int8[] [mscorlib]System.Guid::ToByteArray()
0xc4c  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0xc51  ldc.i4.0
0xc52  ldc.i4.s 0x16
0xc54  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xc59  stfld    string Microsoft.CommonSchema.Services.Logging.CorrelationVector::correlationVectorBase
0xc5e  ret
```
