# Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.GetStringOrNullColumn

- ea: `0x2ff0`
- end: `0x2ffe`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.GetStringOrNullColumn`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2500`

## pseudocode

```c

```

## disassembly

```asm
0x2ff0  ldarg.0
0x2ff1  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::_sqlAccess
0x2ff6  ldarg.1
0x2ff7  ldarg.2
0x2ff8  callvirt instance string Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::GetStringOrNullColumn(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader results, int32 index)
0x2ffd  ret
```
