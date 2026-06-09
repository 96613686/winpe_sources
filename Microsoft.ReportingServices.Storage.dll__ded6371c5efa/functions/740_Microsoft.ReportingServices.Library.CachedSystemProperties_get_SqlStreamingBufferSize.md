# Microsoft.ReportingServices.Library.CachedSystemProperties::get_SqlStreamingBufferSize

- ea: `0x740`
- end: `0x7ad`
- name: `Microsoft.ReportingServices.Library.CachedSystemProperties::get_SqlStreamingBufferSize`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x7b0`

## callees

- `0x130`
- `0x740`

## pseudocode

```c

```

## disassembly

```asm
0x740  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SqlStreamingBufferSizeParam
0x745  brtrue.s loc_7A2
0x747  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x74c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x751  ldstr    aSqlstreamingbu// "SqlStreamingBufferSize"
0x756  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x75b  ldstr    aSqlstreamingbu// "SqlStreamingBufferSize"
0x760  callvirt instance string Microsoft.ReportingServices.Library.CachedSystemProperties::GetParameter(string name)
0x765  ldsfld   int32 Microsoft.ReportingServices.Library.CachedSystemProperties::m_DefaultSqlStreamingBufferSize
0x76a  ldstr    aBytes// "Bytes"
0x76f  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace, string, string, int32, string)
0x774  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SqlStreamingBufferSizeParam
0x779  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SqlStreamingBufferSizeParam
0x77e  ldc.i4   0x400
0x783  callvirt instance void class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x788  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SqlStreamingBufferSizeParam
0x78d  ldc.i4   0x6400000
0x792  callvirt instance void class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x797  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SqlStreamingBufferSizeParam
0x79c  ldc.i4.1
0x79d  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ApplicationParameter::set_TraceSuccess(bool)
0x7a2  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SqlStreamingBufferSizeParam
0x7a7  callvirt instance var<u1> class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x7ac  ret
```
