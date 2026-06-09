# Microsoft.ReportingServices.Diagnostics.ScheduleDescription::MinutesDescription

- ea: `0xbdb0`
- end: `0xbde5`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleDescription::MinutesDescription`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xf490`

## callees

- `0xbdb0`
- `0xbf40`
- `0xc450`
- `0xc520`

## pseudocode

```c

```

## disassembly

```asm
0xbdb0  ldarg.0
0xbdb1  ldarg.1
0xbdb2  ldarg.2
0xbdb3  ldloca.s 0
0xbdb5  ldloca.s 1
0xbdb7  ldloca.s 2
0xbdb9  call     instance void Microsoft.ReportingServices.Diagnostics.ScheduleDescription::GetBoundaryStrings(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, [out] string& startDateString, [out] string& startTimeString, [out] string& endDateString)
0xbdbe  ldarg.3
0xbdbf  ldc.i4.s 0x3C
0xbdc1  div
0xbdc2  ldarg.3
0xbdc3  ldc.i4.s 0x3C
0xbdc5  rem
0xbdc6  ldloc.0
0xbdc7  ldloc.1
0xbdc8  call     string Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::MinutesScheduleDescription(int32 hours, int32 minutes, string date, string time)
0xbdcd  stloc.3
0xbdce  ldloc.2
0xbdcf  brfalse.s loc_BDE3
0xbdd1  ldloc.3
0xbdd2  ldstr    asc_1664A// " "
0xbdd7  ldloc.2
0xbdd8  call     string Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::EndScheduleDescription(string date)
0xbddd  call     string [mscorlib]System.String::Concat(string, string, string)
0xbde2  stloc.3
0xbde3  ldloc.3
0xbde4  ret
```
