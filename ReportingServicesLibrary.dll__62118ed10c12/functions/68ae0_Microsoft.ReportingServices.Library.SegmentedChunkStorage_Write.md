# Microsoft.ReportingServices.Library.SegmentedChunkStorage::Write

- ea: `0x68ae0`
- end: `0x68c6a`
- name: `Microsoft.ReportingServices.Library.SegmentedChunkStorage::Write`
- size: `394`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0xf3f0`
- `0x68ae0`
- `0x68c90`
- `0x68cb0`
- `0x68cc0`
- `0x68e60`
- `0x68f00`
- `0x68f40`
- `0x69210`
- `0x6a070`

## string_xrefs

- `0x68aee`: `attempt to write after Close()`
- `0x68b01`: `Chunk was not opened with write access`
- `0x68b15`: `Attempt to write beyond end of stream`
- `0x68b93`: `bytesToWrite`

## pseudocode

```c

```

## disassembly

```asm
0x68ae0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x68ae5  ldarg.0
0x68ae6  ldfld    class Microsoft.ReportingServices.Library.SegmentChunkDbInterface Microsoft.ReportingServices.Library.SegmentedChunkStorage::m_storage
0x68aeb  ldnull
0x68aec  cgt.un
0x68aee  ldstr    aAttemptToWrite// "attempt to write after Close()"
0x68af3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x68af8  ldarg.0
0x68af9  ldfld    valuetype Microsoft.ReportingServices.Library.WriteOptions Microsoft.ReportingServices.Library.SegmentedChunkStorage::m_writeOptions
0x68afe  ldc.i4.3
0x68aff  bne.un.s loc_68B0C
0x68b01  ldstr    aChunkWasNotOpe// "Chunk was not opened with write access"
0x68b06  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x68b0b  throw
0x68b0c  ldarg.1
0x68b0d  ldarg.0
0x68b0e  call     instance int64 Microsoft.ReportingServices.Library.SegmentedChunkStorage::get_Length()
0x68b13  ble.s    loc_68B20
0x68b15  ldstr    aAttemptToWrite_0// "Attempt to write beyond end of stream"
0x68b1a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x68b1f  throw
0x68b20  ldc.i4.0
0x68b21  stloc.0
0x68b22  ldarg.s  4
0x68b24  stloc.1
0x68b25  ldarg.0
0x68b26  ldfld    bool Microsoft.ReportingServices.Library.SegmentedChunkStorage::m_versionOnWrite
0x68b2b  brfalse  loc_68C50
0x68b30  ldarg.0
0x68b31  call     instance void Microsoft.ReportingServices.Library.SegmentedChunkStorage::VersionChunk()
0x68b36  br       loc_68C50
0x68b3b  ldarg.0
0x68b3c  ldfld    class Microsoft.ReportingServices.Library.SegmentList Microsoft.ReportingServices.Library.SegmentedChunkStorage::m_segments
0x68b41  ldarg.1
0x68b42  ldloca.s 2
0x68b44  callvirt instance class SegmentData Microsoft.ReportingServices.Library.SegmentList::MapPositionToSegment(int64 absolutePosition, [out] int32& startingIndex)
0x68b49  stloc.3
0x68b4a  ldloc.3
0x68b4b  brfalse.s loc_68B5E
0x68b4d  ldloc.3
0x68b4e  ldfld    bool SegmentData::VersionOnWrite
0x68b53  brfalse.s loc_68B5E
0x68b55  ldarg.0
0x68b56  ldloc.3
0x68b57  call     instance void Microsoft.ReportingServices.Library.SegmentedChunkStorage::VersionSegment(class SegmentData segment)
0x68b5c  br.s     loc_68B74
0x68b5e  ldloc.3
0x68b5f  brtrue.s loc_68B74
0x68b61  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x68b66  ldloc.2
0x68b67  ldc.i4.0
0x68b68  ceq
0x68b6a  ldstr    aDataindex0// "dataIndex == 0"
0x68b6f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x68b74  ldarg.s  4
0x68b76  ldloc.0
0x68b77  sub
0x68b78  call     int32 Microsoft.ReportingServices.Library.Global::get_ChunkSegmentSize()
0x68b7d  ldloc.2
0x68b7e  sub
0x68b7f  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x68b84  stloc.s  4
0x68b86  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x68b8b  ldloc.s  4
0x68b8d  ldc.i4.0
0x68b8e  clt
0x68b90  ldc.i4.0
0x68b91  ceq
0x68b93  ldstr    aBytestowrite// "bytesToWrite"
0x68b98  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x68b9d  ldloc.0
0x68b9e  ldarg.3
0x68b9f  add
0x68ba0  stloc.s  5
0x68ba2  ldloca.s 6
0x68ba4  ldarg.2
0x68ba5  stfld    unsigned int8[] ReadWriteParameters::Buffer
0x68baa  ldloca.s 6
0x68bac  ldloc.s  5
0x68bae  stfld    int32 ReadWriteParameters::Offset
0x68bb3  ldloca.s 6
0x68bb5  ldloc.s  4
0x68bb7  stfld    int32 ReadWriteParameters::Length
0x68bbc  ldloca.s 6
0x68bbe  ldarg.0
0x68bbf  call     instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.SegmentedChunkStorage::get_Id()
0x68bc4  stfld    valuetype [mscorlib]System.Guid ReadWriteParameters::ChunkId
0x68bc9  ldloca.s 6
0x68bcb  ldarg.0
0x68bcc  call     instance bool Microsoft.ReportingServices.Library.SegmentedChunkStorage::get_IsPermanent()
0x68bd1  stfld    bool ReadWriteParameters::IsPermanent
0x68bd6  ldloca.s 6
0x68bd8  ldloc.3
0x68bd9  stfld    class SegmentData ReadWriteParameters::Segment
0x68bde  ldloca.s 6
0x68be0  ldloc.2
0x68be1  stfld    int32 ReadWriteParameters::DataIndex
0x68be6  ldloca.s 6
0x68be8  ldarg.1
0x68be9  stfld    int64 ReadWriteParameters::AbsolutePosition
0x68bee  ldloca.s 7
0x68bf0  initobj  ReadWriteStatistics
0x68bf6  ldloc.3
0x68bf7  brfalse.s loc_68C10
0x68bf9  ldarg.0
0x68bfa  ldfld    class Microsoft.ReportingServices.Library.SegmentStorageLayer Microsoft.ReportingServices.Library.SegmentedChunkStorage::m_storageLayer
0x68bff  ldarg.0
0x68c00  ldfld    class Microsoft.ReportingServices.Library.SegmentChunkDbInterface Microsoft.ReportingServices.Library.SegmentedChunkStorage::m_storage
0x68c05  ldloc.s  6
0x68c07  ldloca.s 7
0x68c09  callvirt instance void Microsoft.ReportingServices.Library.SegmentStorageLayer::Write(class Microsoft.ReportingServices.Library.SegmentChunkDbInterface storage, valuetype ReadWriteParameters parameters, valuetype ReadWriteStatistics& statistics)
0x68c0e  br.s     loc_68C1A
0x68c10  ldarg.0
0x68c11  ldloca.s 6
0x68c13  ldloca.s 7
0x68c15  call     instance void Microsoft.ReportingServices.Library.SegmentedChunkStorage::CreateSegmentInStorageLayer(valuetype ReadWriteParameters& wp, valuetype ReadWriteStatistics& stats)
0x68c1a  ldarg.0
0x68c1b  ldarg.0
0x68c1c  ldfld    int64 Microsoft.ReportingServices.Library.SegmentedChunkStorage::m_timeSpentCompression
0x68c21  ldloc.s  7
0x68c23  ldfld    int64 ReadWriteStatistics::CompressionTime
0x68c28  add
0x68c29  stfld    int64 Microsoft.ReportingServices.Library.SegmentedChunkStorage::m_timeSpentCompression
0x68c2e  ldarg.0
0x68c2f  ldarg.0
0x68c30  ldfld    int64 Microsoft.ReportingServices.Library.SegmentedChunkStorage::m_timeSpentUncompression
0x68c35  ldloc.s  7
0x68c37  ldfld    int64 ReadWriteStatistics::UncompressionTime
0x68c3c  add
0x68c3d  stfld    int64 Microsoft.ReportingServices.Library.SegmentedChunkStorage::m_timeSpentUncompression
0x68c42  ldc.i4.0
0x68c43  stloc.2
0x68c44  ldloc.0
0x68c45  ldloc.s  4
0x68c47  add
0x68c48  stloc.0
0x68c49  ldarg.1
0x68c4a  ldloc.s  4
0x68c4c  conv.i8
0x68c4d  add
0x68c4e  starg.s  1
0x68c50  ldloc.0
0x68c51  ldloc.1
0x68c52  blt      loc_68B3B
0x68c57  ldarg.0
0x68c58  ldarg.0
0x68c59  ldfld    int64 Microsoft.ReportingServices.Library.SegmentedChunkStorage::m_length
0x68c5e  ldarg.1
0x68c5f  call     int64 [mscorlib]System.Math::Max(int64, int64)
0x68c64  stfld    int64 Microsoft.ReportingServices.Library.SegmentedChunkStorage::m_length
0x68c69  ret
```
