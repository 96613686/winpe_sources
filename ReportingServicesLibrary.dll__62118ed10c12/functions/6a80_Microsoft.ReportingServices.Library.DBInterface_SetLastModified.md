# Microsoft.ReportingServices.Library.DBInterface::SetLastModified

- ea: `0x6a80`
- end: `0x6b24`
- name: `Microsoft.ReportingServices.Library.DBInterface::SetLastModified`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x4630`
- `0x6a80`
- `0xf560`

## string_xrefs

- `0x6a8e`: `@Path`
- `0x6aa7`: `@ModifiedBySid`

## pseudocode

```c

```

## disassembly

```asm
0x6a80  ldarg.0
0x6a81  ldstr    aSetlastmodifie// "SetLastModified"
0x6a86  ldnull
0x6a87  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x6a8c  stloc.0
0x6a8d  ldloc.0
0x6a8e  ldstr    aPath// "@Path"
0x6a93  ldc.i4.s 0xC
0x6a95  ldarg.1
0x6a96  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x6a9b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x6aa0  pop
0x6aa1  ldloc.0
0x6aa2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6aa7  ldstr    aModifiedbysid// "@ModifiedBySid"
0x6aac  ldarg.2
0x6aad  ldarg.0
0x6aae  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x6ab3  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x6ab8  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(string name, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType authType)
0x6abd  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6ac2  ldc.i4.s 0x15
0x6ac4  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x6ac9  ldloc.0
0x6aca  ldstr    aModifiedbyname// "@ModifiedByName"
0x6acf  ldc.i4.s 0xC
0x6ad1  ldarg.2
0x6ad2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x6ad7  pop
0x6ad8  ldloc.0
0x6ad9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6ade  ldstr    aAuthtype// "@AuthType"
0x6ae3  ldarg.0
0x6ae4  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x6ae9  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x6aee  box      [mscorlib]System.Int32
0x6af3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6af8  pop
0x6af9  ldloc.0
0x6afa  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6aff  ldstr    aModifieddate// "@ModifiedDate"
0x6b04  ldarg.3
0x6b05  box      [mscorlib]System.DateTime
0x6b0a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6b0f  pop
0x6b10  ldloc.0
0x6b11  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x6b16  pop
0x6b17  leave.s  loc_6B23
0x6b19  ldloc.0
0x6b1a  brfalse.s loc_6B22
0x6b1c  ldloc.0
0x6b1d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b22  endfinally
0x6b23  ret
```
