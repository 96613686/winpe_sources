# Microsoft.ReportingServices.Library.CachedSystemProperties::get_StoredParametersThreshold

- ea: `0x550`
- end: `0x5aa`
- name: `Microsoft.ReportingServices.Library.CachedSystemProperties::get_StoredParametersThreshold`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x130`
- `0x550`

## pseudocode

```c

```

## disassembly

```asm
0x550  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_storedParametersThreshold
0x555  brtrue.s loc_59F
0x557  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x55c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x561  ldstr    aStoredparamete// "StoredParametersThreshold"
0x566  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x56b  ldstr    aStoredparamete// "StoredParametersThreshold"
0x570  callvirt instance string Microsoft.ReportingServices.Library.CachedSystemProperties::GetParameter(string name)
0x575  ldsfld   int32 Microsoft.ReportingServices.Library.CachedSystemProperties::m_defaultStoredParametersThreshold
0x57a  ldstr    aCharacters// "characters"
0x57f  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace, string, string, int32, string)
0x584  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_storedParametersThreshold
0x589  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_storedParametersThreshold
0x58e  ldc.i4.1
0x58f  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ApplicationParameter::set_TraceSuccess(bool)
0x594  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_storedParametersThreshold
0x599  ldc.i4.1
0x59a  callvirt instance void class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x59f  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_storedParametersThreshold
0x5a4  callvirt instance var<u1> class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x5a9  ret
```
