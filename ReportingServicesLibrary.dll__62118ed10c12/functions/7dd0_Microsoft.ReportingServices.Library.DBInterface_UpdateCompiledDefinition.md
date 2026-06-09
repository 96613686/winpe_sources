# Microsoft.ReportingServices.Library.DBInterface::UpdateCompiledDefinition

- ea: `0x7dd0`
- end: `0x7e97`
- name: `Microsoft.ReportingServices.Library.DBInterface::UpdateCompiledDefinition`
- size: `199`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2d860`
- `0x89440`

## callees

- `0x7dd0`

## string_xrefs

- `0x7de2`: `@Path`
- `0x7dd1`: `UpdateCompiledDefinition`

## pseudocode

```c

```

## disassembly

```asm
0x7dd0  ldarg.0
0x7dd1  ldstr    aUpdatecompiled// "UpdateCompiledDefinition"
0x7dd6  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.CancelableSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewCancelableStandardSqlCommand(string)
0x7ddb  stloc.0
0x7ddc  ldloc.0
0x7ddd  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7de2  ldstr    aPath// "@Path"
0x7de7  ldc.i4.s 0xC
0x7de9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7dee  ldarg.1
0x7def  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x7df4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7df9  ldloc.0
0x7dfa  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7dff  ldstr    aOldsnapshotid// "@OldSnapshotId"
0x7e04  ldc.i4.s 0xE
0x7e06  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7e0b  ldarg.2
0x7e0c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7e11  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7e16  brtrue.s loc_7E20
0x7e18  ldarg.2
0x7e19  box      [mscorlib]System.Guid
0x7e1e  br.s     loc_7E25
0x7e20  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x7e25  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7e2a  ldloc.0
0x7e2b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7e30  ldstr    aNewsnapshotid// "@NewSnapshotId"
0x7e35  ldc.i4.s 0xE
0x7e37  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7e3c  ldarg.3
0x7e3d  box      [mscorlib]System.Guid
0x7e42  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7e47  ldloc.0
0x7e48  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7e4d  ldstr    aItemid_1// "@ItemId"
0x7e52  ldc.i4.s 0xE
0x7e54  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7e59  stloc.1
0x7e5a  ldloc.1
0x7e5b  ldc.i4.2
0x7e5c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x7e61  ldloc.0
0x7e62  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x7e67  pop
0x7e68  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7e6d  stloc.2
0x7e6e  ldloc.1
0x7e6f  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x7e74  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x7e79  beq.s    loc_7E87
0x7e7b  ldloc.1
0x7e7c  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x7e81  unbox.any [mscorlib]System.Guid
0x7e86  stloc.2
0x7e87  ldloc.2
0x7e88  stloc.3
0x7e89  leave.s  loc_7E95
0x7e8b  ldloc.0
0x7e8c  brfalse.s loc_7E94
0x7e8e  ldloc.0
0x7e8f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7e94  endfinally
0x7e95  ldloc.3
0x7e96  ret
```
