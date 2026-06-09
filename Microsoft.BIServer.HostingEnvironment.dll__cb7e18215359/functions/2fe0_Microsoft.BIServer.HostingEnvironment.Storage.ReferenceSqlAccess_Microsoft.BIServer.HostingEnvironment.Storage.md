# Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.ExecuteBatchScript_0

- ea: `0x2fe0`
- end: `0x2fee`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.ExecuteBatchScript_0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x24f0`

## pseudocode

```c

```

## disassembly

```asm
0x2fe0  ldarg.0
0x2fe1  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::_sqlAccess
0x2fe6  ldarg.1
0x2fe7  ldarg.2
0x2fe8  callvirt instance void Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::ExecuteBatchScript(string script, valuetype [mscorlib]System.TimeSpan individualCommandTimeout)
0x2fed  ret
```
