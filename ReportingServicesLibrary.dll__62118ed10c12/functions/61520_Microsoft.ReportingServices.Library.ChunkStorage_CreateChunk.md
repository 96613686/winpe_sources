# Microsoft.ReportingServices.Library.ChunkStorage::CreateChunk

- ea: `0x61520`
- end: `0x6174d`
- name: `Microsoft.ReportingServices.Library.ChunkStorage::CreateChunk`
- size: `557`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x626f0`
- `0x63370`

## callees

- `0x61520`

## string_xrefs

- `0x61532`: `### CreateChunk({0}, {1}, {2}, |{3}|, ofs {4}, L {5})`
- `0x6157a`: `CreateChunkAndGetPointer`
- `0x616aa`: `WriteChunkPortion - connection state = `
- `0x616d7`: `WriteChunkPortion - reader had something to read`
- `0x616ea`: `WriteChunkPortion - reader has next result`
- `0x6170b`: `CreateChunkAndGetPointer: {0}`
- `0x61735`: `CreateChunkAndGetPointer - null chunk pointer!`

## pseudocode

```c

```

## disassembly

```asm
0x61520  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x61525  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x6152a  brfalse.s loc_61579
0x6152c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x61531  ldc.i4.4
0x61532  ldstr    aCreatechunk012// "### CreateChunk({0}, {1}, {2}, |{3}|, o"...
0x61537  ldc.i4.6
0x61538  newarr   [mscorlib]System.Object
0x6153d  dup
0x6153e  ldc.i4.0
0x6153f  ldarg.1
0x61540  box      [mscorlib]System.Guid
0x61545  stelem.ref
0x61546  dup
0x61547  ldc.i4.1
0x61548  ldarg.3
0x61549  stelem.ref
0x6154a  dup
0x6154b  ldc.i4.2
0x6154c  ldarg.s  4
0x6154e  box      [mscorlib]System.Int32
0x61553  stelem.ref
0x61554  dup
0x61555  ldc.i4.3
0x61556  ldarg.s  8
0x61558  ldlen
0x61559  conv.i4
0x6155a  box      [mscorlib]System.Int32
0x6155f  stelem.ref
0x61560  dup
0x61561  ldc.i4.4
0x61562  ldarg.s  9
0x61564  box      [mscorlib]System.Int32
0x61569  stelem.ref
0x6156a  dup
0x6156b  ldc.i4.5
0x6156c  ldarg.s  0xA
0x6156e  box      [mscorlib]System.Int32
0x61573  stelem.ref
0x61574  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x61579  ldarg.0
0x6157a  ldstr    aCreatechunkand// "CreateChunkAndGetPointer"
0x6157f  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.CancelableSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewCancelableStandardSqlCommand(string)
0x61584  stloc.0
0x61585  ldloc.0
0x61586  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6158b  ldstr    aSnapshotdataid// "@SnapshotDataID"
0x61590  ldc.i4.s 0xE
0x61592  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x61597  ldarg.1
0x61598  box      [mscorlib]System.Guid
0x6159d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x615a2  ldloc.0
0x615a3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x615a8  ldstr    aIspermanentsna// "@IsPermanentSnapshot"
0x615ad  ldc.i4.2
0x615ae  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x615b3  ldarg.2
0x615b4  box      [mscorlib]System.Boolean
0x615b9  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x615be  ldloc.0
0x615bf  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x615c4  ldstr    aChunkname// "@ChunkName"
0x615c9  ldc.i4.s 0xC
0x615cb  ldc.i4   0x104
0x615d0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x615d5  ldarg.3
0x615d6  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x615db  ldloc.0
0x615dc  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x615e1  ldstr    aChunktype// "@ChunkType"
0x615e6  ldc.i4.8
0x615e7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x615ec  ldarg.s  4
0x615ee  box      [mscorlib]System.Int32
0x615f3  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x615f8  ldarg.s  5
0x615fa  brfalse.s loc_6161A
0x615fc  ldloc.0
0x615fd  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61602  ldstr    aMimetype// "@MimeType"
0x61607  ldc.i4.s 0xC
0x61609  ldc.i4   0x104
0x6160e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x61613  ldarg.s  5
0x61615  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6161a  ldloc.0
0x6161b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61620  ldstr    aVersion// "@Version"
0x61625  ldc.i4.s 0x10
0x61627  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6162c  ldarg.s  7
0x6162e  box      [mscorlib]System.Int16
0x61633  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61638  ldloc.0
0x61639  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6163e  ldstr    aChunkflags// "@ChunkFlags"
0x61643  ldc.i4.s 0x14
0x61645  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6164a  ldarg.s  6
0x6164c  conv.u1
0x6164d  box      [mscorlib]System.Byte
0x61652  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61657  ldloc.0
0x61658  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6165d  ldstr    aContent_0// "@Content"
0x61662  ldc.i4.7
0x61663  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x61668  dup
0x61669  ldarg.s  8
0x6166b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61670  dup
0x61671  ldarg.s  0xA
0x61673  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x61678  ldarg.s  9
0x6167a  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_Offset(int32)
0x6167f  ldloc.0
0x61680  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61685  ldstr    aChunkpointer// "@ChunkPointer"
0x6168a  ldc.i4.1
0x6168b  ldc.i4.s 0x10
0x6168d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x61692  stloc.1
0x61693  ldloc.1
0x61694  ldc.i4.2
0x61695  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x6169a  ldloc.0
0x6169b  callvirt instance class [System.Data]System.Data.IDbConnection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Connection()
0x616a0  callvirt instance valuetype [System.Data]System.Data.ConnectionState [System.Data]System.Data.IDbConnection::get_State()
0x616a5  stloc.2
0x616a6  ldloc.2
0x616a7  ldc.i4.1
0x616a8  beq.s    loc_616C7
0x616aa  ldstr    aWritechunkport// "WriteChunkPortion - connection state = "
0x616af  ldloca.s 2
0x616b1  constrained. [System.Data]System.Data.ConnectionState
0x616b7  callvirt instance string [mscorlib]System.Object::ToString()
0x616bc  call     string [mscorlib]System.String::Concat(string, string)
0x616c1  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ReportServerDatabaseUnavailableException::.ctor(string)
0x616c6  throw
0x616c7  nop
0x616c8  ldloc.0
0x616c9  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x616ce  stloc.3
0x616cf  ldloc.3
0x616d0  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x616d5  brfalse.s loc_616E2
0x616d7  ldstr    aWritechunkport_0// "WriteChunkPortion - reader had somethin"...
0x616dc  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x616e1  throw
0x616e2  ldloc.3
0x616e3  callvirt instance bool [System.Data]System.Data.IDataReader::NextResult()
0x616e8  brfalse.s loc_616F5
0x616ea  ldstr    aWritechunkport_1// "WriteChunkPortion - reader has next res"...
0x616ef  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x616f4  throw
0x616f5  leave.s  loc_61701
0x616f7  ldloc.3
0x616f8  brfalse.s loc_61700
0x616fa  ldloc.3
0x616fb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61700  endfinally
0x61701  leave.s  loc_61727
0x61703  stloc.s  4
0x61705  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x6170a  ldc.i4.1
0x6170b  ldstr    aCreatechunkand_0// "CreateChunkAndGetPointer: {0}"
0x61710  ldc.i4.1
0x61711  newarr   [mscorlib]System.Object
0x61716  dup
0x61717  ldc.i4.0
0x61718  ldloc.s  4
0x6171a  callvirt instance string [mscorlib]System.Object::ToString()
0x6171f  stelem.ref
0x61720  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x61725  rethrow
0x61727  ldarg.s  0xB
0x61729  ldloc.1
0x6172a  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x6172f  stind.ref
0x61730  ldarg.s  0xB
0x61732  ldind.ref
0x61733  brtrue.s loc_61740
0x61735  ldstr    aCreatechunkand_1// "CreateChunkAndGetPointer - null chunk p"...
0x6173a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x6173f  throw
0x61740  leave.s  loc_6174C
0x61742  ldloc.0
0x61743  brfalse.s loc_6174B
0x61745  ldloc.0
0x61746  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6174b  endfinally
0x6174c  ret
```
