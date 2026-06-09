# Microsoft.ReportingServices.Library.ChunkStorage::ReadChunkPortion

- ea: `0x61b90`
- end: `0x61ca7`
- name: `Microsoft.ReportingServices.Library.ChunkStorage::ReadChunkPortion`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x623e0`
- `0x62e60`

## callees

- `0x61b90`

## string_xrefs

- `0x61b91`: `ReadChunkPortion`
- `0x61c4b`: `ReadChunkPortion - reader had something to read`
- `0x61c5e`: `ReadChunkPortion - reader has next result`
- `0x61c7e`: `ReadChunkPortion: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x61b90  ldarg.0
0x61b91  ldstr    aReadchunkporti// "ReadChunkPortion"
0x61b96  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.CancelableSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewCancelableStandardSqlCommand(string)
0x61b9b  stloc.0
0x61b9c  ldloc.0
0x61b9d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61ba2  ldstr    aChunkpointer// "@ChunkPointer"
0x61ba7  ldc.i4.1
0x61ba8  ldc.i4.s 0x10
0x61baa  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x61baf  ldarg.1
0x61bb0  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61bb5  ldloc.0
0x61bb6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61bbb  ldstr    aIspermanentsna// "@IsPermanentSnapshot"
0x61bc0  ldc.i4.2
0x61bc1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x61bc6  ldarg.2
0x61bc7  box      [mscorlib]System.Boolean
0x61bcc  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61bd1  ldloc.0
0x61bd2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61bd7  ldstr    aDataindex// "@DataIndex"
0x61bdc  ldc.i4.8
0x61bdd  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x61be2  ldarg.3
0x61be3  box      [mscorlib]System.Int64
0x61be8  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61bed  ldloc.0
0x61bee  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61bf3  ldstr    aLength// "@Length"
0x61bf8  ldc.i4.8
0x61bf9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x61bfe  ldarg.s  6
0x61c00  box      [mscorlib]System.Int32
0x61c05  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61c0a  ldloc.0
0x61c0b  callvirt instance class [System.Data]System.Data.IDbConnection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Connection()
0x61c10  callvirt instance valuetype [System.Data]System.Data.ConnectionState [System.Data]System.Data.IDbConnection::get_State()
0x61c15  ldc.i4.1
0x61c16  beq.s    loc_61C1F
0x61c18  ldc.i4.0
0x61c19  stloc.1
0x61c1a  leave    loc_61CA5
0x61c1f  nop
0x61c20  ldloc.0
0x61c21  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x61c26  stloc.2
0x61c27  ldloc.2
0x61c28  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x61c2d  brtrue.s loc_61C33
0x61c2f  ldc.i4.0
0x61c30  stloc.1
0x61c31  leave.s  loc_61CA5
0x61c33  ldloc.2
0x61c34  ldc.i4.0
0x61c35  ldc.i4.0
0x61c36  conv.i8
0x61c37  ldarg.s  4
0x61c39  ldarg.s  5
0x61c3b  ldarg.s  6
0x61c3d  callvirt instance int64 [System.Data]System.Data.IDataRecord::GetBytes(int32, int64, unsigned int8[], int32, int32)
0x61c42  pop
0x61c43  ldloc.2
0x61c44  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x61c49  brfalse.s loc_61C56
0x61c4b  ldstr    aReadchunkporti_0// "ReadChunkPortion - reader had something"...
0x61c50  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x61c55  throw
0x61c56  ldloc.2
0x61c57  callvirt instance bool [System.Data]System.Data.IDataReader::NextResult()
0x61c5c  brfalse.s loc_61C69
0x61c5e  ldstr    aReadchunkporti_1// "ReadChunkPortion - reader has next resu"...
0x61c63  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x61c68  throw
0x61c69  leave.s  loc_61C75
0x61c6b  ldloc.2
0x61c6c  brfalse.s loc_61C74
0x61c6e  ldloc.2
0x61c6f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61c74  endfinally
0x61c75  leave.s  loc_61CA3
0x61c77  stloc.3
0x61c78  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x61c7d  ldc.i4.1
0x61c7e  ldstr    aReadchunkporti_2// "ReadChunkPortion: {0}"
0x61c83  ldc.i4.1
0x61c84  newarr   [mscorlib]System.Object
0x61c89  dup
0x61c8a  ldc.i4.0
0x61c8b  ldloc.3
0x61c8c  callvirt instance string [mscorlib]System.Object::ToString()
0x61c91  stelem.ref
0x61c92  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x61c97  rethrow
0x61c99  ldloc.0
0x61c9a  brfalse.s loc_61CA2
0x61c9c  ldloc.0
0x61c9d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61ca2  endfinally
0x61ca3  ldc.i4.1
0x61ca4  ret
0x61ca5  ldloc.1
0x61ca6  ret
```
