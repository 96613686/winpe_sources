# Microsoft.ReportingServices.Library.ConnectionManager::get_UnverifiedConnection

- ea: `0x3180`
- end: `0x31ae`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::get_UnverifiedConnection`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x6a90`

## callees

- `0x3180`
- `0x3910`
- `0x3930`
- `0x3970`

## pseudocode

```c

```

## disassembly

```asm
0x3180  ldarg.0
0x3181  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::_connection
0x3186  brtrue.s loc_31A7
0x3188  ldarg.0
0x3189  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::PerformVerificationChecks()
0x318e  ldarg.0
0x318f  call     instance string Microsoft.ReportingServices.Library.ConnectionManager::get_ConnectionString()
0x3194  brtrue.s loc_31A1
0x3196  ldstr    aStorageDoesNot// "Storage does not contain a connnection "...
0x319b  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x31a0  throw
0x31a1  ldarg.0
0x31a2  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::OpenConnection()
0x31a7  ldarg.0
0x31a8  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::_connection
0x31ad  ret
```
