# CompressedStorageLayer::Read

- ea: `0x8c730`
- end: `0x8c860`
- name: `CompressedStorageLayer::Read`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x69680`
- `0x8c730`

## string_xrefs

- `0x8c7d0`: `Decompressed segment {0}, original size = {1}, decompressed size = {2}`
- `0x8c80b`: `Expected read count not achieved`

## pseudocode

```c

```

## disassembly

```asm
0x8c730  ldarg.2
0x8c731  ldfld    class SegmentData ReadWriteParameters::Segment
0x8c736  stloc.0
0x8c737  ldloc.0
0x8c738  ldfld    int32 SegmentData::ActualSegmentLength
0x8c73d  newarr   [mscorlib]System.Byte
0x8c742  stloc.1
0x8c743  ldarg.1
0x8c744  ldarg.2
0x8c745  ldfld    valuetype [mscorlib]System.Guid ReadWriteParameters::ChunkId
0x8c74a  ldarg.2
0x8c74b  ldfld    bool ReadWriteParameters::IsPermanent
0x8c750  ldloc.0
0x8c751  ldfld    valuetype [mscorlib]System.Guid SegmentData::SegmentId
0x8c756  ldc.i4.0
0x8c757  ldloc.1
0x8c758  ldc.i4.0
0x8c759  ldloc.1
0x8c75a  ldlen
0x8c75b  conv.i4
0x8c75c  callvirt instance void Microsoft.ReportingServices.Library.SegmentChunkDbInterface::ReadChunkSegment(valuetype [mscorlib]System.Guid chunkId, bool isPermanent, valuetype [mscorlib]System.Guid segmentId, int32 dataIndex, unsigned int8[] buffer, int32 offset, int32 count)
0x8c761  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Timer::.ctor()
0x8c766  stloc.2
0x8c767  ldloc.2
0x8c768  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Timer::StartTimer()
0x8c76d  ldloc.1
0x8c76e  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x8c773  stloc.3
0x8c774  ldloc.3
0x8c775  ldc.i4.0
0x8c776  newobj   instance void [System]System.IO.Compression.GZipStream::.ctor(class [mscorlib]System.IO.Stream, valuetype [System]System.IO.Compression.CompressionMode)
0x8c77b  stloc.s  4
0x8c77d  ldarg.2
0x8c77e  ldfld    unsigned int8[] ReadWriteParameters::Buffer
0x8c783  ldarg.2
0x8c784  ldfld    int32 ReadWriteParameters::Offset
0x8c789  ldarg.2
0x8c78a  ldfld    int32 ReadWriteParameters::Length
0x8c78f  ldc.i4.1
0x8c790  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[], int32, int32, bool)
0x8c795  stloc.s  5
0x8c797  ldloc.3
0x8c798  ldc.i4.0
0x8c799  conv.i8
0x8c79a  ldc.i4.0
0x8c79b  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x8c7a0  pop
0x8c7a1  ldloc.0
0x8c7a2  ldfld    int32 SegmentData::LogicalSegmentLength
0x8c7a7  newarr   [mscorlib]System.Byte
0x8c7ac  stloc.s  6
0x8c7ae  ldloc.s  4
0x8c7b0  ldloc.s  6
0x8c7b2  ldc.i4.0
0x8c7b3  ldloc.s  6
0x8c7b5  ldlen
0x8c7b6  conv.i4
0x8c7b7  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x8c7bc  stloc.s  7
0x8c7be  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x8c7c3  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x8c7c8  brfalse.s loc_8C803
0x8c7ca  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x8c7cf  ldc.i4.4
0x8c7d0  ldstr    aDecompressedSe// "Decompressed segment {0}, original size"...
0x8c7d5  ldc.i4.3
0x8c7d6  newarr   [mscorlib]System.Object
0x8c7db  dup
0x8c7dc  ldc.i4.0
0x8c7dd  ldloc.0
0x8c7de  ldfld    valuetype [mscorlib]System.Guid SegmentData::SegmentId
0x8c7e3  box      [mscorlib]System.Guid
0x8c7e8  stelem.ref
0x8c7e9  dup
0x8c7ea  ldc.i4.1
0x8c7eb  ldloc.1
0x8c7ec  ldlen
0x8c7ed  conv.i4
0x8c7ee  box      [mscorlib]System.Int32
0x8c7f3  stelem.ref
0x8c7f4  dup
0x8c7f5  ldc.i4.2
0x8c7f6  ldloc.s  7
0x8c7f8  box      [mscorlib]System.Int32
0x8c7fd  stelem.ref
0x8c7fe  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x8c803  ldloc.s  7
0x8c805  ldloc.s  6
0x8c807  ldlen
0x8c808  conv.i4
0x8c809  beq.s    loc_8C816
0x8c80b  ldstr    aExpectedReadCo// "Expected read count not achieved"
0x8c810  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8c815  throw
0x8c816  ldloc.s  5
0x8c818  ldloc.s  6
0x8c81a  ldarg.2
0x8c81b  ldfld    int32 ReadWriteParameters::DataIndex
0x8c820  ldarg.2
0x8c821  ldfld    int32 ReadWriteParameters::Length
0x8c826  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x8c82b  leave.s  loc_8C84F
0x8c82d  ldloc.s  5
0x8c82f  brfalse.s loc_8C838
0x8c831  ldloc.s  5
0x8c833  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8c838  endfinally
0x8c839  ldloc.s  4
0x8c83b  brfalse.s loc_8C844
0x8c83d  ldloc.s  4
0x8c83f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8c844  endfinally
0x8c845  ldloc.3
0x8c846  brfalse.s loc_8C84E
0x8c848  ldloc.3
0x8c849  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8c84e  endfinally
0x8c84f  ldarg.3
0x8c850  ldflda   int64 ReadWriteStatistics::UncompressionTime
0x8c855  dup
0x8c856  ldind.i8
0x8c857  ldloc.2
0x8c858  callvirt instance int64 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Timer::ElapsedTimeMs()
0x8c85d  add
0x8c85e  stind.i8
0x8c85f  ret
```
