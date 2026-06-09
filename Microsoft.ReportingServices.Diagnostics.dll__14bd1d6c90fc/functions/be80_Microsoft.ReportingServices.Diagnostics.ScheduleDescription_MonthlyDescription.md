# Microsoft.ReportingServices.Diagnostics.ScheduleDescription::MonthlyDescription

- ea: `0xbe80`
- end: `0xbeca`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleDescription::MonthlyDescription`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0xf490`

## callees

- `0xbe80`
- `0xbf40`
- `0xc020`
- `0xc4d0`
- `0xc4e0`
- `0xc520`

## pseudocode

```c

```

## disassembly

```asm
0xbe80  ldarg.0
0xbe81  ldarg.1
0xbe82  ldarg.2
0xbe83  ldloca.s 0
0xbe85  ldloca.s 1
0xbe87  ldloca.s 2
0xbe89  call     instance void Microsoft.ReportingServices.Diagnostics.ScheduleDescription::GetBoundaryStrings(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, [out] string& startDateString, [out] string& startTimeString, [out] string& endDateString)
0xbe8e  ldarg.s  4
0xbe90  ldc.i4   0xFFF
0xbe95  bne.un.s loc_BEA2
0xbe97  ldloc.1
0xbe98  ldarg.3
0xbe99  ldloc.0
0xbe9a  call     string Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::MonthlyEveryMonthScheduleDescription(string time, string days, string date)
0xbe9f  stloc.3
0xbea0  br.s     loc_BEB3
0xbea2  ldloc.1
0xbea3  ldarg.3
0xbea4  ldarg.0
0xbea5  ldarg.s  4
0xbea7  call     instance string Microsoft.ReportingServices.Diagnostics.ScheduleDescription::MonthsOfYearString(unsigned int32 months)
0xbeac  ldloc.0
0xbead  call     string Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::MontlyScheduleDescription(string time, string days, string months, string date)
0xbeb2  stloc.3
0xbeb3  ldloc.2
0xbeb4  brfalse.s loc_BEC8
0xbeb6  ldloc.3
0xbeb7  ldstr    asc_1664A// " "
0xbebc  ldloc.2
0xbebd  call     string Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::EndScheduleDescription(string date)
0xbec2  call     string [mscorlib]System.String::Concat(string, string, string)
0xbec7  stloc.3
0xbec8  ldloc.3
0xbec9  ret
```
