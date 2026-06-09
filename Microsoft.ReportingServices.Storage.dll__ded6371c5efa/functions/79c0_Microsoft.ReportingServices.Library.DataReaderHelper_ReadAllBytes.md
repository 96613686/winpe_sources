# Microsoft.ReportingServices.Library.DataReaderHelper::ReadAllBytes

- ea: `0x79c0`
- end: `0x7a32`
- name: `Microsoft.ReportingServices.Library.DataReaderHelper::ReadAllBytes`
- size: `114`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2ca0`
- `0x2d40`

## callees

- `0x79c0`

## string_xrefs

- `0x7a22`: `totalBytesRead`

## pseudocode

```c

```

## disassembly

```asm
0x79c0  ldarg.0
0x79c1  ldarg.1
0x79c2  ldc.i4.0
0x79c3  conv.i8
0x79c4  ldnull
0x79c5  ldc.i4.0
0x79c6  ldc.i4.0
0x79c7  callvirt instance int64 [System.Data]System.Data.IDataRecord::GetBytes(int32, int64, unsigned int8[], int32, int32)
0x79cc  stloc.0
0x79cd  ldloc.0
0x79ce  ldc.i4   0x7FFFFFFF
0x79d3  conv.i8
0x79d4  ble.s    loc_79F2
0x79d6  ldstr    aByteCountExcee// "Byte count exceeds Int32.MaxValue: "
0x79db  ldloca.s 0
0x79dd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x79e2  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x79e7  call     string [mscorlib]System.String::Concat(string, string)
0x79ec  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x79f1  throw
0x79f2  ldc.i4.0
0x79f3  conv.i8
0x79f4  stloc.1
0x79f5  ldc.i4.0
0x79f6  conv.i8
0x79f7  stloc.2
0x79f8  ldloc.0
0x79f9  conv.ovf.i
0x79fa  newarr   [mscorlib]System.Byte
0x79ff  stloc.3
0x7a00  br.s     loc_7A2C
0x7a02  ldarg.0
0x7a03  ldarg.1
0x7a04  ldloc.1
0x7a05  ldloc.3
0x7a06  ldloc.1
0x7a07  conv.i4
0x7a08  ldloc.0
0x7a09  ldloc.1
0x7a0a  sub
0x7a0b  conv.i4
0x7a0c  callvirt instance int64 [System.Data]System.Data.IDataRecord::GetBytes(int32, int64, unsigned int8[], int32, int32)
0x7a11  stloc.2
0x7a12  ldloc.1
0x7a13  ldloc.2
0x7a14  add
0x7a15  stloc.1
0x7a16  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x7a1b  ldloc.1
0x7a1c  ldloc.0
0x7a1d  cgt
0x7a1f  ldc.i4.0
0x7a20  ceq
0x7a22  ldstr    aTotalbytesread// "totalBytesRead"
0x7a27  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x7a2c  ldloc.1
0x7a2d  ldloc.0
0x7a2e  bne.un.s loc_7A02
0x7a30  ldloc.3
0x7a31  ret
```
