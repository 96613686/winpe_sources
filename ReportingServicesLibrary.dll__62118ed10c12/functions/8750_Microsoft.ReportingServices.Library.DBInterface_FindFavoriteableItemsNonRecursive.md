# Microsoft.ReportingServices.Library.DBInterface::FindFavoriteableItemsNonRecursive

- ea: `0x8750`
- end: `0x87ea`
- name: `Microsoft.ReportingServices.Library.DBInterface::FindFavoriteableItemsNonRecursive`
- size: `154`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x4630`
- `0x8750`
- `0x96b0`
- `0xf570`

## string_xrefs

- `0x87b8`: `@UserSid`
- `0x875e`: `@Path`

## pseudocode

```c

```

## disassembly

```asm
0x8750  ldarg.0
0x8751  ldstr    aFindfavoriteab_0// "FindFavoriteableItemsNonRecursive"
0x8756  ldnull
0x8757  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x875c  stloc.0
0x875d  ldloc.0
0x875e  ldstr    aPath// "@Path"
0x8763  ldc.i4.s 0xC
0x8765  ldarg.s  4
0x8767  ldarg.1
0x8768  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x876d  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator::ExternalToCatalog(string)
0x8772  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x8777  pop
0x8778  ldloc.0
0x8779  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x877e  ldstr    aAuthtype// "@AuthType"
0x8783  ldarg.0
0x8784  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x8789  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x878e  box      [mscorlib]System.Int32
0x8793  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8798  pop
0x8799  ldloc.0
0x879a  ldstr    aUsername_0// "@UserName"
0x879f  ldc.i4.s 0xC
0x87a1  ldarg.0
0x87a2  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x87a7  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x87ac  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x87b1  pop
0x87b2  ldloc.0
0x87b3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x87b8  ldstr    aUsersid// "@UserSid"
0x87bd  ldarg.0
0x87be  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x87c3  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x87c8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x87cd  pop
0x87ce  ldarg.0
0x87cf  ldloc.0
0x87d0  ldarg.2
0x87d1  ldarg.3
0x87d2  ldarg.s  4
0x87d4  ldarg.s  5
0x87d6  call     instance bool Microsoft.ReportingServices.Library.DBInterface::FindFavoriteableItems(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand command, [out] class Microsoft.ReportingServices.Library.FavoriteableCatalogItemList& result, class Microsoft.ReportingServices.Library.Security secMgr, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator pathTranslator, bool appendMyReports)
0x87db  stloc.1
0x87dc  leave.s  loc_87E8
0x87de  ldloc.0
0x87df  brfalse.s loc_87E7
0x87e1  ldloc.0
0x87e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x87e7  endfinally
0x87e8  ldloc.1
0x87e9  ret
```
