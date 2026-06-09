# Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.ExecuteReaderAsync

- ea: `0x2fb0`
- end: `0x2fbf`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.ExecuteReaderAsync`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x24c0`

## pseudocode

```c

```

## disassembly

```asm
0x2fb0  ldarg.0
0x2fb1  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::_sqlAccess
0x2fb6  ldarg.1
0x2fb7  ldarg.2
0x2fb8  ldarg.3
0x2fb9  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Data]System.Data.Common.DbDataReader> Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::ExecuteReaderAsync(string storedProcedure, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> parameters, valuetype [System.Data]System.Data.CommandBehavior commandBehavior)
0x2fbe  ret
```
