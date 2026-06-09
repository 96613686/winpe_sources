# Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.ExecuteAsync_0

- ea: `0x2f30`
- end: `0x2f3e`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.ExecuteAsync_0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2440`

## pseudocode

```c

```

## disassembly

```asm
0x2f30  ldarg.0
0x2f31  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::_sqlAccess
0x2f36  ldarg.1
0x2f37  ldarg.2
0x2f38  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::ExecuteAsync(string storedProcedure, object parameters)
0x2f3d  ret
```
