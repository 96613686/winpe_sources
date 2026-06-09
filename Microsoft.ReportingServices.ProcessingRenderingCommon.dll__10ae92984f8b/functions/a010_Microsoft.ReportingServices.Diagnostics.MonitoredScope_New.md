# Microsoft.ReportingServices.Diagnostics.MonitoredScope::New

- ea: `0xa010`
- end: `0xa03b`
- name: `Microsoft.ReportingServices.Diagnostics.MonitoredScope::New`
- size: `43`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xa040`
- `0xa060`
- `0xa080`
- `0xa0b0`

## callees

- `0x9f80`
- `0x9ff0`
- `0xa010`
- `0xa120`

## pseudocode

```c

```

## disassembly

```asm
0xa010  call     bool Microsoft.ReportingServices.Diagnostics.MonitoredScope::get_TraceMonitoredScope()
0xa015  brtrue.s loc_A01D
0xa017  ldsfld   class Microsoft.ReportingServices.Diagnostics.MonitoredScope Microsoft.ReportingServices.Diagnostics.MonitoredScope::dummyInstance
0xa01c  ret
0xa01d  ldsfld   class Microsoft.ReportingServices.Diagnostics.MonitoredScope Microsoft.ReportingServices.Diagnostics.MonitoredScope::instance
0xa022  stloc.0
0xa023  ldloc.0
0xa024  brtrue.s loc_A032
0xa026  newobj   instance void Microsoft.ReportingServices.Diagnostics.MonitoredScope::.ctor()
0xa02b  stloc.0
0xa02c  ldloc.0
0xa02d  stsfld   class Microsoft.ReportingServices.Diagnostics.MonitoredScope Microsoft.ReportingServices.Diagnostics.MonitoredScope::instance
0xa032  ldloc.0
0xa033  ldarg.0
0xa034  callvirt instance void Microsoft.ReportingServices.Diagnostics.MonitoredScope::Start(string name)
0xa039  ldloc.0
0xa03a  ret
```
