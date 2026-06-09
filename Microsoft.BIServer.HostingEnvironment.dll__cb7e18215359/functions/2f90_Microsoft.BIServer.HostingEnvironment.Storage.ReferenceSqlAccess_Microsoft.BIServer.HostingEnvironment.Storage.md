# Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.ExecuteNonQuery

- ea: `0x2f90`
- end: `0x2f9e`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.ExecuteNonQuery`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x24a0`

## pseudocode

```c

```

## disassembly

```asm
0x2f90  ldarg.0
0x2f91  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::_sqlAccess
0x2f96  ldarg.1
0x2f97  ldarg.2
0x2f98  callvirt instance void Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::ExecuteNonQuery(string statement, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> parameters)
0x2f9d  ret
```
