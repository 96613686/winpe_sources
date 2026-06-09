# Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::Create_MethodProxy_0

- ea: `0x22e0`
- end: `0x22f7`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::Create_MethodProxy_0`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2320`

## pseudocode

```c

```

## disassembly

```asm
0x22e0  ldarg.1
0x22e1  ldc.i4.0
0x22e2  call     class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetArgument(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, int32)
0x22e7  stloc.0
0x22e8  ldloc.0
0x22e9  callvirt T0x2B00000D
0x22ee  stloc.1
0x22ef  ldarg.0
0x22f0  ldloc.1
0x22f1  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSite::Create(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest)
0x22f6  ret
```
