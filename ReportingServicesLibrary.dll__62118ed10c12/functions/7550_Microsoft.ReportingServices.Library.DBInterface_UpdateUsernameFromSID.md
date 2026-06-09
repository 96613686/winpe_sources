# Microsoft.ReportingServices.Library.DBInterface::UpdateUsernameFromSID

- ea: `0x7550`
- end: `0x75bd`
- name: `Microsoft.ReportingServices.Library.DBInterface::UpdateUsernameFromSID`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0xfe30`

## callees

- `0x7550`

## string_xrefs

- `0x7551`: `UpdateUsernameFromSID`
- `0x7589`: `Error in UpdateUsernameFromSID: {0}`
- `0x75a6`: `Error in UpdateUsernameFromSID: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7550  ldarg.0
0x7551  ldstr    aUpdateusername// "UpdateUsernameFromSID"
0x7556  ldnull
0x7557  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x755c  stloc.0
0x755d  ldloc.0
0x755e  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x7563  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_UserNameSIDRefreshSQLTimeout()
0x7568  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout(int32)
0x756d  ldloc.0
0x756e  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x7573  pop
0x7574  leave.s  loc_7580
0x7576  ldloc.0
0x7577  brfalse.s loc_757F
0x7579  ldloc.0
0x757a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x757f  endfinally
0x7580  leave.s  loc_75BC
0x7582  stloc.1
0x7583  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CleanupTracer()
0x7588  ldc.i4.1
0x7589  ldstr    aErrorInUpdateu// "Error in UpdateUsernameFromSID: {0}"
0x758e  ldc.i4.1
0x758f  newarr   [mscorlib]System.Object
0x7594  dup
0x7595  ldc.i4.0
0x7596  ldloc.1
0x7597  stelem.ref
0x7598  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x759d  leave.s  loc_75BC
0x759f  stloc.2
0x75a0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CleanupTracer()
0x75a5  ldc.i4.1
0x75a6  ldstr    aErrorInUpdateu// "Error in UpdateUsernameFromSID: {0}"
0x75ab  ldc.i4.1
0x75ac  newarr   [mscorlib]System.Object
0x75b1  dup
0x75b2  ldc.i4.0
0x75b3  ldloc.2
0x75b4  stelem.ref
0x75b5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x75ba  rethrow
0x75bc  ret
```
