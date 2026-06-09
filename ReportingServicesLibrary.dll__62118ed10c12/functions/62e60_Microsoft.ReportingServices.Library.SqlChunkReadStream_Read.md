# Microsoft.ReportingServices.Library.SqlChunkReadStream::Read

- ea: `0x62e60`
- end: `0x62ed8`
- name: `Microsoft.ReportingServices.Library.SqlChunkReadStream::Read`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x61b90`
- `0x62e60`

## string_xrefs

- `0x62e68`: `Stream is already closed and can't be accessed.`
- `0x62ebc`: `Can't read cunk portion from the database`

## pseudocode

```c

```

## disassembly

```asm
0x62e60  ldarg.0
0x62e61  ldfld    bool Microsoft.ReportingServices.Library.SqlChunkReadStream::m_isOpen
0x62e66  brtrue.s loc_62E73
0x62e68  ldstr    aStreamIsAlread// "Stream is already closed and can't be a"...
0x62e6d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x62e72  throw
0x62e73  ldarg.0
0x62e74  ldfld    int64 Microsoft.ReportingServices.Library.SqlChunkReadStream::m_position
0x62e79  ldarg.0
0x62e7a  ldfld    int64 Microsoft.ReportingServices.Library.SqlChunkReadStream::m_chunkLength
0x62e7f  blt.s    loc_62E83
0x62e81  ldc.i4.0
0x62e82  ret
0x62e83  ldarg.0
0x62e84  ldfld    int64 Microsoft.ReportingServices.Library.SqlChunkReadStream::m_chunkLength
0x62e89  ldarg.0
0x62e8a  ldfld    int64 Microsoft.ReportingServices.Library.SqlChunkReadStream::m_position
0x62e8f  sub
0x62e90  stloc.0
0x62e91  ldarg.3
0x62e92  conv.i8
0x62e93  ldloc.0
0x62e94  ble.s    loc_62E9A
0x62e96  ldloc.0
0x62e97  conv.i4
0x62e98  starg.s  3
0x62e9a  ldarg.0
0x62e9b  ldfld    class Microsoft.ReportingServices.Library.ChunkStorage Microsoft.ReportingServices.Library.SqlChunkReadStream::m_storage
0x62ea0  ldarg.0
0x62ea1  ldfld    object Microsoft.ReportingServices.Library.SqlChunkReadStream::m_chunkPointer
0x62ea6  ldarg.0
0x62ea7  ldfld    bool Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::m_isPermanentSnapshot
0x62eac  ldarg.0
0x62ead  ldfld    int64 Microsoft.ReportingServices.Library.SqlChunkReadStream::m_position
0x62eb2  ldarg.1
0x62eb3  ldarg.2
0x62eb4  ldarg.3
0x62eb5  callvirt instance bool Microsoft.ReportingServices.Library.ChunkStorage::ReadChunkPortion(object chunkPointer, bool isPermanentSnapshot, int64 dataIndex, unsigned int8[] buffer, int32 bufferIndex, int32 length)
0x62eba  brtrue.s loc_62EC7
0x62ebc  ldstr    aCanTReadCunkPo// "Can't read cunk portion from the databa"...
0x62ec1  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x62ec6  throw
0x62ec7  ldarg.0
0x62ec8  ldarg.0
0x62ec9  ldfld    int64 Microsoft.ReportingServices.Library.SqlChunkReadStream::m_position
0x62ece  ldarg.3
0x62ecf  conv.i8
0x62ed0  add
0x62ed1  stfld    int64 Microsoft.ReportingServices.Library.SqlChunkReadStream::m_position
0x62ed6  ldarg.3
0x62ed7  ret
```
