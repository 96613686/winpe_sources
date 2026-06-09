# Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.get_DatabaseName

- ea: `0x3010`
- end: `0x301c`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess.get_DatabaseName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2520`

## pseudocode

```c

```

## disassembly

```asm
0x3010  ldarg.0
0x3011  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.HostingEnvironment.Storage.ReferenceSqlAccess::_sqlAccess
0x3016  callvirt instance string Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::get_DatabaseName()
0x301b  ret
```
