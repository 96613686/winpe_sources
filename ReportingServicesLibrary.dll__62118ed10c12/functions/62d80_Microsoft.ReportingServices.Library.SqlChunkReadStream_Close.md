# Microsoft.ReportingServices.Library.SqlChunkReadStream::Close

- ea: `0x62d80`
- end: `0x62e29`
- name: `Microsoft.ReportingServices.Library.SqlChunkReadStream::Close`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x62d80`

## string_xrefs

- `0x62d9b`: `### ChunkReadStream.Close() - closing... id={0}, name='{1}'`
- `0x62e01`: `### ChunkReadStream - Closed! id={0}, name='{1}'`

## pseudocode

```c

```

## disassembly

```asm
0x62d80  ldarg.0
0x62d81  ldfld    bool Microsoft.ReportingServices.Library.SqlChunkReadStream::m_isOpen
0x62d86  brtrue.s loc_62D89
0x62d88  ret
0x62d89  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x62d8e  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x62d93  brfalse.s loc_62DC2
0x62d95  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x62d9a  ldc.i4.4
0x62d9b  ldstr    aChunkreadstrea_0// "### ChunkReadStream.Close() - closing.."...
0x62da0  ldc.i4.2
0x62da1  newarr   [mscorlib]System.Object
0x62da6  dup
0x62da7  ldc.i4.0
0x62da8  ldarg.0
0x62da9  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::m_snapshotDataID
0x62dae  box      [mscorlib]System.Guid
0x62db3  stelem.ref
0x62db4  dup
0x62db5  ldc.i4.1
0x62db6  ldarg.0
0x62db7  ldfld    string Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::m_chunkName
0x62dbc  stelem.ref
0x62dbd  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x62dc2  ldarg.0
0x62dc3  ldfld    bool Microsoft.ReportingServices.Library.SqlChunkReadStream::m_isConnectionOwner
0x62dc8  brtrue.s loc_62DD2
0x62dca  ldarg.0
0x62dcb  ldc.i4.0
0x62dcc  stfld    bool Microsoft.ReportingServices.Library.SqlChunkReadStream::m_isOpen
0x62dd1  ret
0x62dd2  ldarg.0
0x62dd3  ldfld    class Microsoft.ReportingServices.Library.ChunkStorage Microsoft.ReportingServices.Library.SqlChunkReadStream::m_storage
0x62dd8  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::Commit()
0x62ddd  ldarg.0
0x62dde  ldc.i4.0
0x62ddf  stfld    bool Microsoft.ReportingServices.Library.SqlChunkReadStream::m_isOpen
0x62de4  ldarg.0
0x62de5  ldfld    class Microsoft.ReportingServices.Library.ChunkStorage Microsoft.ReportingServices.Library.SqlChunkReadStream::m_storage
0x62dea  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::DisconnectStorage()
0x62def  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x62df4  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x62df9  brfalse.s loc_62E28
0x62dfb  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x62e00  ldc.i4.4
0x62e01  ldstr    aChunkreadstrea_1// "### ChunkReadStream - Closed! id={0}, n"...
0x62e06  ldc.i4.2
0x62e07  newarr   [mscorlib]System.Object
0x62e0c  dup
0x62e0d  ldc.i4.0
0x62e0e  ldarg.0
0x62e0f  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::m_snapshotDataID
0x62e14  box      [mscorlib]System.Guid
0x62e19  stelem.ref
0x62e1a  dup
0x62e1b  ldc.i4.1
0x62e1c  ldarg.0
0x62e1d  ldfld    string Microsoft.ReportingServices.Library.SnapshotChunkStreamBase::m_chunkName
0x62e22  stelem.ref
0x62e23  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x62e28  ret
```
