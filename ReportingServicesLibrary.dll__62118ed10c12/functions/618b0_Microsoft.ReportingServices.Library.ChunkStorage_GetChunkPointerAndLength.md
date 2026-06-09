# Microsoft.ReportingServices.Library.ChunkStorage::GetChunkPointerAndLength

- ea: `0x618b0`
- end: `0x61a78`
- name: `Microsoft.ReportingServices.Library.ChunkStorage::GetChunkPointerAndLength`
- size: `456`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x626f0`
- `0x63230`

## callees

- `0x618b0`

## string_xrefs

- `0x61a1a`: `GetChunkPointerAndLength - reader had something to read`
- `0x61a2d`: `GetChunkPointerAndLength - reader has next result`

## pseudocode

```c

```

## disassembly

```asm
0x618b0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x618b5  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x618ba  brfalse.s loc_618E9
0x618bc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x618c1  ldc.i4.4
0x618c2  ldstr    aGetchunkpointe// "### GetChunkPointerAndLength({0}, {1}, "...
0x618c7  ldc.i4.3
0x618c8  newarr   [mscorlib]System.Object
0x618cd  dup
0x618ce  ldc.i4.0
0x618cf  ldarg.1
0x618d0  box      [mscorlib]System.Guid
0x618d5  stelem.ref
0x618d6  dup
0x618d7  ldc.i4.1
0x618d8  ldarg.3
0x618d9  stelem.ref
0x618da  dup
0x618db  ldc.i4.2
0x618dc  ldarg.s  4
0x618de  box      [mscorlib]System.Int32
0x618e3  stelem.ref
0x618e4  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x618e9  ldarg.0
0x618ea  ldstr    aGetchunkpointe_0// "GetChunkPointerAndLength"
0x618ef  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.CancelableSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewCancelableStandardSqlCommand(string)
0x618f4  stloc.0
0x618f5  ldloc.0
0x618f6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x618fb  ldstr    aSnapshotdataid// "@SnapshotDataID"
0x61900  ldc.i4.s 0xE
0x61902  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x61907  ldarg.1
0x61908  box      [mscorlib]System.Guid
0x6190d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61912  ldloc.0
0x61913  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61918  ldstr    aIspermanentsna// "@IsPermanentSnapshot"
0x6191d  ldc.i4.2
0x6191e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x61923  ldarg.2
0x61924  box      [mscorlib]System.Boolean
0x61929  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6192e  ldloc.0
0x6192f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61934  ldstr    aChunkname// "@ChunkName"
0x61939  ldc.i4.s 0xC
0x6193b  ldc.i4   0x104
0x61940  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x61945  ldarg.3
0x61946  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6194b  ldloc.0
0x6194c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61951  ldstr    aChunktype// "@ChunkType"
0x61956  ldc.i4.8
0x61957  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6195c  ldarg.s  4
0x6195e  box      [mscorlib]System.Int32
0x61963  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61968  ldloc.0
0x61969  callvirt instance class [System.Data]System.Data.IDbConnection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Connection()
0x6196e  callvirt instance valuetype [System.Data]System.Data.ConnectionState [System.Data]System.Data.IDbConnection::get_State()
0x61973  stloc.1
0x61974  ldloc.1
0x61975  ldc.i4.1
0x61976  beq.s    loc_61995
0x61978  ldstr    aGetchunkpointe_1// "GetChunkPointerAndLength - connection s"...
0x6197d  ldloca.s 1
0x6197f  constrained. [System.Data]System.Data.ConnectionState
0x61985  callvirt instance string [mscorlib]System.Object::ToString()
0x6198a  call     string [mscorlib]System.String::Concat(string, string)
0x6198f  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ReportServerDatabaseUnavailableException::.ctor(string)
0x61994  throw
0x61995  ldarg.s  5
0x61997  ldnull
0x61998  stind.ref
0x61999  ldarg.s  6
0x6199b  ldc.i4.0
0x6199c  conv.i8
0x6199d  stind.i8
0x6199e  ldarg.s  7
0x619a0  ldnull
0x619a1  stind.ref
0x619a2  ldarg.s  8
0x619a4  ldc.i4.0
0x619a5  stind.i4
0x619a6  ldarg.s  9
0x619a8  ldsfld   int16 Microsoft.ReportingServices.Library.ChunkHeader::MissingVersion
0x619ad  stind.i2
0x619ae  ldloc.0
0x619af  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x619b4  stloc.2
0x619b5  ldloc.2
0x619b6  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x619bb  brtrue.s loc_619C4
0x619bd  ldc.i4.0
0x619be  stloc.3
0x619bf  leave    loc_61A76
0x619c4  ldarg.s  5
0x619c6  ldloc.2
0x619c7  ldc.i4.0
0x619c8  callvirt instance object [System.Data]System.Data.IDataRecord::GetValue(int32)
0x619cd  stind.ref
0x619ce  ldarg.s  6
0x619d0  ldloc.2
0x619d1  ldc.i4.1
0x619d2  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x619d7  conv.i8
0x619d8  stind.i8
0x619d9  ldloc.2
0x619da  ldc.i4.2
0x619db  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x619e0  brtrue.s loc_619EC
0x619e2  ldarg.s  7
0x619e4  ldloc.2
0x619e5  ldc.i4.2
0x619e6  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x619eb  stind.ref
0x619ec  ldloc.2
0x619ed  ldc.i4.3
0x619ee  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x619f3  brtrue.s loc_619FF
0x619f5  ldarg.s  8
0x619f7  ldloc.2
0x619f8  ldc.i4.3
0x619f9  callvirt instance unsigned int8 [System.Data]System.Data.IDataRecord::GetByte(int32)
0x619fe  stind.i4
0x619ff  ldloc.2
0x61a00  ldc.i4.4
0x61a01  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x61a06  brtrue.s loc_61A12
0x61a08  ldarg.s  9
0x61a0a  ldloc.2
0x61a0b  ldc.i4.4
0x61a0c  callvirt instance int16 [System.Data]System.Data.IDataRecord::GetInt16(int32)
0x61a11  stind.i2
0x61a12  ldloc.2
0x61a13  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x61a18  brfalse.s loc_61A25
0x61a1a  ldstr    aGetchunkpointe_2// "GetChunkPointerAndLength - reader had s"...
0x61a1f  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x61a24  throw
0x61a25  ldloc.2
0x61a26  callvirt instance bool [System.Data]System.Data.IDataReader::NextResult()
0x61a2b  brfalse.s loc_61A38
0x61a2d  ldstr    aGetchunkpointe_3// "GetChunkPointerAndLength - reader has n"...
0x61a32  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x61a37  throw
0x61a38  leave.s  loc_61A44
0x61a3a  ldloc.2
0x61a3b  brfalse.s loc_61A43
0x61a3d  ldloc.2
0x61a3e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61a43  endfinally
0x61a44  leave.s  loc_61A74
0x61a46  stloc.s  4
0x61a48  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x61a4d  ldc.i4.1
0x61a4e  ldstr    aGetchunkpointe_4// "GetChunkPointerAndLength: {0}"
0x61a53  ldc.i4.1
0x61a54  newarr   [mscorlib]System.Object
0x61a59  dup
0x61a5a  ldc.i4.0
0x61a5b  ldloc.s  4
0x61a5d  callvirt instance string [mscorlib]System.Object::ToString()
0x61a62  stelem.ref
0x61a63  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x61a68  leave.s  loc_61A74
0x61a6a  ldloc.0
0x61a6b  brfalse.s loc_61A73
0x61a6d  ldloc.0
0x61a6e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61a73  endfinally
0x61a74  ldc.i4.1
0x61a75  ret
0x61a76  ldloc.3
0x61a77  ret
```
