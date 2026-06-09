# Microsoft.ReportingServices.Library.DBInterface::MoveObject

- ea: `0x4ff0`
- end: `0x513f`
- name: `Microsoft.ReportingServices.Library.DBInterface::MoveObject`
- size: `335`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x4ff0`

## string_xrefs

- `0x4fff`: `MoveObject`
- `0x5011`: `@OldPath`
- `0x5068`: `@NewPath`
- `0x509e`: `@RenameOnly`
- `0x50bb`: `@MaxPathLength`

## pseudocode

```c

```

## disassembly

```asm
0x4ff0  ldarg.1
0x4ff1  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x4ff6  stloc.0
0x4ff7  ldarg.3
0x4ff8  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x4ffd  stloc.1
0x4ffe  ldarg.0
0x4fff  ldstr    aMoveobject// "MoveObject"
0x5004  ldnull
0x5005  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x500a  stloc.2
0x500b  ldloc.2
0x500c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5011  ldstr    aOldpath// "@OldPath"
0x5016  ldloc.0
0x5017  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x501c  ldc.i4.s 0xC
0x501e  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x5023  ldloc.2
0x5024  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5029  ldstr    aOldprefix// "@OldPrefix"
0x502e  ldloc.0
0x502f  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::EncodeForLike(string)
0x5034  ldstr    asc_92514// "/%"
0x5039  call     string [mscorlib]System.String::Concat(string, string)
0x503e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5043  ldc.i4.s 0xC
0x5045  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x504a  ldloc.2
0x504b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5050  ldstr    aNewname// "@NewName"
0x5055  ldarg.2
0x5056  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x505b  ldc.i4.s 0xC
0x505d  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x5062  ldloc.2
0x5063  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5068  ldstr    aNewpath// "@NewPath"
0x506d  ldloc.1
0x506e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5073  ldc.i4.s 0xC
0x5075  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x507a  ldloc.2
0x507b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5080  ldstr    aNewparentid// "@NewParentID"
0x5085  ldarg.s  4
0x5087  box      [mscorlib]System.Guid
0x508c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5091  ldc.i4.s 0xE
0x5093  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x5098  ldloc.2
0x5099  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x509e  ldstr    aRenameonly// "@RenameOnly"
0x50a3  ldarg.s  5
0x50a5  box      [mscorlib]System.Boolean
0x50aa  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x50af  ldc.i4.2
0x50b0  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x50b5  ldloc.2
0x50b6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x50bb  ldstr    aMaxpathlength// "@MaxPathLength"
0x50c0  ldc.i4.8
0x50c1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x50c6  call     int32 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::get_MaxItemPathLength()
0x50cb  box      [mscorlib]System.Int32
0x50d0  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x50d5  ldloc.2
0x50d6  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x50db  stloc.3
0x50dc  ldloc.3
0x50dd  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x50e2  brfalse.s loc_5106
0x50e4  ldloc.3
0x50e5  ldc.i4.0
0x50e6  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x50eb  stloc.s  4
0x50ed  ldloc.1
0x50ee  ldloc.s  4
0x50f0  ldloc.0
0x50f1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x50f6  callvirt instance string [mscorlib]System.String::Substring(int32)
0x50fb  call     string [mscorlib]System.String::Concat(string, string)
0x5100  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemPathLengthExceededException::.ctor(string)
0x5105  throw
0x5106  ldc.i4.1
0x5107  stloc.s  5
0x5109  leave.s  loc_513C
0x510b  ldloc.3
0x510c  brfalse.s loc_5114
0x510e  ldloc.3
0x510f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5114  endfinally
0x5115  dup
0x5116  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_IsSqlException()
0x511b  brtrue.s loc_511F
0x511d  rethrow
0x511f  callvirt instance int32 [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorNumber()
0x5124  ldsfld   int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Native::SqlUniqueIndexViolationCode
0x5129  bne.un.s loc_5130
0x512b  ldc.i4.0
0x512c  stloc.s  5
0x512e  leave.s  loc_513C
0x5130  rethrow
0x5132  ldloc.2
0x5133  brfalse.s loc_513B
0x5135  ldloc.2
0x5136  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x513b  endfinally
0x513c  ldloc.s  5
0x513e  ret
```
