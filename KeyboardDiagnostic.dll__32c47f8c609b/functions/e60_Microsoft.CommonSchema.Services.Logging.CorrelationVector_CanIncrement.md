# Microsoft.CommonSchema.Services.Logging.CorrelationVector::CanIncrement

- ea: `0xe60`
- end: `0xee5`
- name: `Microsoft.CommonSchema.Services.Logging.CorrelationVector::CanIncrement`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xcb0`

## callees

- `0xe60`

## pseudocode

```c

```

## disassembly

```asm
0xe60  ldarg.0
0xe61  ldfld    int32 Microsoft.CommonSchema.Services.Logging.CorrelationVector::lastExtension
0xe66  ldc.i4.1
0xe67  add
0xe68  stloc.0
0xe69  ldarg.0
0xe6a  ldfld    string Microsoft.CommonSchema.Services.Logging.CorrelationVector::correlationVectorBase
0xe6f  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe74  conv.r8
0xe75  ldloc.0
0xe76  conv.r8
0xe77  call     float64 [mscorlib]System.Math::Log10(float64)
0xe7c  ldc.r8   1.0
0xe85  add
0xe86  call     float64 [mscorlib]System.Math::Floor(float64)
0xe8b  add
0xe8c  ldc.r8   1.0
0xe95  add
0xe96  ldarg.0
0xe97  ldfld    valuetype CorrelationVectorVersion Microsoft.CommonSchema.Services.Logging.CorrelationVector::version
0xe9c  brtrue.s loc_EA3
0xe9e  ldc.i4.s 0x3F
0xea0  stloc.1
0xea1  br.s     loc_ED1
0xea3  ldc.i4.1
0xea4  ldarg.0
0xea5  ldfld    valuetype CorrelationVectorVersion Microsoft.CommonSchema.Services.Logging.CorrelationVector::version
0xeaa  bne.un.s loc_EB1
0xeac  ldc.i4.s 0x7F
0xeae  stloc.1
0xeaf  br.s     loc_ED1
0xeb1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xeb6  ldstr    aUnsupportedCor// "Unsupported correlation vector version:"...
0xebb  ldarg.0
0xebc  ldfld    valuetype CorrelationVectorVersion Microsoft.CommonSchema.Services.Logging.CorrelationVector::version
0xec1  box      CorrelationVectorVersion
0xec6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xecb  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xed0  throw
0xed1  ldloc.1
0xed2  conv.r8
0xed3  ble.s    loc_EE3
0xed5  ldarg.0
0xed6  ldfld    int32 Microsoft.CommonSchema.Services.Logging.CorrelationVector::lastExtension
0xedb  ldc.i4   0x7FFFFFFF
0xee0  cgt
0xee2  ret
0xee3  ldc.i4.1
0xee4  ret
```
