# Microsoft.ReportingServices.Diagnostics.ScheduleDescription::MonthlyDOWDescription

- ea: `0xbed0`
- end: `0xbf35`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleDescription::MonthlyDOWDescription`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0xf490`

## callees

- `0xbed0`
- `0xbf40`
- `0xbfa0`
- `0xc000`
- `0xc020`
- `0xc4f0`
- `0xc510`
- `0xc520`

## pseudocode

```c

```

## disassembly

```asm
0xbed0  ldarg.0
0xbed1  ldarg.1
0xbed2  ldarg.2
0xbed3  ldloca.s 0
0xbed5  ldloca.s 1
0xbed7  ldloca.s 2
0xbed9  call     instance void Microsoft.ReportingServices.Diagnostics.ScheduleDescription::GetBoundaryStrings(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, [out] string& startDateString, [out] string& startTimeString, [out] string& endDateString)
0xbede  ldarg.0
0xbedf  ldarg.3
0xbee0  call     instance string Microsoft.ReportingServices.Diagnostics.ScheduleDescription::DaysOfWeekString(unsigned int32 days)
0xbee5  stloc.3
0xbee6  ldarg.0
0xbee7  ldarg.s  4
0xbee9  call     instance string Microsoft.ReportingServices.Diagnostics.ScheduleDescription::WeeksString(valuetype Microsoft.ReportingServices.Diagnostics.WeeksOfMonth weeksOfMonth)
0xbeee  stloc.s  4
0xbef0  ldarg.s  5
0xbef2  ldc.i4   0xFFF
0xbef7  bne.un.s loc_BF07
0xbef9  ldloc.1
0xbefa  ldloc.s  4
0xbefc  ldloc.3
0xbefd  ldloc.0
0xbefe  call     string Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::MonthlyDOWEveryMonthScheduleDescription(string time, string week, string days, string date)
0xbf03  stloc.s  5
0xbf05  br.s     loc_BF1B
0xbf07  ldloc.1
0xbf08  ldloc.s  4
0xbf0a  ldloc.3
0xbf0b  ldarg.0
0xbf0c  ldarg.s  5
0xbf0e  call     instance string Microsoft.ReportingServices.Diagnostics.ScheduleDescription::MonthsOfYearString(unsigned int32 months)
0xbf13  ldloc.0
0xbf14  call     string Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::MontlyDOWScheduleDescription(string time, string week, string days, string months, string date)
0xbf19  stloc.s  5
0xbf1b  ldloc.2
0xbf1c  brfalse.s loc_BF32
0xbf1e  ldloc.s  5
0xbf20  ldstr    asc_1664A// " "
0xbf25  ldloc.2
0xbf26  call     string Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::EndScheduleDescription(string date)
0xbf2b  call     string [mscorlib]System.String::Concat(string, string, string)
0xbf30  stloc.s  5
0xbf32  ldloc.s  5
0xbf34  ret
```
