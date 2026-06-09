# Microsoft.ReportingServices.Library.CachedSystemProperties::GetSystemProperty

- ea: `0x8e0`
- end: `0x957`
- name: `Microsoft.ReportingServices.Library.CachedSystemProperties::GetSystemProperty`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xa0`

## callees

- `0x8e0`
- `0x30f0`
- `0x32e0`
- `0x6a40`
- `0x6a50`
- `0x6a70`
- `0x6ae0`
- `0x6c00`
- `0x7190`
- `0x7360`

## string_xrefs

- `0x90a`: `GetOneConfigurationInfo`

## pseudocode

```c

```

## disassembly

```asm
0x8e0  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplicationHasCatalogAccess()
0x8e5  brfalse.s loc_944
0x8e7  newobj   instance void Microsoft.ReportingServices.Library.Storage::.ctor()
0x8ec  stloc.0
0x8ed  ldloc.0
0x8ee  ldc.i4.1
0x8ef  ldc.i4   0x1000
0x8f4  newobj   instance void Microsoft.ReportingServices.Library.ConnectionManager::.ctor(valuetype Microsoft.ReportingServices.Library.ConnectionTransactionType transactionType, valuetype [System.Data]System.Data.IsolationLevel defaultIsolationLevel)
0x8f9  callvirt instance void Microsoft.ReportingServices.Library.Storage::set_ConnectionManager(class Microsoft.ReportingServices.Library.ConnectionManager value)
0x8fe  ldloc.0
0x8ff  callvirt instance class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x904  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x909  ldloc.0
0x90a  ldstr    aGetoneconfigur// "GetOneConfigurationInfo"
0x90f  ldnull
0x910  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string storedProcedureName, [opt] class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection connection)
0x915  stloc.1
0x916  ldloc.1
0x917  ldstr    aName// "@Name"
0x91c  ldc.i4.s 0xC
0x91e  ldarg.0
0x91f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string paramName, valuetype [System.Data]System.Data.SqlDbType type, object val)
0x924  pop
0x925  ldloc.1
0x926  callvirt instance object Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteScalar()
0x92b  castclass [mscorlib]System.String
0x930  stloc.2
0x931  leave.s  loc_955
0x933  ldloc.1
0x934  brfalse.s loc_93C
0x936  ldloc.1
0x937  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x93c  endfinally
0x93d  ldloc.0
0x93e  callvirt instance void Microsoft.ReportingServices.Library.Storage::DisconnectStorage()
0x943  endfinally
0x944  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x949  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_Settings()
0x94e  ldarg.0
0x94f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x954  ret
0x955  ldloc.2
0x956  ret
```
