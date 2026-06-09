# Microsoft.ReportingServices.Diagnostics.ScheduleDescription::GetBoundaryStrings

- ea: `0xbf40`
- end: `0xbf91`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleDescription::GetBoundaryStrings`
- size: `81`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbd80`
- `0xbdb0`
- `0xbdf0`
- `0xbe30`
- `0xbe80`
- `0xbed0`

## callees

- `0xbf40`

## pseudocode

```c

```

## disassembly

```asm
0xbf40  ldarg.s  4
0xbf42  ldarga.s 1
0xbf44  ldstr    aT// "t"
0xbf49  ldarg.0
0xbf4a  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Diagnostics.ScheduleDescription::m_culture
0xbf4f  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0xbf54  stind.ref
0xbf55  ldarg.3
0xbf56  ldarga.s 1
0xbf58  ldstr    aD// "d"
0xbf5d  ldarg.0
0xbf5e  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Diagnostics.ScheduleDescription::m_culture
0xbf63  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0xbf68  stind.ref
0xbf69  ldarg.2
0xbf6a  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xbf6f  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xbf74  brfalse.s loc_BF8C
0xbf76  ldarg.s  5
0xbf78  ldarga.s 2
0xbf7a  ldstr    aD// "d"
0xbf7f  ldarg.0
0xbf80  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Diagnostics.ScheduleDescription::m_culture
0xbf85  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0xbf8a  stind.ref
0xbf8b  ret
0xbf8c  ldarg.s  5
0xbf8e  ldnull
0xbf8f  stind.ref
0xbf90  ret
```
