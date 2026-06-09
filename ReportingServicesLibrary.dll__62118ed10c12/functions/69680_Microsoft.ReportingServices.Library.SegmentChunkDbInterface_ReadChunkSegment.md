# Microsoft.ReportingServices.Library.SegmentChunkDbInterface::ReadChunkSegment

- ea: `0x69680`
- end: `0x69766`
- name: `Microsoft.ReportingServices.Library.SegmentChunkDbInterface::ReadChunkSegment`
- size: `230`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8c610`
- `0x8c730`

## callees

- `0x69680`

## string_xrefs

- `0x69681`: `ReadChunkSegment`
- `0x69732`: `no data to read`

## pseudocode

```c

```

## disassembly

```asm
0x69680  ldarg.0
0x69681  ldstr    aReadchunksegme// "ReadChunkSegment"
0x69686  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.CancelableSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewCancelableStandardSqlCommand(string)
0x6968b  stloc.0
0x6968c  ldloc.0
0x6968d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x69692  ldstr    aChunkid// "@ChunkId"
0x69697  ldc.i4.s 0xE
0x69699  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6969e  ldarg.1
0x6969f  box      [mscorlib]System.Guid
0x696a4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x696a9  ldloc.0
0x696aa  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x696af  ldstr    aIspermanent// "@IsPermanent"
0x696b4  ldc.i4.2
0x696b5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x696ba  ldarg.2
0x696bb  box      [mscorlib]System.Boolean
0x696c0  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x696c5  ldloc.0
0x696c6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x696cb  ldstr    aSegmentid// "@SegmentId"
0x696d0  ldc.i4.s 0xE
0x696d2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x696d7  ldarg.3
0x696d8  box      [mscorlib]System.Guid
0x696dd  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x696e2  ldloc.0
0x696e3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x696e8  ldstr    aDataindex// "@DataIndex"
0x696ed  ldc.i4.8
0x696ee  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x696f3  ldarg.s  4
0x696f5  box      [mscorlib]System.Int32
0x696fa  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x696ff  ldloc.0
0x69700  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x69705  ldstr    aLength// "@Length"
0x6970a  ldc.i4.8
0x6970b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x69710  ldarg.s  7
0x69712  box      [mscorlib]System.Int32
0x69717  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6971c  ldloc.0
0x6971d  ldc.i4.s 0x10
0x6971f  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader(valuetype [System.Data]System.Data.CommandBehavior)
0x69724  stloc.1
0x69725  ldloc.1
0x69726  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x6972b  stloc.2
0x6972c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x69731  ldloc.2
0x69732  ldstr    aNoDataToRead// "no data to read"
0x69737  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6973c  ldloc.2
0x6973d  brfalse.s loc_6974F
0x6973f  ldloc.1
0x69740  ldc.i4.0
0x69741  ldc.i4.0
0x69742  conv.i8
0x69743  ldarg.s  5
0x69745  ldarg.s  6
0x69747  ldarg.s  7
0x69749  callvirt instance int64 [System.Data]System.Data.IDataRecord::GetBytes(int32, int64, unsigned int8[], int32, int32)
0x6974e  pop
0x6974f  leave.s  loc_69765
0x69751  ldloc.1
0x69752  brfalse.s loc_6975A
0x69754  ldloc.1
0x69755  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6975a  endfinally
0x6975b  ldloc.0
0x6975c  brfalse.s loc_69764
0x6975e  ldloc.0
0x6975f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69764  endfinally
0x69765  ret
```
