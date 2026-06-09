# Microsoft.ReportingServices.Library.CachedSystemProperties::get_StoredParametersLifetime

- ea: `0x5b0`
- end: `0x60a`
- name: `Microsoft.ReportingServices.Library.CachedSystemProperties::get_StoredParametersLifetime`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x130`
- `0x5b0`

## pseudocode

```c

```

## disassembly

```asm
0x5b0  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_storedParametersLifetime
0x5b5  brtrue.s loc_5FF
0x5b7  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x5bc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x5c1  ldstr    aStoredparamete_0// "StoredParametersLifetime"
0x5c6  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x5cb  ldstr    aStoredparamete_0// "StoredParametersLifetime"
0x5d0  callvirt instance string Microsoft.ReportingServices.Library.CachedSystemProperties::GetParameter(string name)
0x5d5  ldsfld   int32 Microsoft.ReportingServices.Library.CachedSystemProperties::m_defaultStoredParametersLifetime
0x5da  ldstr    aDays// "days"
0x5df  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace, string, string, int32, string)
0x5e4  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_storedParametersLifetime
0x5e9  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_storedParametersLifetime
0x5ee  ldc.i4.1
0x5ef  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ApplicationParameter::set_TraceSuccess(bool)
0x5f4  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_storedParametersLifetime
0x5f9  ldc.i4.1
0x5fa  callvirt instance void class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x5ff  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_storedParametersLifetime
0x604  callvirt instance var<u1> class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x609  ret
```
