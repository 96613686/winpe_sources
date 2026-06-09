# Microsoft.ReportingServices.Diagnostics.ScheduleDescription::DaysOfWeekString

- ea: `0xbfa0`
- end: `0xbffd`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleDescription::DaysOfWeekString`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xbe30`
- `0xbed0`

## callees

- `0xbfa0`
- `0x10bc0`

## pseudocode

```c

```

## disassembly

```asm
0xbfa0  ldstr    asc_126C2// ""
0xbfa5  stloc.0
0xbfa6  ldarg.0
0xbfa7  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Diagnostics.ScheduleDescription::m_culture
0xbfac  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xbfb1  callvirt instance string [mscorlib]System.Globalization.TextInfo::get_ListSeparator()
0xbfb6  stloc.1
0xbfb7  ldc.i4.1
0xbfb8  stloc.2
0xbfb9  br.s     loc_BFE9
0xbfbb  ldarg.1
0xbfbc  conv.u8
0xbfbd  ldloc.2
0xbfbe  conv.i8
0xbfbf  and
0xbfc0  ldc.i4.0
0xbfc1  conv.i8
0xbfc2  ble.s    loc_BFE5
0xbfc4  ldloc.0
0xbfc5  ldstr    asc_1664A// " "
0xbfca  ldloc.2
0xbfcb  stloc.3
0xbfcc  ldloca.s 3
0xbfce  constrained. Microsoft.ReportingServices.Diagnostics.DaysOfWeek
0xbfd4  callvirt instance string [mscorlib]System.Object::ToString()
0xbfd9  call     string Keys::GetString(string key)
0xbfde  ldloc.1
0xbfdf  call     string [mscorlib]System.String::Concat(string, string, string, string)
0xbfe4  stloc.0
0xbfe5  ldloc.2
0xbfe6  ldc.i4.2
0xbfe7  mul
0xbfe8  stloc.2
0xbfe9  ldloc.2
0xbfea  ldc.i4.s 0x40
0xbfec  ble.s    loc_BFBB
0xbfee  ldloc.0
0xbfef  ldloc.1
0xbff0  callvirt instance char[] [mscorlib]System.String::ToCharArray()
0xbff5  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xbffa  stloc.0
0xbffb  ldloc.0
0xbffc  ret
```
