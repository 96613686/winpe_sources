# Microsoft.SharePoint.Publishing.SitePageServerStub::SetProperty_0

- ea: `0x10ae0`
- end: `0x10ba5`
- name: `Microsoft.SharePoint.Publishing.SitePageServerStub::SetProperty_0`
- size: `197`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xfb30`
- `0x10ae0`

## string_xrefs

- `0x10b30`: `CanvasJson1`
- `0x10b66`: `CanvasJson1`

## pseudocode

```c

```

## disassembly

```asm
0x10ae0  ldarg.s  4
0x10ae2  brtrue.s loc_10AEF
0x10ae4  ldstr    aProxycontext// "proxyContext"
0x10ae9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10aee  throw
0x10aef  ldarg.1
0x10af0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage
0x10af5  stloc.0
0x10af6  ldloc.0
0x10af7  brtrue.s loc_10B04
0x10af9  ldstr    aTarget// "target"
0x10afe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10b03  throw
0x10b04  ldarg.2
0x10b05  brtrue.s loc_10B12
0x10b07  ldstr    aPropname// "propName"
0x10b0c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10b11  throw
0x10b12  ldarg.0
0x10b13  ldarg.2
0x10b14  ldarg.s  4
0x10b16  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10b1b  starg.s  2
0x10b1d  ldarg.2
0x10b1e  dup
0x10b1f  stloc.1
0x10b20  brfalse.s loc_10B99
0x10b22  ldloc.1
0x10b23  ldstr    aCanvascontent1// "CanvasContent1"
0x10b28  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10b2d  brtrue.s loc_10B4B
0x10b2f  ldloc.1
0x10b30  ldstr    aCanvasjson1// "CanvasJson1"
0x10b35  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10b3a  brtrue.s loc_10B65
0x10b3c  ldloc.1
0x10b3d  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x10b42  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10b47  brtrue.s loc_10B7F
0x10b49  br.s     loc_10B99
0x10b4b  ldarg.0
0x10b4c  ldstr    aCanvascontent1// "CanvasContent1"
0x10b51  ldarg.s  4
0x10b53  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10b58  ldloc.0
0x10b59  ldarg.3
0x10b5a  callvirt T0x2B000001
0x10b5f  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage::set_CanvasContent1(string)
0x10b64  ret
0x10b65  ldarg.0
0x10b66  ldstr    aCanvasjson1// "CanvasJson1"
0x10b6b  ldarg.s  4
0x10b6d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10b72  ldloc.0
0x10b73  ldarg.3
0x10b74  callvirt T0x2B000001
0x10b79  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage::set_CanvasJson1(string)
0x10b7e  ret
0x10b7f  ldarg.0
0x10b80  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x10b85  ldarg.s  4
0x10b87  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10b8c  ldloc.0
0x10b8d  ldarg.3
0x10b8e  callvirt T0x2B000001
0x10b93  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage::set_LayoutWebpartsContent(string)
0x10b98  ret
0x10b99  ldarg.0
0x10b9a  ldarg.1
0x10b9b  ldarg.2
0x10b9c  ldarg.3
0x10b9d  ldarg.s  4
0x10b9f  call     instance void Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::SetProperty(object target, string propName, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue node, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10ba4  ret
```
