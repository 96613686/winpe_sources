# Microsoft.ReportingServices.Library.DBInterface::RemoveFromFavorites

- ea: `0x4970`
- end: `0x4a3c`
- name: `Microsoft.ReportingServices.Library.DBInterface::RemoveFromFavorites`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x4630`
- `0x4970`
- `0xf570`

## string_xrefs

- `0x49a9`: `@UserSid`
- `0x4971`: `RemoveItemFromFavorites`

## pseudocode

```c

```

## disassembly

```asm
0x4970  ldarg.0
0x4971  ldstr    aRemoveitemfrom// "RemoveItemFromFavorites"
0x4976  ldnull
0x4977  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x497c  stloc.0
0x497d  ldloc.0
0x497e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4983  ldstr    aItemid_0// "@ItemID"
0x4988  ldarg.2
0x4989  box      [mscorlib]System.Guid
0x498e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4993  pop
0x4994  ldloc.0
0x4995  ldstr    aUsername_0// "@UserName"
0x499a  ldc.i4.s 0xC
0x499c  ldarg.1
0x499d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x49a2  pop
0x49a3  ldloc.0
0x49a4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x49a9  ldstr    aUsersid// "@UserSid"
0x49ae  ldarg.0
0x49af  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x49b4  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x49b9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x49be  pop
0x49bf  ldloc.0
0x49c0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x49c5  ldstr    aAuthtype// "@AuthType"
0x49ca  ldarg.0
0x49cb  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x49d0  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x49d5  box      [mscorlib]System.Int32
0x49da  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x49df  ldc.i4.8
0x49e0  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x49e5  ldloc.0
0x49e6  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x49eb  ldc.i4.0
0x49ec  cgt
0x49ee  stloc.1
0x49ef  leave.s  loc_4A3A
0x49f1  ldloc.0
0x49f2  brfalse.s loc_49FA
0x49f4  ldloc.0
0x49f5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x49fa  endfinally
0x49fb  stloc.2
0x49fc  ldloc.2
0x49fd  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_IsSqlException()
0x4a02  brtrue.s loc_4A06
0x4a04  rethrow
0x4a06  ldloc.2
0x4a07  callvirt instance int32 [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorNumber()
0x4a0c  ldsfld   int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Native::SqlConstraintViolationCode
0x4a11  beq.s    loc_4A20
0x4a13  ldloc.2
0x4a14  callvirt instance int32 [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorNumber()
0x4a19  ldsfld   int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Native::SqlUniqueIndexViolationCode
0x4a1e  bne.un.s loc_4A38
0x4a20  ldarga.s 2
0x4a22  constrained. [mscorlib]System.Guid
0x4a28  callvirt instance string [mscorlib]System.Object::ToString()
0x4a2d  ldstr    aCatalogitem// "CatalogItem"
0x4a32  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemNotFoundException::.ctor(string, string)
0x4a37  throw
0x4a38  rethrow
0x4a3a  ldloc.1
0x4a3b  ret
```
