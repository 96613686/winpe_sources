# Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.PrepareStoredProcedure

- ea: `0x2fc0`
- end: `0x2fce`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.PrepareStoredProcedure`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x24d0`

## pseudocode

```c

```

## disassembly

```asm
0x2fc0  ldarg.0
0x2fc1  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::_sqlAccess
0x2fc6  ldarg.1
0x2fc7  ldarg.2
0x2fc8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::PrepareStoredProcedure(string storedProcedureName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> parameters)
0x2fcd  ret
```
