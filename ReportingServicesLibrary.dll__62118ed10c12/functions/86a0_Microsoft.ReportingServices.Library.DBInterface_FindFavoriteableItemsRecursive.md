# Microsoft.ReportingServices.Library.DBInterface::FindFavoriteableItemsRecursive

- ea: `0x86a0`
- end: `0x8749`
- name: `Microsoft.ReportingServices.Library.DBInterface::FindFavoriteableItemsRecursive`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x4630`
- `0x86a0`
- `0x96b0`
- `0xf570`

## string_xrefs

- `0x8717`: `@UserSid`
- `0x86ae`: `@Path`

## pseudocode

```c

```

## disassembly

```asm
0x86a0  ldarg.0
0x86a1  ldstr    aFindfavoriteab// "FindFavoriteableItemsRecursive"
0x86a6  ldnull
0x86a7  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x86ac  stloc.0
0x86ad  ldloc.0
0x86ae  ldstr    aPath// "@Path"
0x86b3  ldc.i4.s 0xC
0x86b5  ldarg.s  4
0x86b7  ldarg.1
0x86b8  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x86bd  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator::ExternalToCatalog(string)
0x86c2  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::EncodeForLike(string)
0x86c7  ldstr    asc_92514// "/%"
0x86cc  call     string [mscorlib]System.String::Concat(string, string)
0x86d1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x86d6  pop
0x86d7  ldloc.0
0x86d8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x86dd  ldstr    aAuthtype// "@AuthType"
0x86e2  ldarg.0
0x86e3  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x86e8  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x86ed  box      [mscorlib]System.Int32
0x86f2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x86f7  pop
0x86f8  ldloc.0
0x86f9  ldstr    aUsername_0// "@UserName"
0x86fe  ldc.i4.s 0xC
0x8700  ldarg.0
0x8701  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x8706  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x870b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x8710  pop
0x8711  ldloc.0
0x8712  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x8717  ldstr    aUsersid// "@UserSid"
0x871c  ldarg.0
0x871d  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x8722  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x8727  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x872c  pop
0x872d  ldarg.0
0x872e  ldloc.0
0x872f  ldarg.2
0x8730  ldarg.3
0x8731  ldarg.s  4
0x8733  ldarg.s  5
0x8735  call     instance bool Microsoft.ReportingServices.Library.DBInterface::FindFavoriteableItems(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand command, [out] class Microsoft.ReportingServices.Library.FavoriteableCatalogItemList& result, class Microsoft.ReportingServices.Library.Security secMgr, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator pathTranslator, bool appendMyReports)
0x873a  stloc.1
0x873b  leave.s  loc_8747
0x873d  ldloc.0
0x873e  brfalse.s loc_8746
0x8740  ldloc.0
0x8741  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8746  endfinally
0x8747  ldloc.1
0x8748  ret
```
