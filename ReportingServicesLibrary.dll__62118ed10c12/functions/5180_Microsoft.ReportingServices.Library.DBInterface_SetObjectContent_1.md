# Microsoft.ReportingServices.Library.DBInterface::SetObjectContent_1

- ea: `0x5180`
- end: `0x52d6`
- name: `Microsoft.ReportingServices.Library.DBInterface::SetObjectContent_1`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5160`

## callees

- `0x5180`

## string_xrefs

- `0x5236`: `@LinkSourceID`
- `0x52aa`: `@ComponentID`
- `0x5266`: `@DataCacheHash`

## pseudocode

```c

```

## disassembly

```asm
0x5180  ldarg.0
0x5181  ldstr    aSetobjectconte// "SetObjectContent"
0x5186  ldnull
0x5187  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x518c  stloc.0
0x518d  ldarg.1
0x518e  ldloc.0
0x518f  ldc.i4.1
0x5190  ldnull
0x5191  call     void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::BindItemPathToCommand(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath, class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand, bool, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext)
0x5196  ldarg.1
0x5197  callvirt instance bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_IsEditSession()
0x519c  brfalse.s loc_51B1
0x519e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x51a3  ldarg.2
0x51a4  ldc.i4.2
0x51a5  ceq
0x51a7  ldstr    aObjecttypeRepo// "objectType == Report"
0x51ac  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x51b1  ldloc.0
0x51b2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x51b7  ldstr    aType// "@Type"
0x51bc  ldarg.2
0x51bd  box      [mscorlib]System.Int32
0x51c2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x51c7  pop
0x51c8  ldarg.3
0x51c9  brfalse.s loc_51E2
0x51cb  ldloc.0
0x51cc  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x51d1  ldstr    aContent_0// "@Content"
0x51d6  ldc.i4.7
0x51d7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x51dc  ldarg.3
0x51dd  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x51e2  ldarg.s  4
0x51e4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x51e9  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x51ee  brfalse.s loc_520E
0x51f0  ldloc.0
0x51f1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x51f6  ldstr    aIntermediate// "@Intermediate"
0x51fb  ldc.i4.s 0xE
0x51fd  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5202  ldarg.s  4
0x5204  box      [mscorlib]System.Guid
0x5209  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x520e  ldarg.s  5
0x5210  brfalse.s loc_5222
0x5212  ldloc.0
0x5213  ldstr    aParameter// "@Parameter"
0x5218  ldc.i4.s 0xB
0x521a  ldarg.s  5
0x521c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x5221  pop
0x5222  ldarg.s  6
0x5224  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5229  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x522e  brfalse.s loc_5248
0x5230  ldloc.0
0x5231  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5236  ldstr    aLinksourceid// "@LinkSourceID"
0x523b  ldarg.s  6
0x523d  box      [mscorlib]System.Guid
0x5242  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5247  pop
0x5248  ldarg.s  7
0x524a  brfalse.s loc_525C
0x524c  ldloc.0
0x524d  ldstr    aMimetype// "@MimeType"
0x5252  ldc.i4.s 0xC
0x5254  ldarg.s  7
0x5256  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x525b  pop
0x525c  ldarg.s  8
0x525e  brfalse.s loc_5279
0x5260  ldloc.0
0x5261  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5266  ldstr    aDatacachehash// "@DataCacheHash"
0x526b  ldc.i4.s 0x15
0x526d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5272  ldarg.s  8
0x5274  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5279  ldarg.s  9
0x527b  brfalse.s loc_5296
0x527d  ldloc.0
0x527e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5283  ldstr    aSubtype// "@SubType"
0x5288  ldc.i4.s 0xC
0x528a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x528f  ldarg.s  9
0x5291  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5296  ldarg.s  0xA
0x5298  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x529d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x52a2  brfalse.s loc_52C2
0x52a4  ldloc.0
0x52a5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x52aa  ldstr    aComponentid// "@ComponentID"
0x52af  ldc.i4.s 0xE
0x52b1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x52b6  ldarg.s  0xA
0x52b8  box      [mscorlib]System.Guid
0x52bd  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x52c2  ldloc.0
0x52c3  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x52c8  pop
0x52c9  leave.s  loc_52D5
0x52cb  ldloc.0
0x52cc  brfalse.s loc_52D4
0x52ce  ldloc.0
0x52cf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x52d4  endfinally
0x52d5  ret
```
