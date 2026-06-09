# Microsoft.SharePoint.Publishing.AddinPluginServerStub::HasProperty

- ea: `0x5d0`
- end: `0x5ff`
- name: `Microsoft.SharePoint.Publishing.AddinPluginServerStub::HasProperty`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x5d0`

## pseudocode

```c

```

## disassembly

```asm
0x5d0  ldarg.2
0x5d1  brfalse.s loc_5E3
0x5d3  ldsfld   string[] Microsoft.SharePoint.Publishing.AddinPluginServerStub::s_valueProperties
0x5d8  ldarg.1
0x5d9  call     T0x2B000003
0x5de  ldc.i4.0
0x5df  blt.s    loc_5E3
0x5e1  ldc.i4.1
0x5e2  ret
0x5e3  ldarg.2
0x5e4  brtrue.s loc_5F6
0x5e6  ldsfld   string[] Microsoft.SharePoint.Publishing.AddinPluginServerStub::s_refProperties
0x5eb  ldarg.1
0x5ec  call     T0x2B000003
0x5f1  ldc.i4.0
0x5f2  blt.s    loc_5F6
0x5f4  ldc.i4.1
0x5f5  ret
0x5f6  ldarg.0
0x5f7  ldarg.1
0x5f8  ldarg.2
0x5f9  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::HasProperty(string, bool)
0x5fe  ret
```
