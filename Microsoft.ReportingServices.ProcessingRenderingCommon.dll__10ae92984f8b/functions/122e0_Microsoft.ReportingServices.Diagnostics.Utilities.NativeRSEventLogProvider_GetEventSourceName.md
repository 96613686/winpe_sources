# Microsoft.ReportingServices.Diagnostics.Utilities.NativeRSEventLogProvider::GetEventSourceName

- ea: `0x122e0`
- end: `0x12324`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.NativeRSEventLogProvider::GetEventSourceName`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x122e0`
- `0x12370`

## string_xrefs

- `0x12313`: `Report Server Windows Service ({0})`

## pseudocode

```c

```

## disassembly

```asm
0x122e0  ldnull
0x122e1  stloc.0
0x122e2  ldarg.1
0x122e3  switch   loc_12312, loc_12304, loc_122F6
0x122f4  br.s     loc_12320
0x122f6  ldarg.0
0x122f7  ldstr    aReportManager0// "Report Manager ({0})"
0x122fc  call     instance string Microsoft.ReportingServices.Diagnostics.Utilities.NativeRSEventLogProvider::AddInstanceToSourceName(string sourceFormat)
0x12301  stloc.0
0x12302  br.s     loc_12322
0x12304  ldarg.0
0x12305  ldstr    aReportServer0// "Report Server ({0})"
0x1230a  call     instance string Microsoft.ReportingServices.Diagnostics.Utilities.NativeRSEventLogProvider::AddInstanceToSourceName(string sourceFormat)
0x1230f  stloc.0
0x12310  br.s     loc_12322
0x12312  ldarg.0
0x12313  ldstr    aReportServerWi// "Report Server Windows Service ({0})"
0x12318  call     instance string Microsoft.ReportingServices.Diagnostics.Utilities.NativeRSEventLogProvider::AddInstanceToSourceName(string sourceFormat)
0x1231d  stloc.0
0x1231e  br.s     loc_12322
0x12320  ldnull
0x12321  stloc.0
0x12322  ldloc.0
0x12323  ret
```
