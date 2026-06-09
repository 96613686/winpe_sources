# Microsoft.ReportingServices.Library.ConnectionManager::EnsureCorrectEdition

- ea: `0x3a60`
- end: `0x3a80`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::EnsureCorrectEdition`
- size: `32`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3210`
- `0x3360`
- `0x33a0`

## callees

- `0x3930`
- `0x3a60`

## pseudocode

```c

```

## disassembly

```asm
0x3a60  ldsfld   valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SqlServerSkuType Microsoft.ReportingServices.Library.ConnectionManager::_edition
0x3a65  brfalse.s loc_3A68
0x3a67  ret
0x3a68  ldarg.0
0x3a69  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::_connection
0x3a6e  ldarg.0
0x3a6f  call     instance string Microsoft.ReportingServices.Library.ConnectionManager::get_ConnectionString()
0x3a74  ldc.i4.1
0x3a75  call     valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SqlServerSkuType [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Sku::EnsureCorrectEdition(class [System.Data]System.Data.IDbConnection, string, bool)
0x3a7a  stsfld   valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SqlServerSkuType Microsoft.ReportingServices.Library.ConnectionManager::_edition
0x3a7f  ret
```
