# Microsoft.ReportingServices.Library.CachedSystemProperties::get_SessionCookies

- ea: `0x610`
- end: `0x65f`
- name: `Microsoft.ReportingServices.Library.CachedSystemProperties::get_SessionCookies`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x130`
- `0x610`

## pseudocode

```c

```

## disassembly

```asm
0x610  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SessionCookiesParam
0x615  brtrue.s loc_654
0x617  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x61c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x621  ldstr    aUsesessioncook// "UseSessionCookies"
0x626  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x62b  ldstr    aUsesessioncook// "UseSessionCookies"
0x630  callvirt instance string Microsoft.ReportingServices.Library.CachedSystemProperties::GetParameter(string name)
0x635  ldsfld   bool Microsoft.ReportingServices.Library.CachedSystemProperties::m_DefaultSessionCookies
0x63a  ldstr    asc_A0B2// ""
0x63f  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace, string, string, bool, string)
0x644  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SessionCookiesParam
0x649  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SessionCookiesParam
0x64e  ldc.i4.1
0x64f  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ApplicationParameter::set_TraceSuccess(bool)
0x654  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SessionCookiesParam
0x659  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter::get_Value()
0x65e  ret
```
