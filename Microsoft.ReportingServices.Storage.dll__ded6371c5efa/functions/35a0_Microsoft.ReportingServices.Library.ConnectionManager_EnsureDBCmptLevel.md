# Microsoft.ReportingServices.Library.ConnectionManager::EnsureDBCmptLevel

- ea: `0x35a0`
- end: `0x364b`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::EnsureDBCmptLevel`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x2ff0`
- `0x3170`
- `0x32d0`
- `0x35a0`
- `0x3650`
- `0x70d0`
- `0x70e0`
- `0x72f0`
- `0x7310`

## string_xrefs

- `0x35cf`: `TempDB`
- `0x362f`: `Failed set DB compatibility level: `

## pseudocode

```c

```

## disassembly

```asm
0x35a0  ldarg.0
0x35a1  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x35a6  stloc.0
0x35a7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x35ac  ldarg.0
0x35ad  ldfld    string Microsoft.ReportingServices.Library.ConnectionManager::dbcmptScriptsTemplate
0x35b2  ldarg.0
0x35b3  ldarg.0
0x35b4  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::get_Connection()
0x35b9  callvirt instance string [System.Data]System.Data.Common.DbConnection::get_Database()
0x35be  call     instance string Microsoft.ReportingServices.Library.ConnectionManager::EscapeAndBracketDBName(string dbName)
0x35c3  ldarg.0
0x35c4  ldarg.0
0x35c5  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::get_Connection()
0x35ca  callvirt instance string [System.Data]System.Data.Common.DbConnection::get_Database()
0x35cf  ldstr    aTempdb// "TempDB"
0x35d4  call     string [mscorlib]System.String::Concat(string, string)
0x35d9  call     instance string Microsoft.ReportingServices.Library.ConnectionManager::EscapeAndBracketDBName(string dbName)
0x35de  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x35e3  ldarg.0
0x35e4  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::_connection
0x35e9  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x35ee  ldloc.0
0x35ef  call     class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand command, class [mscorlib]System.IDisposable connectionLockContext)
0x35f4  stloc.1
0x35f5  ldloc.1
0x35f6  ldc.i4.1
0x35f7  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType value)
0x35fc  ldloc.1
0x35fd  call     int32 Microsoft.ReportingServices.Library.ConnectionManager::get_SqlCommandTimeoutSeconds()
0x3602  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout(int32 value)
0x3607  ldloc.1
0x3608  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x360d  pop
0x360e  leave.s  loc_361A
0x3610  ldloc.1
0x3611  brfalse.s loc_3619
0x3613  ldloc.1
0x3614  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3619  endfinally
0x361a  leave.s  loc_3626
0x361c  ldloc.0
0x361d  brfalse.s loc_3625
0x361f  ldloc.0
0x3620  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3625  endfinally
0x3626  leave.s  loc_364A
0x3628  stloc.2
0x3629  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x362e  ldc.i4.1
0x362f  ldstr    aFailedSetDbCom// "Failed set DB compatibility level: "
0x3634  ldc.i4.1
0x3635  newarr   [mscorlib]System.Object
0x363a  dup
0x363b  ldc.i4.0
0x363c  ldloc.2
0x363d  callvirt instance string [mscorlib]System.Object::ToString()
0x3642  stelem.ref
0x3643  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x3648  rethrow
0x364a  ret
```
