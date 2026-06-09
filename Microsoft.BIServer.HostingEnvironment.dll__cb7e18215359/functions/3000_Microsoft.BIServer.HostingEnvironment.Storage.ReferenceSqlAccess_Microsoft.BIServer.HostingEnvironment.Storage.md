# Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.GetBinaryOrNullColumn

- ea: `0x3000`
- end: `0x300e`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.GetBinaryOrNullColumn`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2510`

## pseudocode

```c

```

## disassembly

```asm
0x3000  ldarg.0
0x3001  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::_sqlAccess
0x3006  ldarg.1
0x3007  ldarg.2
0x3008  callvirt instance unsigned int8[] Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::GetBinaryOrNullColumn(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader results, int32 index)
0x300d  ret
```
