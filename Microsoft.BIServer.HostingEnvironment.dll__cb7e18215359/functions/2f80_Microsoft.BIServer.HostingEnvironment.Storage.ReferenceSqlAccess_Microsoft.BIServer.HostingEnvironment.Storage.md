# Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.ExecuteBatchScript

- ea: `0x2f80`
- end: `0x2f8d`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.ExecuteBatchScript`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2490`

## pseudocode

```c

```

## disassembly

```asm
0x2f80  ldarg.0
0x2f81  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::_sqlAccess
0x2f86  ldarg.1
0x2f87  callvirt instance void Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::ExecuteBatchScript(string script)
0x2f8c  ret
```
