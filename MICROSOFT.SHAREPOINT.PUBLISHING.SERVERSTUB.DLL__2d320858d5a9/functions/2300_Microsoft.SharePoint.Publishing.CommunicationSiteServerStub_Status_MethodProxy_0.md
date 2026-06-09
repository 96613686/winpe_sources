# Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::Status_MethodProxy_0

- ea: `0x2300`
- end: `0x2317`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::Status_MethodProxy_0`
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
0x2300  ldarg.1
0x2301  ldc.i4.0
0x2302  call     class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetArgument(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, int32)
0x2307  stloc.0
0x2308  ldloc.0
0x2309  callvirt T0x2B000001
0x230e  stloc.1
0x230f  ldarg.0
0x2310  ldloc.1
0x2311  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSite::GetSiteStatus(string)
0x2316  ret
```
