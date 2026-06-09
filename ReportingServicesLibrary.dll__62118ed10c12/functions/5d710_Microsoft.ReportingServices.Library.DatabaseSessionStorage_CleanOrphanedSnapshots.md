# Microsoft.ReportingServices.Library.DatabaseSessionStorage::CleanOrphanedSnapshots

- ea: `0x5d710`
- end: `0x5da70`
- name: `Microsoft.ReportingServices.Library.DatabaseSessionStorage::CleanOrphanedSnapshots`
- size: `864`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0xfb60`

## callees

- `0xf200`
- `0x15e90`
- `0x161e0`
- `0x5d710`
- `0x8bc50`
- `0x8bc60`
- `0x8bc70`

## string_xrefs

- `0x5d7b8`: `@TemporarySnapshotCount`
- `0x5d7f8`: `@TemporaryChunkCount`
- `0x5d838`: `@TemporaryMappingCount`
- `0x5d878`: `@TemporarySegmentCount`

## pseudocode

```c

```

## disassembly

```asm
0x5d710  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CleanupTracer()
0x5d715  ldc.i4.4
0x5d716  ldstr    aCleaningOrphan// "Cleaning orphaned snapshots from DB"
0x5d71b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5d720  ldarg.1
0x5d721  ldc.i4.0
0x5d722  stind.i4
0x5d723  ldarg.2
0x5d724  ldc.i4.0
0x5d725  stind.i4
0x5d726  ldarg.3
0x5d727  ldc.i4.0
0x5d728  stind.i4
0x5d729  ldc.i4.1
0x5d72a  ldc.i4   0x1000
0x5d72f  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::.ctor(valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType, valuetype [System.Data]System.Data.IsolationLevel)
0x5d734  stloc.0
0x5d735  ldloc.0
0x5d736  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x5d73b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x5d740  stloc.1
0x5d741  ldloc.0
0x5d742  callvirt instance class [mscorlib]System.IDisposable [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x5d747  stloc.2
0x5d748  ldstr    aCleanorphaneds// "CleanOrphanedSnapshots"
0x5d74d  ldloc.0
0x5d74e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_Connection()
0x5d753  ldloc.0
0x5d754  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_Transaction()
0x5d759  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction)
0x5d75e  call     class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand)
0x5d763  stloc.3
0x5d764  ldloc.3
0x5d765  ldc.i4.4
0x5d766  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x5d76b  ldloc.3
0x5d76c  call     int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_SqlCleanupTimeoutSeconds()
0x5d771  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout(int32)
0x5d776  ldloc.3
0x5d777  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5d77c  ldstr    aMachine// "@Machine"
0x5d781  ldc.i4.s 0xC
0x5d783  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5d788  call     string [mscorlib]System.Environment::get_MachineName()
0x5d78d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5d792  ldloc.3
0x5d793  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5d798  ldstr    aPermanentsnaps// "@PermanentSnapshotCount"
0x5d79d  ldc.i4.8
0x5d79e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5d7a3  call     int32 CleanupStorage::get_SnapshotCountPerBatch()
0x5d7a8  box      [mscorlib]System.Int32
0x5d7ad  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5d7b2  ldloc.3
0x5d7b3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5d7b8  ldstr    aTemporarysnaps// "@TemporarySnapshotCount"
0x5d7bd  ldc.i4.8
0x5d7be  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5d7c3  call     int32 CleanupStorage::get_SnapshotCountPerBatch()
0x5d7c8  box      [mscorlib]System.Int32
0x5d7cd  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5d7d2  ldloc.3
0x5d7d3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5d7d8  ldstr    aPermanentchunk// "@PermanentChunkCount"
0x5d7dd  ldc.i4.8
0x5d7de  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5d7e3  call     int32 CleanupStorage::get_ChunkCountPerBatch()
0x5d7e8  box      [mscorlib]System.Int32
0x5d7ed  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5d7f2  ldloc.3
0x5d7f3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5d7f8  ldstr    aTemporarychunk// "@TemporaryChunkCount"
0x5d7fd  ldc.i4.8
0x5d7fe  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5d803  call     int32 CleanupStorage::get_ChunkCountPerBatch()
0x5d808  box      [mscorlib]System.Int32
0x5d80d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5d812  ldloc.3
0x5d813  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5d818  ldstr    aPermanentmappi// "@PermanentMappingCount"
0x5d81d  ldc.i4.8
0x5d81e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5d823  call     int32 CleanupStorage::get_ChunkCountPerBatch()
0x5d828  box      [mscorlib]System.Int32
0x5d82d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5d832  ldloc.3
0x5d833  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5d838  ldstr    aTemporarymappi// "@TemporaryMappingCount"
0x5d83d  ldc.i4.8
0x5d83e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5d843  call     int32 CleanupStorage::get_ChunkCountPerBatch()
0x5d848  box      [mscorlib]System.Int32
0x5d84d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5d852  ldloc.3
0x5d853  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5d858  ldstr    aPermanentsegme// "@PermanentSegmentCount"
0x5d85d  ldc.i4.8
0x5d85e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5d863  call     int32 CleanupStorage::get_SegmentCountPerBatch()
0x5d868  box      [mscorlib]System.Int32
0x5d86d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5d872  ldloc.3
0x5d873  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5d878  ldstr    aTemporarysegme// "@TemporarySegmentCount"
0x5d87d  ldc.i4.8
0x5d87e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5d883  call     int32 CleanupStorage::get_SegmentCountPerBatch()
0x5d888  box      [mscorlib]System.Int32
0x5d88d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5d892  ldloc.3
0x5d893  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5d898  ldstr    aSnapshotsclean// "@SnapshotsCleaned"
0x5d89d  ldc.i4.8
0x5d89e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5d8a3  stloc.s  4
0x5d8a5  ldloc.s  4
0x5d8a7  ldc.i4.2
0x5d8a8  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x5d8ad  ldloc.3
0x5d8ae  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5d8b3  ldstr    aChunkscleaned// "@ChunksCleaned"
0x5d8b8  ldc.i4.8
0x5d8b9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5d8be  stloc.s  5
0x5d8c0  ldloc.s  5
0x5d8c2  ldc.i4.2
0x5d8c3  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x5d8c8  ldloc.3
0x5d8c9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5d8ce  ldstr    aMappingscleane// "@MappingsCleaned"
0x5d8d3  ldc.i4.8
0x5d8d4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5d8d9  stloc.s  6
0x5d8db  ldloc.s  6
0x5d8dd  ldc.i4.2
0x5d8de  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x5d8e3  ldloc.3
0x5d8e4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5d8e9  ldstr    aSegmentscleane// "@SegmentsCleaned"
0x5d8ee  ldc.i4.8
0x5d8ef  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5d8f4  stloc.s  7
0x5d8f6  ldloc.s  7
0x5d8f8  ldc.i4.2
0x5d8f9  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x5d8fe  ldloc.3
0x5d8ff  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x5d904  stloc.s  9
0x5d906  br.s     loc_5D924
0x5d908  ldloc.s  9
0x5d90a  ldc.i4.0
0x5d90b  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5d910  brtrue.s loc_5D924
0x5d912  ldloc.s  9
0x5d914  ldc.i4.0
0x5d915  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x5d91a  stloc.s  0xA
0x5d91c  ldloc.1
0x5d91d  ldloc.s  0xA
0x5d91f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x5d924  ldloc.s  9
0x5d926  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x5d92b  brtrue.s loc_5D908
0x5d92d  leave.s  loc_5D93B
0x5d92f  ldloc.s  9
0x5d931  brfalse.s loc_5D93A
0x5d933  ldloc.s  9
0x5d935  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d93a  endfinally
0x5d93b  ldc.i4.0
0x5d93c  stloc.s  8
0x5d93e  ldloc.s  4
0x5d940  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x5d945  brfalse.s loc_5D963
0x5d947  ldloc.s  4
0x5d949  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x5d94e  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d953  beq.s    loc_5D963
0x5d955  ldloc.s  4
0x5d957  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x5d95c  unbox.any [mscorlib]System.Int32
0x5d961  stloc.s  8
0x5d963  ldloc.s  5
0x5d965  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x5d96a  brfalse.s loc_5D988
0x5d96c  ldloc.s  5
0x5d96e  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x5d973  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d978  beq.s    loc_5D988
0x5d97a  ldarg.1
0x5d97b  ldloc.s  5
0x5d97d  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x5d982  unbox.any [mscorlib]System.Int32
0x5d987  stind.i4
0x5d988  ldloc.s  6
0x5d98a  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x5d98f  brfalse.s loc_5D9AD
0x5d991  ldloc.s  6
0x5d993  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x5d998  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d99d  beq.s    loc_5D9AD
0x5d99f  ldarg.2
0x5d9a0  ldloc.s  6
0x5d9a2  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x5d9a7  unbox.any [mscorlib]System.Int32
0x5d9ac  stind.i4
0x5d9ad  ldloc.s  7
0x5d9af  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x5d9b4  brfalse.s loc_5D9D2
0x5d9b6  ldloc.s  7
0x5d9b8  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x5d9bd  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d9c2  beq.s    loc_5D9D2
0x5d9c4  ldarg.3
0x5d9c5  ldloc.s  7
0x5d9c7  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x5d9cc  unbox.any [mscorlib]System.Int32
0x5d9d1  stind.i4
0x5d9d2  ldloc.s  8
0x5d9d4  stloc.s  0xB
0x5d9d6  leave    loc_5DA6D
0x5d9db  ldloc.3
0x5d9dc  brfalse.s loc_5D9E4
0x5d9de  ldloc.3
0x5d9df  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d9e4  endfinally
0x5d9e5  ldloc.2
0x5d9e6  brfalse.s loc_5D9EE
0x5d9e8  ldloc.2
0x5d9e9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d9ee  endfinally
0x5d9ef  stloc.s  0xC
0x5d9f1  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CleanupTracer()
0x5d9f6  ldc.i4.1
0x5d9f7  ldstr    aErrorInCleanor_0// "Error in CleanOrphanedSnapshots: {0}"
0x5d9fc  ldc.i4.1
0x5d9fd  newarr   [mscorlib]System.Object
0x5da02  dup
0x5da03  ldc.i4.0
0x5da04  ldloc.s  0xC
0x5da06  stelem.ref
0x5da07  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x5da0c  ldloc.s  0xC
0x5da0e  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x5da13  brtrue.s loc_5DA17
0x5da15  rethrow
0x5da17  ldc.i4.0
0x5da18  stloc.s  0xB
0x5da1a  leave.s  loc_5DA6D
0x5da1c  nop
0x5da1d  ldloc.0
0x5da1e  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x5da23  leave.s  loc_5DA6C
0x5da25  ldloc.1
0x5da26  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x5da2b  stloc.s  0xD
0x5da2d  br.s     loc_5DA52
0x5da2f  ldloca.s 0xD
0x5da31  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x5da36  stloc.s  0xE
0x5da38  call     class Microsoft.ReportingServices.Library.PartitionManager Microsoft.ReportingServices.Library.Global::get_PartitionManager()
0x5da3d  ldloc.s  0xE
0x5da3f  callvirt instance bool Microsoft.ReportingServices.Library.PartitionManager::DeleteChunkFile(valuetype [mscorlib]System.Guid chunkId)
0x5da44  pop
0x5da45  leave.s  loc_5DA52
0x5da47  call     bool Microsoft.ReportingServices.Library.PartitionManager::HandleFileCleanupException(class [mscorlib]System.Exception e)
0x5da4c  brtrue.s loc_5DA50
0x5da4e  rethrow
0x5da50  leave.s  loc_5DA52
0x5da52  ldloca.s 0xD
0x5da54  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x5da59  brtrue.s loc_5DA2F
0x5da5b  leave.s  loc_5DA6B
0x5da5d  ldloca.s 0xD
0x5da5f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x5da65  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5da6a  endfinally
0x5da6b  endfinally
0x5da6c  endfinally
0x5da6d  ldloc.s  0xB
0x5da6f  ret
```
