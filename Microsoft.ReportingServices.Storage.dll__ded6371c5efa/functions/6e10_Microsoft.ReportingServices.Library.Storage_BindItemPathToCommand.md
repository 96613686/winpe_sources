# Microsoft.ReportingServices.Library.Storage::BindItemPathToCommand

- ea: `0x6e10`
- end: `0x6ea7`
- name: `Microsoft.ReportingServices.Library.Storage::BindItemPathToCommand`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x3fa0`
- `0x6e10`
- `0x7320`
- `0x7360`

## string_xrefs

- `0x6e11`: `@Path`
- `0x6e32`: `attempt to use edit session on unsupporteded method`
- `0x6e70`: `@OwnerSid`

## pseudocode

```c

```

## disassembly

```asm
0x6e10  ldarg.1
0x6e11  ldstr    aPath_0// "@Path"
0x6e16  ldc.i4.s 0xC
0x6e18  ldarg.0
0x6e19  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x6e1e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string paramName, valuetype [System.Data]System.Data.SqlDbType type, object val)
0x6e23  pop
0x6e24  ldarg.0
0x6e25  callvirt instance bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_IsEditSession()
0x6e2a  brfalse.s loc_6EA6
0x6e2c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x6e31  ldarg.2
0x6e32  ldstr    aAttemptToUseEd// "attempt to use edit session on unsuppor"...
0x6e37  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6e3c  ldarg.1
0x6e3d  ldstr    aEditsessionid// "@EditSessionID"
0x6e42  ldc.i4.s 0x16
0x6e44  ldarg.0
0x6e45  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_EditSessionID()
0x6e4a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string paramName, valuetype [System.Data]System.Data.SqlDbType type, object val)
0x6e4f  pop
0x6e50  ldarg.3
0x6e51  brfalse.s loc_6EA6
0x6e53  ldnull
0x6e54  stloc.0
0x6e55  ldarg.3
0x6e56  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x6e5b  ldc.i4.1
0x6e5c  bne.un.s loc_6E6A
0x6e5e  ldarg.3
0x6e5f  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x6e64  call     unsigned int8[] Microsoft.ReportingServices.Library.Native::NameToSid(string name)
0x6e69  stloc.0
0x6e6a  ldarg.1
0x6e6b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6e70  ldstr    aOwnersid// "@OwnerSid"
0x6e75  ldc.i4.s 0x15
0x6e77  ldc.i4.s 0x55
0x6e79  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6e7e  ldloc.0
0x6e7f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6e84  ldarg.1
0x6e85  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6e8a  ldstr    aOwnername// "@OwnerName"
0x6e8f  ldc.i4.s 0xC
0x6e91  ldc.i4   0x104
0x6e96  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6e9b  ldarg.3
0x6e9c  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x6ea1  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6ea6  ret
```
