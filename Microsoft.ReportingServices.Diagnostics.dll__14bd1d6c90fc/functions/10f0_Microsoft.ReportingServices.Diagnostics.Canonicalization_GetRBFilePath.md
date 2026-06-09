# Microsoft.ReportingServices.Diagnostics.Canonicalization::GetRBFilePath

- ea: `0x10f0`
- end: `0x114d`
- name: `Microsoft.ReportingServices.Diagnostics.Canonicalization::GetRBFilePath`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xeb0`
- `0xf70`

## callees

- `0x10f0`

## pseudocode

```c

```

## disassembly

```asm
0x10f0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10f5  ldstr    a0123// "/{0}{1}/{2}{3}"
0x10fa  ldc.i4.4
0x10fb  newarr   [mscorlib]System.Object
0x1100  dup
0x1101  ldc.i4.0
0x1102  ldstr    aReportbuilder// "ReportBuilder"
0x1107  stelem.ref
0x1108  dup
0x1109  ldc.i4.1
0x110a  ldarg.1
0x110b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1110  brtrue.s loc_111F
0x1112  ldstr    asc_1254E// "/"
0x1117  ldarg.1
0x1118  call     string [mscorlib]System.String::Concat(string, string)
0x111d  br.s     loc_1124
0x111f  ldsfld   string [mscorlib]System.String::Empty
0x1124  stelem.ref
0x1125  dup
0x1126  ldc.i4.2
0x1127  ldarg.0
0x1128  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x112d  ldc.i4.s 0x2F
0x112f  callvirt instance string [mscorlib]System.String::Replace(char, char)
0x1134  stelem.ref
0x1135  dup
0x1136  ldc.i4.3
0x1137  ldarg.2
0x1138  brtrue.s loc_1141
0x113a  ldsfld   string [mscorlib]System.String::Empty
0x113f  br.s     loc_1146
0x1141  ldstr    aDeploy// ".deploy"
0x1146  stelem.ref
0x1147  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x114c  ret
```
