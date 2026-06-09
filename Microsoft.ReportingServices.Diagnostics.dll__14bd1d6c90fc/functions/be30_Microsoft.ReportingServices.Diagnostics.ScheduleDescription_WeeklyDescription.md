# Microsoft.ReportingServices.Diagnostics.ScheduleDescription::WeeklyDescription

- ea: `0xbe30`
- end: `0xbe7e`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleDescription::WeeklyDescription`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0xf490`

## callees

- `0xbe30`
- `0xbf40`
- `0xbfa0`
- `0xc4a0`
- `0xc4b0`
- `0xc520`

## pseudocode

```c

```

## disassembly

```asm
0xbe30  ldarg.0
0xbe31  ldarg.1
0xbe32  ldarg.2
0xbe33  ldloca.s 0
0xbe35  ldloca.s 1
0xbe37  ldloca.s 2
0xbe39  call     instance void Microsoft.ReportingServices.Diagnostics.ScheduleDescription::GetBoundaryStrings(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, [out] string& startDateString, [out] string& startTimeString, [out] string& endDateString)
0xbe3e  ldarg.0
0xbe3f  ldarg.3
0xbe40  call     instance string Microsoft.ReportingServices.Diagnostics.ScheduleDescription::DaysOfWeekString(unsigned int32 days)
0xbe45  stloc.3
0xbe46  ldarg.s  4
0xbe48  ldc.i4.1
0xbe49  conv.i8
0xbe4a  bne.un.s loc_BE58
0xbe4c  ldloc.1
0xbe4d  ldloc.3
0xbe4e  ldloc.0
0xbe4f  call     string Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::WeeklyScheduleDescription(string time, string days, string date)
0xbe54  stloc.s  4
0xbe56  br.s     loc_BE64
0xbe58  ldloc.1
0xbe59  ldloc.3
0xbe5a  ldarg.s  4
0xbe5c  ldloc.0
0xbe5d  call     string Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::WeeklyWithIntervalScheduleDescription(string time, string days, int64 interval, string date)
0xbe62  stloc.s  4
0xbe64  ldloc.2
0xbe65  brfalse.s loc_BE7B
0xbe67  ldloc.s  4
0xbe69  ldstr    asc_1664A// " "
0xbe6e  ldloc.2
0xbe6f  call     string Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::EndScheduleDescription(string date)
0xbe74  call     string [mscorlib]System.String::Concat(string, string, string)
0xbe79  stloc.s  4
0xbe7b  ldloc.s  4
0xbe7d  ret
```
