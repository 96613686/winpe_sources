# Microsoft.CommonSchema.Services.Logging.CorrelationVector::ValidateCorrelationVector

- ea: `0xd20`
- end: `0xd58`
- name: `Microsoft.CommonSchema.Services.Logging.CorrelationVector::ValidateCorrelationVector`
- size: `56`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xb60`
- `0xba0`

## callees

- `0xd20`
- `0xd60`

## pseudocode

```c

```

## disassembly

```asm
0xd20  ldarg.1
0xd21  brtrue.s loc_D2E
0xd23  ldarg.0
0xd24  ldc.i4.s 0x3F
0xd26  ldc.i4.s 0x10
0xd28  call     void Microsoft.CommonSchema.Services.Logging.CorrelationVector::ValidateCorrelationVector(string correlationVector, unsigned int8 maxVectorLength, unsigned int8 baseLength)
0xd2d  ret
0xd2e  ldc.i4.1
0xd2f  ldarg.1
0xd30  bne.un.s loc_D3D
0xd32  ldarg.0
0xd33  ldc.i4.s 0x7F
0xd35  ldc.i4.s 0x16
0xd37  call     void Microsoft.CommonSchema.Services.Logging.CorrelationVector::ValidateCorrelationVector(string correlationVector, unsigned int8 maxVectorLength, unsigned int8 baseLength)
0xd3c  ret
0xd3d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xd42  ldstr    aUnsupportedCor// "Unsupported correlation vector version:"...
0xd47  ldarg.1
0xd48  box      CorrelationVectorVersion
0xd4d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xd52  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xd57  throw
```
