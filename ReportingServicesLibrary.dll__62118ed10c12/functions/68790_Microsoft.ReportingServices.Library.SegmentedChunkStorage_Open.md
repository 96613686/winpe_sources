# Microsoft.ReportingServices.Library.SegmentedChunkStorage::Open

- ea: `0x68790`
- end: `0x6882f`
- name: `Microsoft.ReportingServices.Library.SegmentedChunkStorage::Open`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x604d0`

## callees

- `0x684d0`
- `0x68790`
- `0x68900`

## string_xrefs

- `0x687a2`: `Open Segmented Chunk ({0}, {1}, {2}, '{3}', {4})`
- `0x687df`: `Invalid writeOptions: WriteOptions.Create`

## pseudocode

```c

```

## disassembly

```asm
0x68790  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x68795  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x6879a  brfalse.s loc_687DB
0x6879c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x687a1  ldc.i4.4
0x687a2  ldstr    aOpenSegmentedC// "Open Segmented Chunk ({0}, {1}, {2}, '{"...
0x687a7  ldc.i4.5
0x687a8  newarr   [mscorlib]System.Object
0x687ad  dup
0x687ae  ldc.i4.0
0x687af  ldarg.0
0x687b0  box      [mscorlib]System.Guid
0x687b5  stelem.ref
0x687b6  dup
0x687b7  ldc.i4.1
0x687b8  ldarg.1
0x687b9  box      [mscorlib]System.Boolean
0x687be  stelem.ref
0x687bf  dup
0x687c0  ldc.i4.2
0x687c1  ldarg.2
0x687c2  stelem.ref
0x687c3  dup
0x687c4  ldc.i4.3
0x687c5  ldarg.3
0x687c6  box      [mscorlib]System.Int32
0x687cb  stelem.ref
0x687cc  dup
0x687cd  ldc.i4.4
0x687ce  ldarg.s  5
0x687d0  box      Microsoft.ReportingServices.Library.WriteOptions
0x687d5  stelem.ref
0x687d6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x687db  ldarg.s  5
0x687dd  brtrue.s loc_687EA
0x687df  ldstr    aInvalidWriteop// "Invalid writeOptions: WriteOptions.Crea"...
0x687e4  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x687e9  throw
0x687ea  ldarg.0
0x687eb  ldarg.1
0x687ec  ldarg.2
0x687ed  ldarg.3
0x687ee  ldarg.s  4
0x687f0  ldarg.s  5
0x687f2  newobj   instance void Microsoft.ReportingServices.Library.SegmentedChunkStorage::.ctor(valuetype [mscorlib]System.Guid snapshotId, bool isPermanent, string chunkName, int32 chunkType, class Microsoft.ReportingServices.Library.ChunkConnectionManager connectionManager, valuetype Microsoft.ReportingServices.Library.WriteOptions writeOptions)
0x687f7  stloc.0
0x687f8  ldloc.0
0x687f9  ldfld    bool Microsoft.ReportingServices.Library.SegmentedChunkStorage::m_isAvailable
0x687fe  brfalse.s loc_68807
0x68800  ldloc.0
0x68801  newobj   instance void Microsoft.ReportingServices.Library.StorageStream::.ctor(class Microsoft.ReportingServices.Library.IStorage store)
0x68806  ret
0x68807  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x6880c  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x68811  brfalse.s loc_6882D
0x68813  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x68818  ldc.i4.4
0x68819  ldstr    aSegmentedChunk// "Segmented Chunk '{0}' was not found."
0x6881e  ldc.i4.1
0x6881f  newarr   [mscorlib]System.Object
0x68824  dup
0x68825  ldc.i4.0
0x68826  ldarg.2
0x68827  stelem.ref
0x68828  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x6882d  ldnull
0x6882e  ret
```
