# Microsoft.CommonSchema.Services.Logging.CorrelationVector::GetUniqueValue

- ea: `0xe00`
- end: `0xe58`
- name: `Microsoft.CommonSchema.Services.Logging.CorrelationVector::GetUniqueValue`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xc00`

## callees

- `0xe00`

## pseudocode

```c

```

## disassembly

```asm
0xe00  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xe05  stloc.1
0xe06  ldloca.s 1
0xe08  call     instance unsigned int8[] [mscorlib]System.Guid::ToByteArray()
0xe0d  stloc.0
0xe0e  ldarg.0
0xe0f  ldfld    valuetype CorrelationVectorVersion Microsoft.CommonSchema.Services.Logging.CorrelationVector::version
0xe14  brtrue.s loc_E20
0xe16  ldloc.0
0xe17  ldc.i4.0
0xe18  ldc.i4.s 0xC
0xe1a  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[], int32, int32)
0xe1f  ret
0xe20  ldc.i4.1
0xe21  ldarg.0
0xe22  ldfld    valuetype CorrelationVectorVersion Microsoft.CommonSchema.Services.Logging.CorrelationVector::version
0xe27  bne.un.s loc_E38
0xe29  ldloc.0
0xe2a  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0xe2f  ldc.i4.0
0xe30  ldc.i4.s 0x16
0xe32  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xe37  ret
0xe38  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xe3d  ldstr    aUnsupportedCor// "Unsupported correlation vector version:"...
0xe42  ldarg.0
0xe43  ldfld    valuetype CorrelationVectorVersion Microsoft.CommonSchema.Services.Logging.CorrelationVector::version
0xe48  box      CorrelationVectorVersion
0xe4d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xe52  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xe57  throw
```
