# Microsoft.ReportingServices.Library.CachedSystemProperties::get_SessionAccessTimeout

- ea: `0x280`
- end: `0x2db`
- name: `Microsoft.ReportingServices.Library.CachedSystemProperties::get_SessionAccessTimeout`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3d20`

## callees

- `0x130`
- `0x280`

## string_xrefs

- `0x291`: `SessionAccessTimeout`
- `0x29b`: `SessionAccessTimeout`

## pseudocode

```c

```

## disassembly

```asm
0x280  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SessionAccessTimeoutParam
0x285  brtrue.s loc_2D0
0x287  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x28c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x291  ldstr    aSessionaccesst// "SessionAccessTimeout"
0x296  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x29b  ldstr    aSessionaccesst// "SessionAccessTimeout"
0x2a0  callvirt instance string Microsoft.ReportingServices.Library.CachedSystemProperties::GetParameter(string name)
0x2a5  ldc.i4   0x258
0x2aa  ldstr    aSeconds// "seconds"
0x2af  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace, string, string, int32, string)
0x2b4  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SessionAccessTimeoutParam
0x2b9  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SessionAccessTimeoutParam
0x2be  ldc.i4.1
0x2bf  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ApplicationParameter::set_TraceSuccess(bool)
0x2c4  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SessionAccessTimeoutParam
0x2c9  ldc.i4.s 0xA
0x2cb  callvirt instance void class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x2d0  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SessionAccessTimeoutParam
0x2d5  callvirt instance var<u1> class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x2da  ret
```
