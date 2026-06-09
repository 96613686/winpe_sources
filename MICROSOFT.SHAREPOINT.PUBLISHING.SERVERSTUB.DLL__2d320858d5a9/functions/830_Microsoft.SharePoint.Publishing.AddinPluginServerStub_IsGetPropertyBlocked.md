# Microsoft.SharePoint.Publishing.AddinPluginServerStub::IsGetPropertyBlocked

- ea: `0x830`
- end: `0x849`
- name: `Microsoft.SharePoint.Publishing.AddinPluginServerStub::IsGetPropertyBlocked`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x830`

## pseudocode

```c

```

## disassembly

```asm
0x830  ldarg.2
0x831  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Publishing.AddinPluginServerStub::s_targetTypeId
0x836  ldarg.1
0x837  callvirt instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::IsGetPropertyBlocked(valuetype [mscorlib]System.Guid, string)
0x83c  brfalse.s loc_840
0x83e  ldc.i4.1
0x83f  ret
0x840  ldarg.0
0x841  ldarg.1
0x842  ldarg.2
0x843  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::IsGetPropertyBlocked(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x848  ret
```
