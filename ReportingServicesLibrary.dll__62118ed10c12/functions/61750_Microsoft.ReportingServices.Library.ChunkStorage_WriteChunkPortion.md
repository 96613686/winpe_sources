# Microsoft.ReportingServices.Library.ChunkStorage::WriteChunkPortion

- ea: `0x61750`
- end: `0x618a5`
- name: `Microsoft.ReportingServices.Library.ChunkStorage::WriteChunkPortion`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x62490`

## callees

- `0x61750`

## string_xrefs

- `0x617c6`: `@DeleteLength`
- `0x6181f`: `WriteChunkPortion - connection state = `
- `0x6184c`: `WriteChunkPortion - reader had something to read`
- `0x6185f`: `WriteChunkPortion - reader has next result`
- `0x61751`: `WriteChunkPortion`
- `0x61778`: `Chunk pointer is null on Write Chunk Portion.`
- `0x6187f`: `WriteChunkPortion: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x61750  ldarg.0
0x61751  ldstr    aWritechunkport_2// "WriteChunkPortion"
0x61756  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.CancelableSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewCancelableStandardSqlCommand(string)
0x6175b  stloc.0
0x6175c  ldloc.0
0x6175d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61762  ldstr    aChunkpointer// "@ChunkPointer"
0x61767  ldc.i4.1
0x61768  ldc.i4.s 0x10
0x6176a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6176f  ldarg.1
0x61770  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61775  ldarg.1
0x61776  brtrue.s loc_61783
0x61778  ldstr    aChunkPointerIs// "Chunk pointer is null on Write Chunk Po"...
0x6177d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x61782  throw
0x61783  ldloc.0
0x61784  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61789  ldstr    aIspermanentsna// "@IsPermanentSnapshot"
0x6178e  ldc.i4.2
0x6178f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x61794  ldarg.2
0x61795  box      [mscorlib]System.Boolean
0x6179a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6179f  ldarg.s  7
0x617a1  ldc.i4.1
0x617a2  bne.un.s loc_617E7
0x617a4  ldloc.0
0x617a5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x617aa  ldstr    aDataindex// "@DataIndex"
0x617af  ldc.i4.8
0x617b0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x617b5  ldarg.3
0x617b6  box      [mscorlib]System.Int64
0x617bb  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x617c0  ldloc.0
0x617c1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x617c6  ldstr    aDeletelength// "@DeleteLength"
0x617cb  ldc.i4.8
0x617cc  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x617d1  ldarg.s  6
0x617d3  ldarg.s  8
0x617d5  ldarg.3
0x617d6  sub
0x617d7  conv.i4
0x617d8  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x617dd  box      [mscorlib]System.Int32
0x617e2  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x617e7  ldloc.0
0x617e8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x617ed  ldstr    aContent_0// "@Content"
0x617f2  ldc.i4.7
0x617f3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x617f8  dup
0x617f9  ldarg.s  4
0x617fb  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61800  dup
0x61801  ldarg.s  6
0x61803  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x61808  ldarg.s  5
0x6180a  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_Offset(int32)
0x6180f  ldloc.0
0x61810  callvirt instance class [System.Data]System.Data.IDbConnection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Connection()
0x61815  callvirt instance valuetype [System.Data]System.Data.ConnectionState [System.Data]System.Data.IDbConnection::get_State()
0x6181a  stloc.1
0x6181b  ldloc.1
0x6181c  ldc.i4.1
0x6181d  beq.s    loc_6183C
0x6181f  ldstr    aWritechunkport// "WriteChunkPortion - connection state = "
0x61824  ldloca.s 1
0x61826  constrained. [System.Data]System.Data.ConnectionState
0x6182c  callvirt instance string [mscorlib]System.Object::ToString()
0x61831  call     string [mscorlib]System.String::Concat(string, string)
0x61836  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ReportServerDatabaseUnavailableException::.ctor(string)
0x6183b  throw
0x6183c  nop
0x6183d  ldloc.0
0x6183e  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x61843  stloc.2
0x61844  ldloc.2
0x61845  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x6184a  brfalse.s loc_61857
0x6184c  ldstr    aWritechunkport_0// "WriteChunkPortion - reader had somethin"...
0x61851  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x61856  throw
0x61857  ldloc.2
0x61858  callvirt instance bool [System.Data]System.Data.IDataReader::NextResult()
0x6185d  brfalse.s loc_6186A
0x6185f  ldstr    aWritechunkport_1// "WriteChunkPortion - reader has next res"...
0x61864  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x61869  throw
0x6186a  leave.s  loc_61876
0x6186c  ldloc.2
0x6186d  brfalse.s loc_61875
0x6186f  ldloc.2
0x61870  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61875  endfinally
0x61876  leave.s  loc_618A4
0x61878  stloc.3
0x61879  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x6187e  ldc.i4.1
0x6187f  ldstr    aWritechunkport_3// "WriteChunkPortion: {0}"
0x61884  ldc.i4.1
0x61885  newarr   [mscorlib]System.Object
0x6188a  dup
0x6188b  ldc.i4.0
0x6188c  ldloc.3
0x6188d  callvirt instance string [mscorlib]System.Object::ToString()
0x61892  stelem.ref
0x61893  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x61898  rethrow
0x6189a  ldloc.0
0x6189b  brfalse.s loc_618A3
0x6189d  ldloc.0
0x6189e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x618a3  endfinally
0x618a4  ret
```
