# Microsoft.ReportingServices.Library.ConnectionManager::VerifyConnectionAndDbVersion

- ea: `0x33a0`
- end: `0x33d5`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::VerifyConnectionAndDbVersion`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x33a0`
- `0x33e0`
- `0x3910`
- `0x3930`
- `0x3970`
- `0x3a60`

## pseudocode

```c

```

## disassembly

```asm
0x33a0  ldarg.0
0x33a1  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::_connection
0x33a6  brfalse.s loc_33A9
0x33a8  ret
0x33a9  ldarg.0
0x33aa  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::PerformVerificationChecks()
0x33af  ldarg.0
0x33b0  call     instance string Microsoft.ReportingServices.Library.ConnectionManager::get_ConnectionString()
0x33b5  brtrue.s loc_33C2
0x33b7  ldstr    aStorageDoesNot// "Storage does not contain a connnection "...
0x33bc  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x33c1  throw
0x33c2  ldarg.0
0x33c3  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::OpenConnection()
0x33c8  ldarg.0
0x33c9  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::EnsureCorrectEdition()
0x33ce  ldarg.0
0x33cf  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::InitEncryption()
0x33d4  ret
```
