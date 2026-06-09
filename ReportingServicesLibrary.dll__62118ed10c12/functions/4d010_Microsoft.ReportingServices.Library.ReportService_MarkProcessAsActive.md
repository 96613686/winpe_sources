# Microsoft.ReportingServices.Library.ReportService::MarkProcessAsActive

- ea: `0x4d010`
- end: `0x4d05d`
- name: `Microsoft.ReportingServices.Library.ReportService::MarkProcessAsActive`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x4d010`
- `0x4f900`

## string_xrefs

- `0x4d022`: `ReportService::MarkProcessAsActive - Mark the WindowsService (worker) AppDomain as active.`
- `0x4d052`: `ReportService::MarkProcessAsActive - m_serviceController is null; Cannot mark the WindowsService (worker) AppDomain as active.`

## pseudocode

```c

```

## disassembly

```asm
0x4d010  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4d015  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4d01a  brfalse.s loc_4D02C
0x4d01c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4d021  ldc.i4.3
0x4d022  ldstr    aReportserviceM// "ReportService::MarkProcessAsActive - Ma"...
0x4d027  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4d02c  ldarg.0
0x4d02d  ldfld    class Microsoft.ReportingServices.Library.ServiceAppDomainController Microsoft.ReportingServices.Library.ReportService::m_serviceController
0x4d032  brfalse.s loc_4D040
0x4d034  ldarg.0
0x4d035  ldfld    class Microsoft.ReportingServices.Library.ServiceAppDomainController Microsoft.ReportingServices.Library.ReportService::m_serviceController
0x4d03a  callvirt instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::MarkProcessAsActive()
0x4d03f  ret
0x4d040  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4d045  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4d04a  brfalse.s loc_4D05C
0x4d04c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4d051  ldc.i4.3
0x4d052  ldstr    aReportserviceM_0// "ReportService::MarkProcessAsActive - m_"...
0x4d057  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4d05c  ret
```
