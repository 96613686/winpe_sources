# Microsoft.BIServer.HostingEnvironment.Storage.ScopedSqlTransaction::Commit

- ea: `0x2d30`
- end: `0x2d3c`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.ScopedSqlTransaction::Commit`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2d30  ldarg.0
0x2d31  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.BIServer.HostingEnvironment.Storage.ScopedSqlTransaction::_transaction
0x2d36  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Commit()
0x2d3b  ret
```
