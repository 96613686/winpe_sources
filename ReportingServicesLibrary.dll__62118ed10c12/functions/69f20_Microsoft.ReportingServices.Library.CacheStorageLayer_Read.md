# Microsoft.ReportingServices.Library.CacheStorageLayer::Read

- ea: `0x69f20`
- end: `0x6a037`
- name: `Microsoft.ReportingServices.Library.CacheStorageLayer::Read`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x69c60`
- `0x69d00`
- `0x69d20`
- `0x69f20`

## string_xrefs

- `0x69f51`: `Retrieved segment {0} for chunk {1} from the segment cache`
- `0x6a013`: `cachedBuffer`

## pseudocode

```c

```

## disassembly

```asm
0x69f20  ldarg.2
0x69f21  ldfld    class SegmentData ReadWriteParameters::Segment
0x69f26  ldfld    valuetype [mscorlib]System.Guid SegmentData::SegmentId
0x69f2b  stloc.0
0x69f2c  ldarg.0
0x69f2d  ldfld    class Microsoft.ReportingServices.Library.SegmentCache Microsoft.ReportingServices.Library.CacheStorageLayer::m_cache
0x69f32  ldloc.0
0x69f33  ldloca.s 1
0x69f35  callvirt instance bool Microsoft.ReportingServices.Library.SegmentCache::TryGetCache(valuetype [mscorlib]System.Guid segmentId, [out] unsigned int8[]& buffer)
0x69f3a  brfalse.s loc_69F7D
0x69f3c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x69f41  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x69f46  brfalse  loc_6A00A
0x69f4b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x69f50  ldc.i4.4
0x69f51  ldstr    aRetrievedSegme// "Retrieved segment {0} for chunk {1} fro"...
0x69f56  ldc.i4.2
0x69f57  newarr   [mscorlib]System.Object
0x69f5c  dup
0x69f5d  ldc.i4.0
0x69f5e  ldloc.0
0x69f5f  box      [mscorlib]System.Guid
0x69f64  stelem.ref
0x69f65  dup
0x69f66  ldc.i4.1
0x69f67  ldarg.2
0x69f68  ldfld    valuetype [mscorlib]System.Guid ReadWriteParameters::ChunkId
0x69f6d  box      [mscorlib]System.Guid
0x69f72  stelem.ref
0x69f73  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x69f78  br       loc_6A00A
0x69f7d  ldarg.2
0x69f7e  ldfld    class SegmentData ReadWriteParameters::Segment
0x69f83  ldfld    int32 SegmentData::LogicalSegmentLength
0x69f88  newarr   [mscorlib]System.Byte
0x69f8d  stloc.1
0x69f8e  ldloca.s 2
0x69f90  initobj  ReadWriteParameters
0x69f96  ldloca.s 2
0x69f98  ldarg.2
0x69f99  ldfld    int64 ReadWriteParameters::AbsolutePosition
0x69f9e  stfld    int64 ReadWriteParameters::AbsolutePosition
0x69fa3  ldloca.s 2
0x69fa5  ldloc.1
0x69fa6  stfld    unsigned int8[] ReadWriteParameters::Buffer
0x69fab  ldloca.s 2
0x69fad  ldarg.2
0x69fae  ldfld    valuetype [mscorlib]System.Guid ReadWriteParameters::ChunkId
0x69fb3  stfld    valuetype [mscorlib]System.Guid ReadWriteParameters::ChunkId
0x69fb8  ldloca.s 2
0x69fba  ldc.i4.0
0x69fbb  stfld    int32 ReadWriteParameters::DataIndex
0x69fc0  ldloca.s 2
0x69fc2  ldarg.2
0x69fc3  ldfld    bool ReadWriteParameters::IsPermanent
0x69fc8  stfld    bool ReadWriteParameters::IsPermanent
0x69fcd  ldloca.s 2
0x69fcf  ldarg.2
0x69fd0  ldfld    class SegmentData ReadWriteParameters::Segment
0x69fd5  ldfld    int32 SegmentData::LogicalSegmentLength
0x69fda  stfld    int32 ReadWriteParameters::Length
0x69fdf  ldloca.s 2
0x69fe1  ldc.i4.0
0x69fe2  stfld    int32 ReadWriteParameters::Offset
0x69fe7  ldloca.s 2
0x69fe9  ldarg.2
0x69fea  ldfld    class SegmentData ReadWriteParameters::Segment
0x69fef  stfld    class SegmentData ReadWriteParameters::Segment
0x69ff4  ldarg.0
0x69ff5  ldarg.1
0x69ff6  ldloc.2
0x69ff7  ldarg.3
0x69ff8  call     instance void Microsoft.ReportingServices.Library.CompositeStorageLayer::Read(class Microsoft.ReportingServices.Library.SegmentChunkDbInterface storage, valuetype ReadWriteParameters parameters, valuetype ReadWriteStatistics& statistics)
0x69ffd  ldarg.0
0x69ffe  ldfld    class Microsoft.ReportingServices.Library.SegmentCache Microsoft.ReportingServices.Library.CacheStorageLayer::m_cache
0x6a003  ldloc.0
0x6a004  ldloc.1
0x6a005  callvirt instance void Microsoft.ReportingServices.Library.SegmentCache::SetCache(valuetype [mscorlib]System.Guid segmentId, unsigned int8[] buffer)
0x6a00a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x6a00f  ldloc.1
0x6a010  ldnull
0x6a011  cgt.un
0x6a013  ldstr    aCachedbuffer// "cachedBuffer"
0x6a018  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6a01d  ldloc.1
0x6a01e  ldc.i4.0
0x6a01f  ldarg.2
0x6a020  ldfld    unsigned int8[] ReadWriteParameters::Buffer
0x6a025  ldarg.2
0x6a026  ldfld    int32 ReadWriteParameters::Offset
0x6a02b  ldarg.2
0x6a02c  ldfld    int32 ReadWriteParameters::Length
0x6a031  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x6a036  ret
```
