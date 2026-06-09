# Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::IsGetPropertyBlocked

- ea: `0x22a0`
- end: `0x22b9`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::IsGetPropertyBlocked`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x22a0`

## pseudocode

```c

```

## disassembly

```asm
0x22a0  ldarg.2
0x22a1  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::s_targetTypeId
0x22a6  ldarg.1
0x22a7  callvirt instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::IsGetPropertyBlocked(valuetype [mscorlib]System.Guid, string)
0x22ac  brfalse.s loc_22B0
0x22ae  ldc.i4.1
0x22af  ret
0x22b0  ldarg.0
0x22b1  ldarg.1
0x22b2  ldarg.2
0x22b3  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::IsGetPropertyBlocked(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x22b8  ret
```
