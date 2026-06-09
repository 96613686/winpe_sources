# Microsoft.ReportingServices.Library.SqlChunkWriteStream::Close

- ea: `0x62290`
- end: `0x623ca`
- name: `Microsoft.ReportingServices.Library.SqlChunkWriteStream::Close`
- size: `314`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x61a80`
- `0x62290`
- `0x62480`
- `0x62b50`

## string_xrefs

- `0x622a2`: `### ChunkWriteStream.Close() - closing... , id={0}, name='{1}'`
- `0x6230c`: `### ChunkWriteStream.Close() - truncating from length {0} to length {1}..., id={1}, name='{2}'`
- `0x623a2`: `### ChunkWriteStream - Closed! id={0}, name='{1}'`

## pseudocode

```c

```

## disassembly

```asm
0x62290  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x62295  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x6229a  brfalse.s loc_622C9
0x6229c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x622a1  ldc.i4.4
0x622a2  ldstr    aChunkwritestre// "### ChunkWriteStream.Close() - closing."...
0x622a7  ldc.i4.2
0x622a8  newarr   [mscorlib]System.Object
0x622ad  dup
0x622ae  ldc.i4.0
0x622af  ldarg.0
0x622b0  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::m_snapshotDataID
0x622b5  box      [mscorlib]System.Guid
0x622ba  stelem.ref
0x622bb  dup
0x622bc  ldc.i4.1
0x622bd  ldarg.0
0x622be  ldfld    string Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::m_chunkName
0x622c3  stelem.ref
0x622c4  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x622c9  ldarg.0
0x622ca  ldfld    bool Microsoft.ReportingServices.Library.WriteSnapshotChunkStreamBase::m_isOpen
0x622cf  brtrue.s loc_622D2
0x622d1  ret
0x622d2  ldarg.0
0x622d3  call     instance void [mscorlib]System.IO.Stream::Close()
0x622d8  ldarg.0
0x622d9  call     instance bool Microsoft.ReportingServices.Library.SqlChunkWriteStream::get_IsConnectionOwner()
0x622de  brtrue.s loc_622E1
0x622e0  ret
0x622e1  ldarg.0
0x622e2  ldfld    class Microsoft.ReportingServices.Library.ChunkStorage Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_storage
0x622e7  brfalse  loc_62390
0x622ec  ldarg.0
0x622ed  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x622f2  ldarg.0
0x622f3  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x622f8  ble.s    loc_6236C
0x622fa  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x622ff  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x62304  brfalse.s loc_6234F
0x62306  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x6230b  ldc.i4.4
0x6230c  ldstr    aChunkwritestre_0// "### ChunkWriteStream.Close() - truncati"...
0x62311  ldc.i4.4
0x62312  newarr   [mscorlib]System.Object
0x62317  dup
0x62318  ldc.i4.0
0x62319  ldarg.0
0x6231a  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x6231f  box      [mscorlib]System.Int64
0x62324  stelem.ref
0x62325  dup
0x62326  ldc.i4.1
0x62327  ldarg.0
0x62328  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x6232d  box      [mscorlib]System.Int64
0x62332  stelem.ref
0x62333  dup
0x62334  ldc.i4.2
0x62335  ldarg.0
0x62336  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::m_snapshotDataID
0x6233b  box      [mscorlib]System.Guid
0x62340  stelem.ref
0x62341  dup
0x62342  ldc.i4.3
0x62343  ldarg.0
0x62344  ldfld    string Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::m_chunkName
0x62349  stelem.ref
0x6234a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x6234f  ldarg.0
0x62350  ldfld    class Microsoft.ReportingServices.Library.ChunkStorage Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_storage
0x62355  ldarg.0
0x62356  ldfld    object Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_chunkPointer
0x6235b  ldarg.0
0x6235c  call     instance bool Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::get_IsPermanent()
0x62361  ldarg.0
0x62362  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x62367  callvirt instance void Microsoft.ReportingServices.Library.ChunkStorage::TruncateChunk(object chunkPointer, bool isPermanentSnapshot, int64 length)
0x6236c  ldarg.0
0x6236d  ldfld    class Microsoft.ReportingServices.Library.ChunkStorage Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_storage
0x62372  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::Commit()
0x62377  ldarg.0
0x62378  ldc.i4.0
0x62379  stfld    bool Microsoft.ReportingServices.Library.WriteSnapshotChunkStreamBase::m_isOpen
0x6237e  ldarg.0
0x6237f  ldfld    class Microsoft.ReportingServices.Library.ChunkStorage Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_storage
0x62384  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::DisconnectStorage()
0x62389  ldarg.0
0x6238a  ldnull
0x6238b  stfld    class Microsoft.ReportingServices.Library.ChunkStorage Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_storage
0x62390  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x62395  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x6239a  brfalse.s loc_623C9
0x6239c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x623a1  ldc.i4.4
0x623a2  ldstr    aChunkwritestre_1// "### ChunkWriteStream - Closed! id={0}, "...
0x623a7  ldc.i4.2
0x623a8  newarr   [mscorlib]System.Object
0x623ad  dup
0x623ae  ldc.i4.0
0x623af  ldarg.0
0x623b0  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::m_snapshotDataID
0x623b5  box      [mscorlib]System.Guid
0x623ba  stelem.ref
0x623bb  dup
0x623bc  ldc.i4.1
0x623bd  ldarg.0
0x623be  ldfld    string Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::m_chunkName
0x623c3  stelem.ref
0x623c4  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x623c9  ret
```
