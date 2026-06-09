# Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.ExecuteAsync

- ea: `0x2f20`
- end: `0x2f2d`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.ExecuteAsync`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2430`

## pseudocode

```c

```

## disassembly

```asm
0x2f20  ldarg.0
0x2f21  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::_sqlAccess
0x2f26  ldarg.1
0x2f27  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::ExecuteAsync(string storedProcedure)
0x2f2c  ret
```
