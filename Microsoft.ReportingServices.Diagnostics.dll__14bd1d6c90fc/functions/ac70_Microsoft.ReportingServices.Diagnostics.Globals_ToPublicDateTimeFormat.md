# Microsoft.ReportingServices.Diagnostics.Globals::ToPublicDateTimeFormat

- ea: `0xac70`
- end: `0xac93`
- name: `Microsoft.ReportingServices.Diagnostics.Globals::ToPublicDateTimeFormat`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xe800`
- `0xe8d0`

## callees

- `0xac60`
- `0xac70`

## pseudocode

```c

```

## disassembly

```asm
0xac70  ldnull
0xac71  stloc.0
0xac72  ldarg.0
0xac73  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xac78  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xac7d  brfalse.s loc_AC91
0xac7f  ldarga.s 0
0xac81  call     string Microsoft.ReportingServices.Diagnostics.Globals::get_PublicDateTimeFormat()
0xac86  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xac8b  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0xac90  stloc.0
0xac91  ldloc.0
0xac92  ret
```
