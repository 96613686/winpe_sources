# Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters

- ea: `0x7320`
- end: `0x732c`
- name: `Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters`
- size: `12`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1230`
- `0x1d70`
- `0x20b0`
- `0x2860`
- `0x28c0`
- `0x2ba0`
- `0x2c10`
- `0x2c60`
- `0x2ca0`
- `0x2d40`
- `0x6240`
- `0x62e0`
- `0x63e0`
- `0x6750`
- `0x68b0`
- `0x6970`
- `0x6e10`
- `0x7360`

## callees

- `0x6f60`

## pseudocode

```c

```

## disassembly

```asm
0x7320  ldarg.0
0x7321  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::get_Command()
0x7326  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x732b  ret
```
