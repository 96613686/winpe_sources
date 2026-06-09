# Microsoft.SharePoint.Publishing.SitePageServerStub::GetProperty

- ea: `0x10230`
- end: `0x102ff`
- name: `Microsoft.SharePoint.Publishing.SitePageServerStub::GetProperty`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe700`
- `0x10230`

## string_xrefs

- `0x1028e`: `CanvasJson1`
- `0x102d0`: `CanvasJson1`

## pseudocode

```c

```

## disassembly

```asm
0x10230  ldarg.2
0x10231  brtrue.s loc_1023E
0x10233  ldstr    aPropname// "propName"
0x10238  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1023d  throw
0x1023e  ldarg.3
0x1023f  brtrue.s loc_1024C
0x10241  ldstr    aProxycontext// "proxyContext"
0x10246  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1024b  throw
0x1024c  ldarg.1
0x1024d  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage
0x10252  stloc.0
0x10253  ldloc.0
0x10254  brtrue.s loc_10261
0x10256  ldstr    aTarget// "target"
0x1025b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10260  throw
0x10261  ldarg.0
0x10262  ldarg.2
0x10263  ldarg.3
0x10264  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10269  starg.s  2
0x1026b  ldarg.2
0x1026c  dup
0x1026d  stloc.1
0x1026e  brfalse  loc_102F5
0x10273  ldloc.1
0x10274  ldstr    aAlternativeurl// "AlternativeUrlMap"
0x10279  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1027e  brtrue.s loc_102A9
0x10280  ldloc.1
0x10281  ldstr    aCanvascontent1// "CanvasContent1"
0x10286  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1028b  brtrue.s loc_102BC
0x1028d  ldloc.1
0x1028e  ldstr    aCanvasjson1// "CanvasJson1"
0x10293  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10298  brtrue.s loc_102CF
0x1029a  ldloc.1
0x1029b  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x102a0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x102a5  brtrue.s loc_102E2
0x102a7  br.s     loc_102F5
0x102a9  ldarg.0
0x102aa  ldstr    aAlternativeurl// "AlternativeUrlMap"
0x102af  ldarg.3
0x102b0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x102b5  ldloc.0
0x102b6  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage::get_AlternativeUrlMap()
0x102bb  ret
0x102bc  ldarg.0
0x102bd  ldstr    aCanvascontent1// "CanvasContent1"
0x102c2  ldarg.3
0x102c3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x102c8  ldloc.0
0x102c9  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage::get_CanvasContent1()
0x102ce  ret
0x102cf  ldarg.0
0x102d0  ldstr    aCanvasjson1// "CanvasJson1"
0x102d5  ldarg.3
0x102d6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x102db  ldloc.0
0x102dc  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage::get_CanvasJson1()
0x102e1  ret
0x102e2  ldarg.0
0x102e3  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x102e8  ldarg.3
0x102e9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x102ee  ldloc.0
0x102ef  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage::get_LayoutWebpartsContent()
0x102f4  ret
0x102f5  ldarg.0
0x102f6  ldarg.1
0x102f7  ldarg.2
0x102f8  ldarg.3
0x102f9  call     instance object Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::GetProperty(object target, string propName, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x102fe  ret
```
