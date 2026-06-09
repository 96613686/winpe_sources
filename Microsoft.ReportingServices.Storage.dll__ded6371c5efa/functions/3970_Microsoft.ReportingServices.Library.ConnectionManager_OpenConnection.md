# Microsoft.ReportingServices.Library.ConnectionManager::OpenConnection

- ea: `0x3970`
- end: `0x3a38`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::OpenConnection`
- size: `200`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x3180`
- `0x3200`
- `0x3360`
- `0x33a0`

## callees

- `0x3930`
- `0x3950`
- `0x3970`
- `0x5a30`
- `0x7c50`

## pseudocode

```c

```

## disassembly

```asm
0x3970  ldnull
0x3971  stloc.0
0x3972  ldc.i4.1
0x3973  call     class [mscorlib]System.Security.Principal.WindowsIdentity [mscorlib]System.Security.Principal.WindowsIdentity::GetCurrent(bool)
0x3978  stloc.1
0x3979  ldloc.1
0x397a  brfalse.s loc_3999
0x397c  ldloc.1
0x397d  callvirt instance native int [mscorlib]System.Security.Principal.WindowsIdentity::get_Token()
0x3982  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3987  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x398c  brfalse.s loc_3999
0x398e  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3993  call     class [mscorlib]System.Security.Principal.WindowsImpersonationContext [mscorlib]System.Security.Principal.WindowsIdentity::Impersonate(native int)
0x3998  stloc.0
0x3999  ldarg.0
0x399a  call     instance bool Microsoft.ReportingServices.Library.ConnectionManager::get_ShouldImpersonateCatUser()
0x399f  brfalse.s loc_39B2
0x39a1  ldarg.0
0x39a2  ldfld    class Microsoft.ReportingServices.Library.ConnectionConfig Microsoft.ReportingServices.Library.ConnectionManager::_config
0x39a7  callvirt instance class [mscorlib]System.Security.Principal.WindowsImpersonationContext Microsoft.ReportingServices.Library.ConnectionConfig::ImpersonateCatUser()
0x39ac  stloc.2
0x39ad  ldloc.0
0x39ae  brtrue.s loc_39B2
0x39b0  ldloc.2
0x39b1  stloc.0
0x39b2  ldarg.0
0x39b3  ldarg.0
0x39b4  call     instance string Microsoft.ReportingServices.Library.ConnectionManager::get_ConnectionString()
0x39b9  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection::.ctor(string)
0x39be  stfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::_connection
0x39c3  ldarg.0
0x39c4  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::_connection
0x39c9  ldarg.0
0x39ca  ldftn    instance void Microsoft.ReportingServices.Library.ConnectionManager::ConnectionStateChange(object sender, class [System.Data]System.Data.StateChangeEventArgs e)
0x39d0  newobj   instance void [System.Data]System.Data.StateChangeEventHandler::.ctor(object, native int)
0x39d5  callvirt instance void [System.Data]System.Data.Common.DbConnection::add_StateChange(class [System.Data]System.Data.StateChangeEventHandler)
0x39da  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MeasureSql::.ctor()
0x39df  stloc.3
0x39e0  ldarg.0
0x39e1  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::_connection
0x39e6  callvirt instance void [System.Data]System.Data.Common.DbConnection::Open()
0x39eb  leave.s  loc_39F7
0x39ed  ldloc.3
0x39ee  brfalse.s loc_39F6
0x39f0  ldloc.3
0x39f1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x39f6  endfinally
0x39f7  ldarg.0
0x39f8  ldc.i4.1
0x39f9  stfld    bool Microsoft.ReportingServices.Library.ConnectionManager::_connectionWasOpened
0x39fe  leave.s  loc_3A26
0x3a00  newobj   instance void Microsoft.ReportingServices.Library.ReportServerDatabaseUnavailableException::.ctor(class [mscorlib]System.Exception innerSqlException)
0x3a05  throw
0x3a06  stloc.s  4
0x3a08  ldloc.s  4
0x3a0a  callvirt instance int32 [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlException::get_Number()
0x3a0f  ldc.i4   0xFDC
0x3a14  bne.un.s loc_3A1E
0x3a16  ldloc.s  4
0x3a18  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerDatabaseLogonFailedException::.ctor(class [mscorlib]System.Exception)
0x3a1d  throw
0x3a1e  ldloc.s  4
0x3a20  newobj   instance void Microsoft.ReportingServices.Library.ReportServerDatabaseUnavailableException::.ctor(class [mscorlib]System.Exception innerSqlException)
0x3a25  throw
0x3a26  leave.s  loc_3A32
0x3a28  ldloc.0
0x3a29  brfalse.s loc_3A31
0x3a2b  ldloc.0
0x3a2c  callvirt instance void [mscorlib]System.Security.Principal.WindowsImpersonationContext::Undo()
0x3a31  endfinally
0x3a32  leave.s  loc_3A37
0x3a34  pop
0x3a35  rethrow
0x3a37  ret
```
