# Microsoft.ReportingServices.Library.ConnectionManager::VerifyConnection

- ea: `0x3360`
- end: `0x3398`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::VerifyConnection`
- size: `56`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x3140`
- `0x3170`

## callees

- `0x3360`
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
0x3360  ldarg.0
0x3361  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::_connection
0x3366  brfalse.s loc_3369
0x3368  ret
0x3369  ldarg.0
0x336a  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::PerformVerificationChecks()
0x336f  ldarg.0
0x3370  call     instance string Microsoft.ReportingServices.Library.ConnectionManager::get_ConnectionString()
0x3375  brtrue.s loc_3382
0x3377  ldstr    aStorageDoesNot// "Storage does not contain a connnection "...
0x337c  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x3381  throw
0x3382  ldarg.0
0x3383  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::OpenConnection()
0x3388  ldarg.0
0x3389  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::EnsureCorrectEdition()
0x338e  ldarg.1
0x338f  brfalse.s loc_3397
0x3391  ldarg.0
0x3392  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::InitEncryption()
0x3397  ret
```
