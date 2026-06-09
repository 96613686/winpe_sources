# Microsoft.ReportingServices.Diagnostics.ScheduleDescription::OnceDescription

- ea: `0xbd80`
- end: `0xbdad`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleDescription::OnceDescription`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xf490`

## callees

- `0xbd80`
- `0xbf40`
- `0xc440`
- `0xc520`

## pseudocode

```c

```

## disassembly

```asm
0xbd80  ldarg.0
0xbd81  ldarg.1
0xbd82  ldarg.2
0xbd83  ldloca.s 0
0xbd85  ldloca.s 1
0xbd87  ldloca.s 2
0xbd89  call     instance void Microsoft.ReportingServices.Diagnostics.ScheduleDescription::GetBoundaryStrings(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, [out] string& startDateString, [out] string& startTimeString, [out] string& endDateString)
0xbd8e  ldloc.1
0xbd8f  ldloc.0
0xbd90  call     string Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::OnceScheduleDescription(string time, string date)
0xbd95  stloc.3
0xbd96  ldloc.2
0xbd97  brfalse.s loc_BDAB
0xbd99  ldloc.3
0xbd9a  ldstr    asc_1664A// " "
0xbd9f  ldloc.2
0xbda0  call     string Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::EndScheduleDescription(string date)
0xbda5  call     string [mscorlib]System.String::Concat(string, string, string)
0xbdaa  stloc.3
0xbdab  ldloc.3
0xbdac  ret
```
