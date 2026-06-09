# Microsoft.ReportingServices.Diagnostics.Conversion::WriteUInt32

- ea: `0xf910`
- end: `0xf945`
- name: `Microsoft.ReportingServices.Diagnostics.Conversion::WriteUInt32`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0xf840`
- `0xf850`
- `0xf860`
- `0xf870`

## pseudocode

```c

```

## disassembly

```asm
0xf910  ldc.i4.4
0xf911  newarr   [mscorlib]System.Byte
0xf916  stloc.0
0xf917  ldloc.0
0xf918  ldc.i4.0
0xf919  ldarg.1
0xf91a  call     unsigned int8 Microsoft.ReportingServices.Diagnostics.Conversion::UInt32ToLowestByte(unsigned int32 toConvert)
0xf91f  stelem.i1
0xf920  ldloc.0
0xf921  ldc.i4.1
0xf922  ldarg.1
0xf923  call     unsigned int8 Microsoft.ReportingServices.Diagnostics.Conversion::UInt32ToLowerByte(unsigned int32 toConvert)
0xf928  stelem.i1
0xf929  ldloc.0
0xf92a  ldc.i4.2
0xf92b  ldarg.1
0xf92c  call     unsigned int8 Microsoft.ReportingServices.Diagnostics.Conversion::UInt32ToHigherByte(unsigned int32 toConvert)
0xf931  stelem.i1
0xf932  ldloc.0
0xf933  ldc.i4.3
0xf934  ldarg.1
0xf935  call     unsigned int8 Microsoft.ReportingServices.Diagnostics.Conversion::UInt32ToHighestByte(unsigned int32 toConvert)
0xf93a  stelem.i1
0xf93b  ldarg.0
0xf93c  ldloc.0
0xf93d  ldc.i4.0
0xf93e  ldc.i4.4
0xf93f  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0xf944  ret
```
