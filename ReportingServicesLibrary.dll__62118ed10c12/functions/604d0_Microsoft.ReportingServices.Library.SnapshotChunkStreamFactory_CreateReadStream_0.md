# Microsoft.ReportingServices.Library.SnapshotChunkStreamFactory::CreateReadStream_0

- ea: `0x604d0`
- end: `0x6067e`
- name: `Microsoft.ReportingServices.Library.SnapshotChunkStreamFactory::CreateReadStream_0`
- size: `430`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x60490`
- `0x604b0`

## callees

- `0xf3d0`
- `0x604d0`
- `0x62b30`
- `0x62b80`
- `0x62ba0`
- `0x62bb0`
- `0x62c80`
- `0x62f80`
- `0x63660`
- `0x63ce0`
- `0x63cf0`
- `0x647c0`
- `0x64800`
- `0x68790`
- `0x69980`
- `0x6a1f0`
- `0x6a210`
- `0x6a240`
- `0x6a250`
- `0x6a290`

## string_xrefs

- `0x604e6`: `invalid updateMode when supportReadWrite=true`
- `0x604fc`: `invalid updateMode when supportReadWrite=false`

## pseudocode

```c

```

## disassembly

```asm
0x604d0  ldarg.s  6
0x604d2  brfalse.s loc_604F2
0x604d4  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x604d9  ldarg.s  7
0x604db  ldc.i4.1
0x604dc  beq.s    loc_604E5
0x604de  ldarg.s  7
0x604e0  ldc.i4.2
0x604e1  ceq
0x604e3  br.s     loc_604E6
0x604e5  ldc.i4.1
0x604e6  ldstr    aInvalidUpdatem// "invalid updateMode when supportReadWrit"...
0x604eb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x604f0  br.s     loc_60506
0x604f2  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x604f7  ldarg.s  7
0x604f9  ldc.i4.3
0x604fa  ceq
0x604fc  ldstr    aInvalidUpdatem_0// "invalid updateMode when supportReadWrit"...
0x60501  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x60506  ldarg.s  9
0x60508  ldnull
0x60509  stind.ref
0x6050a  ldnull
0x6050b  stloc.0
0x6050c  ldnull
0x6050d  stloc.1
0x6050e  ldnull
0x6050f  stloc.2
0x60510  ldnull
0x60511  stloc.3
0x60512  ldarg.s  5
0x60514  newobj   instance void Microsoft.ReportingServices.Library.ChunkConnectionManager::.ctor(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager connectionManager)
0x60519  stloc.3
0x6051a  ldloc.3
0x6051b  callvirt instance bool Microsoft.ReportingServices.Library.ChunkConnectionManager::get_IsConnectionOwner()
0x60520  brfalse.s loc_60538
0x60522  ldloc.3
0x60523  ldc.i4   0x10000
0x60528  callvirt instance void Microsoft.ReportingServices.Library.ChunkConnectionManager::set_IsolationLevel(valuetype [System.Data]System.Data.IsolationLevel value)
0x6052d  ldloc.3
0x6052e  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.ChunkConnectionManager::get_ConnectionManager()
0x60533  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x60538  ldloc.3
0x60539  callvirt instance class Microsoft.ReportingServices.Library.SegmentChunkDbInterface Microsoft.ReportingServices.Library.ChunkConnectionManager::get_DbInterface()
0x6053e  ldarg.0
0x6053f  ldarg.1
0x60540  ldarg.2
0x60541  ldarg.3
0x60542  callvirt instance bool Microsoft.ReportingServices.Library.SegmentChunkDbInterface::IsSegmentedChunk(valuetype [mscorlib]System.Guid snapshotId, bool isPermanent, string chunkName, int32 chunkType)
0x60547  brfalse.s loc_605A6
0x60549  ldarg.0
0x6054a  ldarg.1
0x6054b  ldarg.2
0x6054c  ldarg.3
0x6054d  ldloc.3
0x6054e  ldarg.s  7
0x60550  call     class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Library.SegmentedChunkStorage::Open(valuetype [mscorlib]System.Guid snapshotId, bool isPermanent, string chunkName, int32 chunkType, class Microsoft.ReportingServices.Library.ChunkConnectionManager connectionMananger, valuetype Microsoft.ReportingServices.Library.WriteOptions writeOptions)
0x60555  stloc.s  4
0x60557  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x6055c  ldloc.s  4
0x6055e  ldnull
0x6055f  cgt.un
0x60561  ldstr    aSegmentedchunk// "segmentedChunkStore"
0x60566  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6056b  ldloc.s  4
0x6056d  isinst   Microsoft.ReportingServices.Library.IHasMimeType
0x60572  stloc.s  5
0x60574  ldloc.s  5
0x60576  brfalse.s loc_60582
0x60578  ldarg.s  9
0x6057a  ldloc.s  5
0x6057c  callvirt instance string Microsoft.ReportingServices.Library.IHasMimeType::get_MimeType()
0x60581  stind.ref
0x60582  ldarg.s  6
0x60584  brtrue.s loc_60594
0x60586  ldloc.s  4
0x60588  call     int32 Microsoft.ReportingServices.Library.Global::get_SqlStreamingBufferSize()
0x6058d  call     class Microsoft.ReportingServices.Library.BufferedReadStream Microsoft.ReportingServices.Library.BufferedReadWriteStream::GetReadOnlyStream(class [mscorlib]System.IO.Stream store, int32 bufferSize)
0x60592  br.s     loc_605A0
0x60594  ldloc.s  4
0x60596  call     int32 Microsoft.ReportingServices.Library.Global::get_SqlStreamingBufferSize()
0x6059b  call     class Microsoft.ReportingServices.Library.BufferedReadWriteStream Microsoft.ReportingServices.Library.BufferedReadWriteStream::GetReadWriteStream(class [mscorlib]System.IO.Stream store, int32 bufferSize)
0x605a0  stloc.0
0x605a1  leave    loc_6067C
0x605a6  ldarg.0
0x605a7  ldarg.1
0x605a8  ldarg.2
0x605a9  ldarg.3
0x605aa  ldloc.3
0x605ab  ldarg.s  8
0x605ad  newobj   instance void Microsoft.ReportingServices.Library.SqlChunkReadStream::.ctor(valuetype [mscorlib]System.Guid snapshotDataID, bool isPermanentSnapshot, string chunkName, int32 chunkType, class Microsoft.ReportingServices.Library.ChunkConnectionManager connectionManager, bool isForUpgrade)
0x605b2  stloc.1
0x605b3  ldloc.1
0x605b4  callvirt instance bool Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::get_IsAvailable()
0x605b9  brfalse  loc_6064B
0x605be  ldloc.1
0x605bf  callvirt instance valuetype Microsoft.ReportingServices.Library.ChunkFlags Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::get_Flags()
0x605c4  ldc.i4.2
0x605c5  and
0x605c6  ldc.i4.2
0x605c7  bne.un.s loc_60618
0x605c9  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x605ce  ldarg.1
0x605cf  ldc.i4.0
0x605d0  ceq
0x605d2  ldstr    aPermanentChunk// "permanent chunk is stored in filesystem"
0x605d7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x605dc  ldarg.0
0x605dd  ldarg.1
0x605de  ldarg.2
0x605df  ldarg.3
0x605e0  newobj   instance void Microsoft.ReportingServices.Library.FileChunkReadStream::.ctor(valuetype [mscorlib]System.Guid snapshotDataID, bool isPermanentSnapshot, string chunkName, int32 chunkType)
0x605e5  stloc.2
0x605e6  ldloc.2
0x605e7  callvirt instance bool Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::get_IsAvailable()
0x605ec  brfalse.s loc_60618
0x605ee  ldloc.1
0x605ef  callvirt instance valuetype Microsoft.ReportingServices.Library.ChunkFlags Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::get_Flags()
0x605f4  ldc.i4.1
0x605f5  and
0x605f6  ldc.i4.1
0x605f7  bne.un.s loc_6060C
0x605f9  ldarg.s  4
0x605fb  brtrue.s loc_6060C
0x605fd  ldloc.2
0x605fe  ldloc.2
0x605ff  callvirt instance int16 Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::get_Version()
0x60604  newobj   instance void Microsoft.ReportingServices.Library.BufferedCompressedReadStream::.ctor(class [mscorlib]System.IO.Stream store, int16 version)
0x60609  stloc.0
0x6060a  br.s     loc_60618
0x6060c  ldloc.2
0x6060d  call     int32 Microsoft.ReportingServices.Library.Global::get_SqlStreamingBufferSize()
0x60612  newobj   instance void Microsoft.ReportingServices.Library.BufferedReadStream::.ctor(class [mscorlib]System.IO.Stream store, int32 bufferSize)
0x60617  stloc.0
0x60618  ldloc.0
0x60619  brtrue.s loc_6064B
0x6061b  ldloc.1
0x6061c  callvirt instance valuetype Microsoft.ReportingServices.Library.ChunkFlags Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::get_Flags()
0x60621  ldc.i4.1
0x60622  and
0x60623  ldc.i4.1
0x60624  bne.un.s loc_6062D
0x60626  ldarg.s  4
0x60628  ldc.i4.0
0x60629  ceq
0x6062b  br.s     loc_6062E
0x6062d  ldc.i4.0
0x6062e  brfalse.s loc_6063F
0x60630  ldloc.1
0x60631  ldloc.1
0x60632  callvirt instance int16 Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::get_Version()
0x60637  newobj   instance void Microsoft.ReportingServices.Library.BufferedCompressedReadStream::.ctor(class [mscorlib]System.IO.Stream store, int16 version)
0x6063c  stloc.0
0x6063d  br.s     loc_6064B
0x6063f  ldloc.1
0x60640  call     int32 Microsoft.ReportingServices.Library.Global::get_SqlStreamingBufferSize()
0x60645  newobj   instance void Microsoft.ReportingServices.Library.BufferedReadStream::.ctor(class [mscorlib]System.IO.Stream store, int32 bufferSize)
0x6064a  stloc.0
0x6064b  ldarg.s  9
0x6064d  ldloc.1
0x6064e  callvirt instance string Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::get_MimeType()
0x60653  stind.ref
0x60654  leave.s  loc_6067C
0x60656  ldloc.1
0x60657  brfalse.s loc_60662
0x60659  ldloc.2
0x6065a  brfalse.s loc_60662
0x6065c  ldloc.1
0x6065d  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x60662  ldloc.0
0x60663  brtrue.s loc_6067B
0x60665  ldloc.3
0x60666  brfalse.s loc_6067B
0x60668  ldloc.3
0x60669  callvirt instance bool Microsoft.ReportingServices.Library.ChunkConnectionManager::get_IsConnectionOwner()
0x6066e  brfalse.s loc_6067B
0x60670  ldloc.3
0x60671  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.ChunkConnectionManager::get_ConnectionManager()
0x60676  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x6067b  endfinally
0x6067c  ldloc.0
0x6067d  ret
```
