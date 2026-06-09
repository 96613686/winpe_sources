# Microsoft.ReportingServices.Library.SqlChunkWriteStream::EnsureChunkOpen

- ea: `0x625f0`
- end: `0x626d2`
- name: `Microsoft.ReportingServices.Library.SqlChunkWriteStream::EnsureChunkOpen`
- size: `226`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x62160`
- `0x623e0`
- `0x62490`

## callees

- `0x625f0`
- `0x631f0`
- `0x63220`
- `0x63230`

## string_xrefs

- `0x62616`: `VersionMismatchException when opening chunk for write`
- `0x6262b`: `access`
- `0x6265d`: `Failed to open up chunk for update.`

## pseudocode

```c

```

## disassembly

```asm
0x625f0  ldc.i4.0
0x625f1  stloc.0
0x625f2  ldarg.0
0x625f3  ldfld    bool Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_isChunkOpened
0x625f8  brtrue   loc_626B8
0x625fd  ldnull
0x625fe  stloc.1
0x625ff  ldarg.0
0x62600  ldarg.0
0x62601  ldfld    class Microsoft.ReportingServices.Library.ChunkConnectionManager Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_connectionManager
0x62606  ldc.i4.0
0x62607  newobj   instance void Microsoft.ReportingServices.Library.SqlChunkAccess::.ctor(class Microsoft.ReportingServices.Library.SnapshotChunkStreamBase chunk, class Microsoft.ReportingServices.Library.ChunkConnectionManager connectionManager, bool isForUpgrade)
0x6260c  stloc.1
0x6260d  leave.s  loc_62622
0x6260f  pop
0x62610  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x62615  ldc.i4.0
0x62616  ldstr    aVersionmismatc// "VersionMismatchException when opening c"...
0x6261b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x62620  rethrow
0x62622  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x62627  ldloc.1
0x62628  ldnull
0x62629  cgt.un
0x6262b  ldstr    aAccess// "access"
0x62630  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x62635  ldarg.0
0x62636  ldfld    bool Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_forUpdate
0x6263b  brfalse.s loc_62672
0x6263d  ldloc.1
0x6263e  ldarg.0
0x6263f  ldflda   object Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_chunkPointer
0x62644  ldarg.0
0x62645  ldflda   int64 Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_length
0x6264a  ldloca.s 2
0x6264c  ldloca.s 3
0x6264e  ldloca.s 4
0x62650  ldarg.0
0x62651  ldflda   class Microsoft.ReportingServices.Library.ChunkStorage Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_storage
0x62656  callvirt instance bool Microsoft.ReportingServices.Library.SqlChunkAccess::OpenExistingChunk([out] object& chunkPointer, [out] int64& chunkLength, [out] string& mimeType, [out] valuetype Microsoft.ReportingServices.Library.ChunkFlags& chunkFlags, [out] int16& version, [out] class Microsoft.ReportingServices.Library.ChunkStorage& storage)
0x6265b  brtrue.s loc_62668
0x6265d  ldstr    aFailedToOpenUp// "Failed to open up chunk for update."
0x62662  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x62667  throw
0x62668  ldarg.0
0x62669  ldc.i4.0
0x6266a  conv.i8
0x6266b  stfld    int64 Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_position
0x62670  br.s     loc_626B1
0x62672  ldarg.1
0x62673  brtrue.s loc_62683
0x62675  ldc.i4.0
0x62676  newarr   [mscorlib]System.Byte
0x6267b  starg.s  1
0x6267d  ldc.i4.0
0x6267e  starg.s  2
0x62680  ldc.i4.0
0x62681  starg.s  3
0x62683  ldarg.0
0x62684  ldloc.1
0x62685  ldarg.1
0x62686  ldarg.2
0x62687  ldarg.3
0x62688  ldarg.0
0x62689  ldflda   object Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_chunkPointer
0x6268e  callvirt instance class Microsoft.ReportingServices.Library.ChunkStorage Microsoft.ReportingServices.Library.SqlChunkAccess::CreateChunk(unsigned int8[] buffer, int32 offset, int32 count, [out] object& chunkPointer)
0x62693  stfld    class Microsoft.ReportingServices.Library.ChunkStorage Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_storage
0x62698  ldarg.0
0x62699  ldarg.0
0x6269a  ldfld    int64 Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_position
0x6269f  ldarg.3
0x626a0  conv.i8
0x626a1  add
0x626a2  stfld    int64 Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_position
0x626a7  ldarg.0
0x626a8  ldarg.3
0x626a9  conv.i8
0x626aa  stfld    int64 Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_length
0x626af  ldc.i4.1
0x626b0  stloc.0
0x626b1  ldarg.0
0x626b2  ldc.i4.1
0x626b3  stfld    bool Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_isChunkOpened
0x626b8  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x626bd  ldarg.0
0x626be  ldfld    class Microsoft.ReportingServices.Library.ChunkStorage Microsoft.ReportingServices.Library.SqlChunkWriteStream::m_storage
0x626c3  ldnull
0x626c4  cgt.un
0x626c6  ldstr    aMStorage// "m_storage"
0x626cb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x626d0  ldloc.0
0x626d1  ret
```
