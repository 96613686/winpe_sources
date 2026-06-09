# Microsoft.ReportingServices.Library.DBInterface::FindObjectsByLink

- ea: `0x88e0`
- end: `0x8948`
- name: `Microsoft.ReportingServices.Library.DBInterface::FindObjectsByLink`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x4630`
- `0x88e0`
- `0x9470`
- `0x9660`

## string_xrefs

- `0x88ec`: `FindObjectsByLink`
- `0x88fe`: `@Link`

## pseudocode

```c

```

## disassembly

```asm
0x88e0  ldarg.0
0x88e1  ldarg.s  4
0x88e3  ldarg.3
0x88e4  ldc.i4.0
0x88e5  callvirt instance class Microsoft.ReportingServices.Library.ICatalogItemDescriptorFactory Microsoft.ReportingServices.Library.DBInterface::CreateDescriptorFactory(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator pathTranslator, class Microsoft.ReportingServices.Library.Security secMgr, valuetype Microsoft.ReportingServices.Library.ItemDescriptorOptions options)
0x88ea  stloc.0
0x88eb  ldarg.0
0x88ec  ldstr    aFindobjectsbyl// "FindObjectsByLink"
0x88f1  ldnull
0x88f2  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x88f7  stloc.1
0x88f8  ldloc.1
0x88f9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x88fe  ldstr    aLink_0// "@Link"
0x8903  ldarg.1
0x8904  box      [mscorlib]System.Guid
0x8909  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x890e  pop
0x890f  ldloc.1
0x8910  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x8915  ldstr    aAuthtype// "@AuthType"
0x891a  ldarg.0
0x891b  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x8920  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x8925  box      [mscorlib]System.Int32
0x892a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x892f  pop
0x8930  ldarg.0
0x8931  ldloc.1
0x8932  ldarg.2
0x8933  ldloc.0
0x8934  call     instance bool Microsoft.ReportingServices.Library.DBInterface::FindObjects(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand command, [out] class Microsoft.ReportingServices.Library.CatalogItemList& result, class Microsoft.ReportingServices.Library.ICatalogItemDescriptorFactory descriptorFactory)
0x8939  stloc.2
0x893a  leave.s  loc_8946
0x893c  ldloc.1
0x893d  brfalse.s loc_8945
0x893f  ldloc.1
0x8940  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8945  endfinally
0x8946  ldloc.2
0x8947  ret
```
