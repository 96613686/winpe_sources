# Microsoft.ReportingServices.Library.CachedSystemProperties::get_EnableIntegratedSecurity

- ea: `0x4b0`
- end: `0x4fb`
- name: `Microsoft.ReportingServices.Library.CachedSystemProperties::get_EnableIntegratedSecurity`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x130`
- `0x4b0`

## string_xrefs

- `0x4c1`: `EnableIntegratedSecurity`
- `0x4cb`: `EnableIntegratedSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x4b0  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_EnableIntegratedSecurityParam
0x4b5  brtrue.s loc_4F0
0x4b7  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x4bc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x4c1  ldstr    aEnableintegrat// "EnableIntegratedSecurity"
0x4c6  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x4cb  ldstr    aEnableintegrat// "EnableIntegratedSecurity"
0x4d0  callvirt instance string Microsoft.ReportingServices.Library.CachedSystemProperties::GetParameter(string name)
0x4d5  ldc.i4.1
0x4d6  ldstr    asc_A0B2// ""
0x4db  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace, string, string, bool, string)
0x4e0  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_EnableIntegratedSecurityParam
0x4e5  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_EnableIntegratedSecurityParam
0x4ea  ldc.i4.1
0x4eb  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ApplicationParameter::set_TraceSuccess(bool)
0x4f0  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_EnableIntegratedSecurityParam
0x4f5  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter::get_Value()
0x4fa  ret
```
