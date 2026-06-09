# Microsoft.ReportingServices.Diagnostics.ScheduleDescription::MonthsOfYearString

- ea: `0xc020`
- end: `0xc080`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleDescription::MonthsOfYearString`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xbe80`
- `0xbed0`

## callees

- `0xc020`
- `0x10bc0`

## pseudocode

```c

```

## disassembly

```asm
0xc020  ldstr    asc_126C2// ""
0xc025  stloc.0
0xc026  ldarg.0
0xc027  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Diagnostics.ScheduleDescription::m_culture
0xc02c  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xc031  callvirt instance string [mscorlib]System.Globalization.TextInfo::get_ListSeparator()
0xc036  stloc.1
0xc037  ldc.i4.1
0xc038  stloc.2
0xc039  br.s     loc_C069
0xc03b  ldarg.1
0xc03c  conv.u8
0xc03d  ldloc.2
0xc03e  conv.i8
0xc03f  and
0xc040  ldc.i4.0
0xc041  conv.i8
0xc042  ble.s    loc_C065
0xc044  ldloc.0
0xc045  ldstr    asc_1664A// " "
0xc04a  ldloc.2
0xc04b  stloc.3
0xc04c  ldloca.s 3
0xc04e  constrained. Microsoft.ReportingServices.Diagnostics.Months
0xc054  callvirt instance string [mscorlib]System.Object::ToString()
0xc059  call     string Keys::GetString(string key)
0xc05e  ldloc.1
0xc05f  call     string [mscorlib]System.String::Concat(string, string, string, string)
0xc064  stloc.0
0xc065  ldloc.2
0xc066  ldc.i4.2
0xc067  mul
0xc068  stloc.2
0xc069  ldloc.2
0xc06a  ldc.i4   0x800
0xc06f  ble.s    loc_C03B
0xc071  ldloc.0
0xc072  ldloc.1
0xc073  callvirt instance char[] [mscorlib]System.String::ToCharArray()
0xc078  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xc07d  stloc.0
0xc07e  ldloc.0
0xc07f  ret
```
