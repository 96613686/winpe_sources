# Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.PrepareStoredProcedure_0

- ea: `0x2fd0`
- end: `0x2fdd`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.PrepareStoredProcedure_0`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x24e0`

## pseudocode

```c

```

## disassembly

```asm
0x2fd0  ldarg.0
0x2fd1  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::_sqlAccess
0x2fd6  ldarg.1
0x2fd7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::PrepareStoredProcedure(string storedProcedureName)
0x2fdc  ret
```
