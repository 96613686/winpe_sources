# Microsoft.ReportingServices.Library.SqlChunkWriteStream::Read

- ea: `0x623e0`
- end: `0x62462`
- name: `Microsoft.ReportingServices.Library.SqlChunkWriteStream::Read`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x61b90`
- `0x623e0`
- `0x625f0`
- `0x62b50`

## string_xrefs

- `0x623e8`: `Stream is already closed and can't be accessed.`
- `0x62446`: `Can't read cunk portion from the database`

## pseudocode

```c

```

## disassembly

```asm
0x623e0  ldarg.0
0x623e1  ldfld    bool Microsoft.ReportingServices.Library.WriteSnapshotChunkStreamBase::m_isOpen
0x623e6  brtrue.s loc_623F3
0x623e8  ldstr    aStreamIsAlread// "Stream is already closed and can't be a"...
0x623ed  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x623f2  throw
0x623f3  ldarg.0
0x623f4  ldnull
0x623f5  ldc.i4.0
0x623f6  ldc.i4.0
0x623f7  call     instance bool Microsoft.ReportingServices.Library.SqlChunkWriteStream::EnsureChunkOpen(unsigned int8[] buffer, int32 offset, int32 count)
0x623fc  pop
0x623fd  ldarg.0
0x623fe  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x62403  ldarg.0
0x62404  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x62409  blt.s    loc_6240D
0x6240b  ldc.i4.0
0x6240c  ret
0x6240d  ldarg.0
0x6240e  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x62413  ldarg.0
0x62414  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x62419  sub
0x6241a  stloc.0
0x6241b  ldarg.3
0x6241c  conv.i8
0x6241d  ldloc.0
0x6241e  ble.s    loc_62424
0x62420  ldloc.0
0x62421  conv.i4
0x62422  starg.s  3
0x62424  ldarg.0
0x62425  ldfld    class Microsoft.ReportingServices.Library.ChunkStorage Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_storage
0x6242a  ldarg.0
0x6242b  ldfld    object Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_chunkPointer
0x62430  ldarg.0
0x62431  call     instance bool Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::get_IsPermanent()
0x62436  ldarg.0
0x62437  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x6243c  ldarg.1
0x6243d  ldarg.2
0x6243e  ldarg.3
0x6243f  callvirt instance bool Microsoft.ReportingServices.Library.ChunkStorage::ReadChunkPortion(object chunkPointer, bool isPermanentSnapshot, int64 dataIndex, unsigned int8[] buffer, int32 bufferIndex, int32 length)
0x62444  brtrue.s loc_62451
0x62446  ldstr    aCanTReadCunkPo// "Can't read cunk portion from the databa"...
0x6244b  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x62450  throw
0x62451  ldarg.0
0x62452  ldarg.0
0x62453  ldfld    int64 Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_position
0x62458  ldarg.3
0x62459  conv.i8
0x6245a  add
0x6245b  stfld    int64 Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_position
0x62460  ldarg.3
0x62461  ret
```
