# Microsoft.ReportingServices.Library.ChunkStorage::GetChunkInformation

- ea: `0x61cb0`
- end: `0x61e1e`
- name: `Microsoft.ReportingServices.Library.ChunkStorage::GetChunkInformation`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5f0a0`

## callees

- `0x61cb0`

## string_xrefs

- `0x61dbc`: `GetChunkInformation - reader had something to read`
- `0x61dcf`: `GetChunkInformation - reader has next result`

## pseudocode

```c

```

## disassembly

```asm
0x61cb0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x61cb5  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x61cba  brfalse.s loc_61CE9
0x61cbc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x61cc1  ldc.i4.4
0x61cc2  ldstr    aGetchunkinform// "### GetChunkInformation({0}, {1}, {2})"
0x61cc7  ldc.i4.3
0x61cc8  newarr   [mscorlib]System.Object
0x61ccd  dup
0x61cce  ldc.i4.0
0x61ccf  ldarg.1
0x61cd0  box      [mscorlib]System.Guid
0x61cd5  stelem.ref
0x61cd6  dup
0x61cd7  ldc.i4.1
0x61cd8  ldarg.3
0x61cd9  stelem.ref
0x61cda  dup
0x61cdb  ldc.i4.2
0x61cdc  ldarg.s  4
0x61cde  box      [mscorlib]System.Int32
0x61ce3  stelem.ref
0x61ce4  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x61ce9  ldarg.0
0x61cea  ldstr    aGetchunkinform_0// "GetChunkInformation"
0x61cef  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.CancelableSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewCancelableStandardSqlCommand(string)
0x61cf4  stloc.0
0x61cf5  ldloc.0
0x61cf6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61cfb  ldstr    aSnapshotdataid// "@SnapshotDataID"
0x61d00  ldc.i4.s 0xE
0x61d02  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x61d07  ldarg.1
0x61d08  box      [mscorlib]System.Guid
0x61d0d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61d12  ldloc.0
0x61d13  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61d18  ldstr    aIspermanentsna// "@IsPermanentSnapshot"
0x61d1d  ldc.i4.2
0x61d1e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x61d23  ldarg.2
0x61d24  box      [mscorlib]System.Boolean
0x61d29  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61d2e  ldloc.0
0x61d2f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61d34  ldstr    aChunkname// "@ChunkName"
0x61d39  ldc.i4.s 0xC
0x61d3b  ldc.i4   0x104
0x61d40  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x61d45  ldarg.3
0x61d46  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61d4b  ldloc.0
0x61d4c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61d51  ldstr    aChunktype// "@ChunkType"
0x61d56  ldc.i4.8
0x61d57  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x61d5c  ldarg.s  4
0x61d5e  box      [mscorlib]System.Int32
0x61d63  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61d68  ldnull
0x61d69  stloc.1
0x61d6a  ldloc.0
0x61d6b  callvirt instance class [System.Data]System.Data.IDbConnection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Connection()
0x61d70  callvirt instance valuetype [System.Data]System.Data.ConnectionState [System.Data]System.Data.IDbConnection::get_State()
0x61d75  stloc.2
0x61d76  ldloc.2
0x61d77  ldc.i4.1
0x61d78  beq.s    loc_61D97
0x61d7a  ldstr    aGetchunkinform_1// "GetChunkInformation - connection state "...
0x61d7f  ldloca.s 2
0x61d81  constrained. [System.Data]System.Data.ConnectionState
0x61d87  callvirt instance string [mscorlib]System.Object::ToString()
0x61d8c  call     string [mscorlib]System.String::Concat(string, string)
0x61d91  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ReportServerDatabaseUnavailableException::.ctor(string)
0x61d96  throw
0x61d97  nop
0x61d98  ldloc.0
0x61d99  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x61d9e  stloc.3
0x61d9f  ldloc.3
0x61da0  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x61da5  brtrue.s loc_61DAC
0x61da7  ldnull
0x61da8  stloc.s  4
0x61daa  leave.s  loc_61E1B
0x61dac  ldloc.3
0x61dad  ldc.i4.0
0x61dae  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x61db3  stloc.1
0x61db4  ldloc.3
0x61db5  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x61dba  brfalse.s loc_61DC7
0x61dbc  ldstr    aGetchunkinform_2// "GetChunkInformation - reader had someth"...
0x61dc1  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x61dc6  throw
0x61dc7  ldloc.3
0x61dc8  callvirt instance bool [System.Data]System.Data.IDataReader::NextResult()
0x61dcd  brfalse.s loc_61DDA
0x61dcf  ldstr    aGetchunkinform_3// "GetChunkInformation - reader has next r"...
0x61dd4  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x61dd9  throw
0x61dda  leave.s  loc_61DE6
0x61ddc  ldloc.3
0x61ddd  brfalse.s loc_61DE5
0x61ddf  ldloc.3
0x61de0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61de5  endfinally
0x61de6  leave.s  loc_61E0C
0x61de8  stloc.s  5
0x61dea  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x61def  ldc.i4.1
0x61df0  ldstr    aGetchunkinform_4// "GetChunkInformation: {0}"
0x61df5  ldc.i4.1
0x61df6  newarr   [mscorlib]System.Object
0x61dfb  dup
0x61dfc  ldc.i4.0
0x61dfd  ldloc.s  5
0x61dff  callvirt instance string [mscorlib]System.Object::ToString()
0x61e04  stelem.ref
0x61e05  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x61e0a  rethrow
0x61e0c  ldloc.1
0x61e0d  stloc.s  4
0x61e0f  leave.s  loc_61E1B
0x61e11  ldloc.0
0x61e12  brfalse.s loc_61E1A
0x61e14  ldloc.0
0x61e15  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61e1a  endfinally
0x61e1b  ldloc.s  4
0x61e1d  ret
```
