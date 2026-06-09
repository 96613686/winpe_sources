# Microsoft.SharePoint.Publishing.AddinPluginServerStub::IsSetPropertyBlocked

- ea: `0x850`
- end: `0x869`
- name: `Microsoft.SharePoint.Publishing.AddinPluginServerStub::IsSetPropertyBlocked`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x850`

## pseudocode

```c

```

## disassembly

```asm
0x850  ldarg.2
0x851  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Publishing.AddinPluginServerStub::s_targetTypeId
0x856  ldarg.1
0x857  callvirt instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::IsSetPropertyBlocked(valuetype [mscorlib]System.Guid, string)
0x85c  brfalse.s loc_860
0x85e  ldc.i4.1
0x85f  ret
0x860  ldarg.0
0x861  ldarg.1
0x862  ldarg.2
0x863  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::IsSetPropertyBlocked(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x868  ret
```
