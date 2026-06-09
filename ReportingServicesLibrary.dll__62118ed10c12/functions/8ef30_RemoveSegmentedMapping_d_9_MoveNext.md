# <RemoveSegmentedMapping>d__9::MoveNext

- ea: `0x8ef30`
- end: `0x8f090`
- name: `<RemoveSegmentedMapping>d__9::MoveNext`
- size: `352`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x8bc50`
- `0x8eea0`
- `0x8ef00`
- `0x8ef30`
- `0x8f090`
- `0x8f0b0`

## string_xrefs

- `0x8ef58`: `RemoveSegmentedMapping`
- `0x8ef86`: `@DeleteCountPermanentChunk`
- `0x8efa2`: `@DeleteCountPermanentMapping`
- `0x8efbe`: `@DeleteCountTempChunk`
- `0x8efda`: `@DeleteCountTempMapping`

## pseudocode

```c

```

## disassembly

```asm
0x8ef30  ldarg.0
0x8ef31  ldfld    int32 <RemoveSegmentedMapping>d__9::<>1__state
0x8ef36  stloc.1
0x8ef37  ldarg.0
0x8ef38  ldfld    class CleanupStorage <RemoveSegmentedMapping>d__9::<>4__this
0x8ef3d  stloc.2
0x8ef3e  ldloc.1
0x8ef3f  brfalse.s loc_8EF4F
0x8ef41  ldloc.1
0x8ef42  ldc.i4.1
0x8ef43  beq      loc_8F054
0x8ef48  ldc.i4.0
0x8ef49  stloc.0
0x8ef4a  leave    loc_8F08E
0x8ef4f  ldarg.0
0x8ef50  ldc.i4.m1
0x8ef51  stfld    int32 <RemoveSegmentedMapping>d__9::<>1__state
0x8ef56  ldarg.0
0x8ef57  ldloc.2
0x8ef58  ldstr    aRemovesegmente// "RemoveSegmentedMapping"
0x8ef5d  ldnull
0x8ef5e  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x8ef63  stfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand <RemoveSegmentedMapping>d__9::<command>5__2
0x8ef68  ldarg.0
0x8ef69  ldc.i4.s 0xFD
0x8ef6b  stfld    int32 <RemoveSegmentedMapping>d__9::<>1__state
0x8ef70  ldarg.0
0x8ef71  ldfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand <RemoveSegmentedMapping>d__9::<command>5__2
0x8ef76  call     int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_SqlCleanupTimeoutSeconds()
0x8ef7b  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout(int32)
0x8ef80  ldarg.0
0x8ef81  ldfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand <RemoveSegmentedMapping>d__9::<command>5__2
0x8ef86  ldstr    aDeletecountper_0// "@DeleteCountPermanentChunk"
0x8ef8b  ldc.i4.8
0x8ef8c  call     int32 CleanupStorage::get_ChunkCountPerBatch()
0x8ef91  box      [mscorlib]System.Int32
0x8ef96  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x8ef9b  pop
0x8ef9c  ldarg.0
0x8ef9d  ldfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand <RemoveSegmentedMapping>d__9::<command>5__2
0x8efa2  ldstr    aDeletecountper_1// "@DeleteCountPermanentMapping"
0x8efa7  ldc.i4.8
0x8efa8  call     int32 CleanupStorage::get_ChunkCountPerBatch()
0x8efad  box      [mscorlib]System.Int32
0x8efb2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x8efb7  pop
0x8efb8  ldarg.0
0x8efb9  ldfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand <RemoveSegmentedMapping>d__9::<command>5__2
0x8efbe  ldstr    aDeletecounttem_0// "@DeleteCountTempChunk"
0x8efc3  ldc.i4.8
0x8efc4  call     int32 CleanupStorage::get_ChunkCountPerBatch()
0x8efc9  box      [mscorlib]System.Int32
0x8efce  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x8efd3  pop
0x8efd4  ldarg.0
0x8efd5  ldfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand <RemoveSegmentedMapping>d__9::<command>5__2
0x8efda  ldstr    aDeletecounttem_1// "@DeleteCountTempMapping"
0x8efdf  ldc.i4.8
0x8efe0  call     int32 CleanupStorage::get_ChunkCountPerBatch()
0x8efe5  box      [mscorlib]System.Int32
0x8efea  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x8efef  pop
0x8eff0  ldarg.0
0x8eff1  ldfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand <RemoveSegmentedMapping>d__9::<command>5__2
0x8eff6  ldstr    aMachinename_0// "@MachineName"
0x8effb  ldc.i4.s 0xC
0x8effd  call     string [mscorlib]System.Environment::get_MachineName()
0x8f002  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x8f007  pop
0x8f008  ldarg.0
0x8f009  ldarg.0
0x8f00a  ldfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand <RemoveSegmentedMapping>d__9::<command>5__2
0x8f00f  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x8f014  stfld    class [System.Data]System.Data.IDataReader <RemoveSegmentedMapping>d__9::<reader>5__3
0x8f019  ldarg.0
0x8f01a  ldc.i4.s 0xFC
0x8f01c  stfld    int32 <RemoveSegmentedMapping>d__9::<>1__state
0x8f021  br.s     loc_8F05C
0x8f023  ldloca.s 3
0x8f025  ldarg.0
0x8f026  ldfld    class [System.Data]System.Data.IDataReader <RemoveSegmentedMapping>d__9::<reader>5__3
0x8f02b  ldc.i4.0
0x8f02c  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x8f031  ldarg.0
0x8f032  ldfld    class [System.Data]System.Data.IDataReader <RemoveSegmentedMapping>d__9::<reader>5__3
0x8f037  ldc.i4.1
0x8f038  callvirt instance bool [System.Data]System.Data.IDataRecord::GetBoolean(int32)
0x8f03d  call     instance void DeletedChunkInfo::.ctor(valuetype [mscorlib]System.Guid chunkId, bool isPermanent)
0x8f042  ldarg.0
0x8f043  ldloc.3
0x8f044  stfld    valuetype DeletedChunkInfo <RemoveSegmentedMapping>d__9::<>2__current
0x8f049  ldarg.0
0x8f04a  ldc.i4.1
0x8f04b  stfld    int32 <RemoveSegmentedMapping>d__9::<>1__state
0x8f050  ldc.i4.1
0x8f051  stloc.0
0x8f052  leave.s  loc_8F08E
0x8f054  ldarg.0
0x8f055  ldc.i4.s 0xFC
0x8f057  stfld    int32 <RemoveSegmentedMapping>d__9::<>1__state
0x8f05c  ldarg.0
0x8f05d  ldfld    class [System.Data]System.Data.IDataReader <RemoveSegmentedMapping>d__9::<reader>5__3
0x8f062  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x8f067  brtrue.s loc_8F023
0x8f069  ldarg.0
0x8f06a  call     instance void <RemoveSegmentedMapping>d__9::<>m__Finally2()
0x8f06f  ldarg.0
0x8f070  ldnull
0x8f071  stfld    class [System.Data]System.Data.IDataReader <RemoveSegmentedMapping>d__9::<reader>5__3
0x8f076  ldarg.0
0x8f077  call     instance void <RemoveSegmentedMapping>d__9::<>m__Finally1()
0x8f07c  ldarg.0
0x8f07d  ldnull
0x8f07e  stfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand <RemoveSegmentedMapping>d__9::<command>5__2
0x8f083  ldc.i4.0
0x8f084  stloc.0
0x8f085  leave.s  loc_8F08E
0x8f087  ldarg.0
0x8f088  call     instance void <RemoveSegmentedMapping>d__9::System.IDisposable.Dispose()
0x8f08d  endfinally
0x8f08e  ldloc.0
0x8f08f  ret
```
