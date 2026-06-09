# Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::RemoveSetting

- ea: `0x4730`
- end: `0x4739`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::RemoveSetting`
- size: `9`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x43a0`
- `0x4740`

## pseudocode

```c

```

## disassembly

```asm
0x4730  ldarg.0
0x4731  ldarg.1
0x4732  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Remove(var<u1>)
0x4737  pop
0x4738  ret
```
