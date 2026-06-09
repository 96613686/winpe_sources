# Microsoft.SharePoint.Publishing.AddinPluginServerStub::IsMethodBlocked

- ea: `0x810`
- end: `0x829`
- name: `Microsoft.SharePoint.Publishing.AddinPluginServerStub::IsMethodBlocked`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x810`

## pseudocode

```c

```

## disassembly

```asm
0x810  ldarg.2
0x811  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Publishing.AddinPluginServerStub::s_targetTypeId
0x816  ldarg.1
0x817  callvirt instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::IsMethodBlocked(valuetype [mscorlib]System.Guid, string)
0x81c  brfalse.s loc_820
0x81e  ldc.i4.1
0x81f  ret
0x820  ldarg.0
0x821  ldarg.1
0x822  ldarg.2
0x823  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::IsMethodBlocked(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x828  ret
```
