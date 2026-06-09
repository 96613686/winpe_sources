# Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter

- ea: `0x7360`
- end: `0x7375`
- name: `Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter`
- size: `21`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8e0`
- `0x2580`
- `0x2710`
- `0x27a0`
- `0x27f0`
- `0x6e10`

## callees

- `0x7320`

## pseudocode

```c

```

## disassembly

```asm
0x7360  ldarg.0
0x7361  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7366  ldarg.1
0x7367  ldarg.2
0x7368  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x736d  dup
0x736e  ldarg.3
0x736f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7374  ret
```
