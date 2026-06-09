# Microsoft.ReportingServices.Diagnostics.Utilities.TraceEventProvider::NotifyModelRetrieval

- ea: `0x12140`
- end: `0x12216`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.TraceEventProvider::NotifyModelRetrieval`
- size: `214`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12145`: `Caller: {0}, IsOnPrem: {1}, IsMD: {2}, DataSourceName: {3}, DbName: {4}, UserName: {5}, IsConnectionFromPool: {6}, Model size: {7}, ModelCacheHit: {8}, StringCacheHit: {9}, HasError: {10}, Error: {11}, Total time: {12}ms, Resolution time: {13}ms, Connection open time: {14}ms, Retrieval time: {15}ms, Parsing time: {16}ms, Puid: {17}, CloudCacheHit: {18}, ModelId: {19}`

## pseudocode

```c

```

## disassembly

```asm
0x12140  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12145  ldstr    aCaller0Isonpre// "Caller: {0}, IsOnPrem: {1}, IsMD: {2}, "...
0x1214a  ldc.i4.s 0x14
0x1214c  newarr   [mscorlib]System.Object
0x12151  dup
0x12152  ldc.i4.0
0x12153  ldarg.1
0x12154  stelem.ref
0x12155  dup
0x12156  ldc.i4.1
0x12157  ldarg.2
0x12158  box      [mscorlib]System.Boolean
0x1215d  stelem.ref
0x1215e  dup
0x1215f  ldc.i4.2
0x12160  ldarg.3
0x12161  box      [mscorlib]System.Boolean
0x12166  stelem.ref
0x12167  dup
0x12168  ldc.i4.3
0x12169  ldarg.s  4
0x1216b  stelem.ref
0x1216c  dup
0x1216d  ldc.i4.4
0x1216e  ldarg.s  5
0x12170  stelem.ref
0x12171  dup
0x12172  ldc.i4.5
0x12173  ldarg.s  6
0x12175  stelem.ref
0x12176  dup
0x12177  ldc.i4.6
0x12178  ldarg.s  7
0x1217a  box      Microsoft.ReportingServices.Diagnostics.Internal.NullableBool
0x1217f  stelem.ref
0x12180  dup
0x12181  ldc.i4.7
0x12182  ldarg.s  8
0x12184  box      [mscorlib]System.Int32
0x12189  stelem.ref
0x1218a  dup
0x1218b  ldc.i4.8
0x1218c  ldarg.s  9
0x1218e  box      Microsoft.ReportingServices.Diagnostics.Internal.NullableBool
0x12193  stelem.ref
0x12194  dup
0x12195  ldc.i4.s 9
0x12197  ldarg.s  0xA
0x12199  box      Microsoft.ReportingServices.Diagnostics.Internal.NullableBool
0x1219e  stelem.ref
0x1219f  dup
0x121a0  ldc.i4.s 0xA
0x121a2  ldarg.s  0xB
0x121a4  box      [mscorlib]System.Boolean
0x121a9  stelem.ref
0x121aa  dup
0x121ab  ldc.i4.s 0xB
0x121ad  ldarg.s  0xC
0x121af  stelem.ref
0x121b0  dup
0x121b1  ldc.i4.s 0xC
0x121b3  ldarg.s  0xD
0x121b5  box      [mscorlib]System.Int64
0x121ba  stelem.ref
0x121bb  dup
0x121bc  ldc.i4.s 0xD
0x121be  ldarg.s  0xE
0x121c0  box      [mscorlib]System.Int64
0x121c5  stelem.ref
0x121c6  dup
0x121c7  ldc.i4.s 0xE
0x121c9  ldarg.s  0xF
0x121cb  box      [mscorlib]System.Int64
0x121d0  stelem.ref
0x121d1  dup
0x121d2  ldc.i4.s 0xF
0x121d4  ldarg.s  0x10
0x121d6  box      [mscorlib]System.Int64
0x121db  stelem.ref
0x121dc  dup
0x121dd  ldc.i4.s 0x10
0x121df  ldarg.s  0x11
0x121e1  box      [mscorlib]System.Int64
0x121e6  stelem.ref
0x121e7  dup
0x121e8  ldc.i4.s 0x11
0x121ea  ldarg.s  0x12
0x121ec  stelem.ref
0x121ed  dup
0x121ee  ldc.i4.s 0x12
0x121f0  ldarg.s  0x13
0x121f2  box      Microsoft.ReportingServices.Diagnostics.Internal.NullableBool
0x121f7  stelem.ref
0x121f8  dup
0x121f9  ldc.i4.s 0x13
0x121fb  ldarg.s  0x14
0x121fd  box      [mscorlib]System.Int64
0x12202  stelem.ref
0x12203  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12208  stloc.0
0x12209  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x1220e  ldc.i4.3
0x1220f  ldloc.0
0x12210  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x12215  ret
```
