# Microsoft.SharePoint.Publishing.SitePageServiceServerStub::GetProperty

- ea: `0x10ea0`
- end: `0x10f51`
- name: `Microsoft.SharePoint.Publishing.SitePageServiceServerStub::GetProperty`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10ea0`

## string_xrefs

- `0x10ee1`: `CommunicationSite`
- `0x10f0a`: `CommunicationSite`

## pseudocode

```c

```

## disassembly

```asm
0x10ea0  ldarg.2
0x10ea1  brtrue.s loc_10EAE
0x10ea3  ldstr    aPropname// "propName"
0x10ea8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10ead  throw
0x10eae  ldarg.3
0x10eaf  brtrue.s loc_10EBC
0x10eb1  ldstr    aProxycontext// "proxyContext"
0x10eb6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10ebb  throw
0x10ebc  ldarg.1
0x10ebd  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService
0x10ec2  stloc.0
0x10ec3  ldloc.0
0x10ec4  brtrue.s loc_10ED1
0x10ec6  ldstr    aTarget// "target"
0x10ecb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10ed0  throw
0x10ed1  ldarg.0
0x10ed2  ldarg.2
0x10ed3  ldarg.3
0x10ed4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10ed9  starg.s  2
0x10edb  ldarg.2
0x10edc  dup
0x10edd  stloc.1
0x10ede  brfalse.s loc_10F47
0x10ee0  ldloc.1
0x10ee1  ldstr    aCommunications// "CommunicationSite"
0x10ee6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10eeb  brtrue.s loc_10F09
0x10eed  ldloc.1
0x10eee  ldstr    aCustomcontenta// "CustomContentApprovalEnabled"
0x10ef3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10ef8  brtrue.s loc_10F1C
0x10efa  ldloc.1
0x10efb  ldstr    aPages// "Pages"
0x10f00  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10f05  brtrue.s loc_10F34
0x10f07  br.s     loc_10F47
0x10f09  ldarg.0
0x10f0a  ldstr    aCommunications// "CommunicationSite"
0x10f0f  ldarg.3
0x10f10  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10f15  ldloc.0
0x10f16  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSite [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService::get_CommunicationSite()
0x10f1b  ret
0x10f1c  ldarg.0
0x10f1d  ldstr    aCustomcontenta// "CustomContentApprovalEnabled"
0x10f22  ldarg.3
0x10f23  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10f28  ldloc.0
0x10f29  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService::get_CustomContentApprovalEnabled()
0x10f2e  box      [mscorlib]System.Boolean
0x10f33  ret
0x10f34  ldarg.0
0x10f35  ldstr    aPages// "Pages"
0x10f3a  ldarg.3
0x10f3b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10f40  ldloc.0
0x10f41  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService::get_Pages()
0x10f46  ret
0x10f47  ldarg.0
0x10f48  ldarg.1
0x10f49  ldarg.2
0x10f4a  ldarg.3
0x10f4b  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10f50  ret
```
