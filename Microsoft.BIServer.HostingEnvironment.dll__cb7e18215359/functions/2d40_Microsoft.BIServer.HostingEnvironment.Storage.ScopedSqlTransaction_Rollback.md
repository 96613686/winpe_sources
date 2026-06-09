# Microsoft.BIServer.HostingEnvironment.Storage.ScopedSqlTransaction::Rollback

- ea: `0x2d40`
- end: `0x2d4c`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.ScopedSqlTransaction::Rollback`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2d40  ldarg.0
0x2d41  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.BIServer.HostingEnvironment.Storage.ScopedSqlTransaction::_transaction
0x2d46  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Rollback()
0x2d4b  ret
```
