# Microsoft.ReportingServices.Library.CachedSystemProperties::get_ChunkSegmentSize

- ea: `0x7b0`
- end: `0x81f`
- name: `Microsoft.ReportingServices.Library.CachedSystemProperties::get_ChunkSegmentSize`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x130`
- `0x740`
- `0x7b0`

## pseudocode

```c

```

## disassembly

```asm
0x7b0  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_ChunkSegmentSizeParam
0x7b5  brtrue.s loc_814
0x7b7  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x7bc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x7c1  ldstr    aChunksegmentsi// "ChunkSegmentSize"
0x7c6  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x7cb  ldstr    aChunksegmentsi// "ChunkSegmentSize"
0x7d0  callvirt instance string Microsoft.ReportingServices.Library.CachedSystemProperties::GetParameter(string name)
0x7d5  call     int32 Microsoft.ReportingServices.Library.CachedSystemProperties::get_SqlStreamingBufferSize()
0x7da  ldc.i4.2
0x7db  div
0x7dc  ldstr    aBytes// "Bytes"
0x7e1  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace, string, string, int32, string)
0x7e6  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_ChunkSegmentSizeParam
0x7eb  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_ChunkSegmentSizeParam
0x7f0  ldc.i4   0x400
0x7f5  callvirt instance void class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x7fa  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_ChunkSegmentSizeParam
0x7ff  ldc.i4   0x6400000
0x804  callvirt instance void class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x809  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_ChunkSegmentSizeParam
0x80e  ldc.i4.1
0x80f  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ApplicationParameter::set_TraceSuccess(bool)
0x814  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_ChunkSegmentSizeParam
0x819  callvirt instance var<u1> class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x81e  ret
```
