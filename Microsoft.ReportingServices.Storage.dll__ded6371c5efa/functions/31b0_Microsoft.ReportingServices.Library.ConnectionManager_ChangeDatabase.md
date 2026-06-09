# Microsoft.ReportingServices.Library.ConnectionManager::ChangeDatabase

- ea: `0x31b0`
- end: `0x31f2`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::ChangeDatabase`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1230`
- `0x17c0`

## callees

- `0x3170`
- `0x31b0`
- `0x6dd0`

## pseudocode

```c

```

## disassembly

```asm
0x31b0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x31b5  ldarg.1
0x31b6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x31bb  ldc.i4.0
0x31bc  ceq
0x31be  ldstr    aStringIsnullor// "!String.IsNullOrEmpty(database)"
0x31c3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x31c8  ldarg.0
0x31c9  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::get_Connection()
0x31ce  callvirt instance string [System.Data]System.Data.Common.DbConnection::get_Database()
0x31d3  ldarg.1
0x31d4  ldc.i4.5
0x31d5  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x31da  brtrue.s loc_31E8
0x31dc  ldarg.0
0x31dd  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::get_Connection()
0x31e2  ldarg.1
0x31e3  callvirt instance void [System.Data]System.Data.Common.DbConnection::ChangeDatabase(string)
0x31e8  leave.s  loc_31F1
0x31ea  call     void Microsoft.ReportingServices.Library.Storage::WrapAndThrowKnownExceptionTypes(class [mscorlib]System.Exception e)
0x31ef  rethrow
0x31f1  ret
```
