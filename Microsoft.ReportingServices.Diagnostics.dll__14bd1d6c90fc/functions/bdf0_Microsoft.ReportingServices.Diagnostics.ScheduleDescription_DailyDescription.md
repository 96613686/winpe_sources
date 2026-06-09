# Microsoft.ReportingServices.Diagnostics.ScheduleDescription::DailyDescription

- ea: `0xbdf0`
- end: `0xbe2d`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleDescription::DailyDescription`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xf490`

## callees

- `0xbdf0`
- `0xbf40`
- `0xc470`
- `0xc480`
- `0xc520`

## pseudocode

```c

```

## disassembly

```asm
0xbdf0  ldarg.0
0xbdf1  ldarg.1
0xbdf2  ldarg.2
0xbdf3  ldloca.s 0
0xbdf5  ldloca.s 1
0xbdf7  ldloca.s 2
0xbdf9  call     instance void Microsoft.ReportingServices.Diagnostics.ScheduleDescription::GetBoundaryStrings(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, [out] string& startDateString, [out] string& startTimeString, [out] string& endDateString)
0xbdfe  ldarg.3
0xbdff  ldc.i4.1
0xbe00  conv.i8
0xbe01  bne.un.s loc_BE0D
0xbe03  ldloc.1
0xbe04  ldloc.0
0xbe05  call     string Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::DailyScheduleDescription(string time, string date)
0xbe0a  stloc.3
0xbe0b  br.s     loc_BE16
0xbe0d  ldloc.1
0xbe0e  ldarg.3
0xbe0f  ldloc.0
0xbe10  call     string Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::DailyWithIntervalScheduleDescription(string time, int64 days, string date)
0xbe15  stloc.3
0xbe16  ldloc.2
0xbe17  brfalse.s loc_BE2B
0xbe19  ldloc.3
0xbe1a  ldstr    asc_1664A// " "
0xbe1f  ldloc.2
0xbe20  call     string Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::EndScheduleDescription(string date)
0xbe25  call     string [mscorlib]System.String::Concat(string, string, string)
0xbe2a  stloc.3
0xbe2b  ldloc.3
0xbe2c  ret
```
