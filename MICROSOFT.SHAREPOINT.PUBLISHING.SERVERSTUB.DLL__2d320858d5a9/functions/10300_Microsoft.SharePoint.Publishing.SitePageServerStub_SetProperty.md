# Microsoft.SharePoint.Publishing.SitePageServerStub::SetProperty

- ea: `0x10300`
- end: `0x103cb`
- name: `Microsoft.SharePoint.Publishing.SitePageServerStub::SetProperty`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xeb60`
- `0x10300`

## string_xrefs

- `0x10350`: `CanvasJson1`
- `0x10388`: `CanvasJson1`

## pseudocode

```c

```

## disassembly

```asm
0x10300  ldarg.s  4
0x10302  brtrue.s loc_1030F
0x10304  ldstr    aProxycontext// "proxyContext"
0x10309  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1030e  throw
0x1030f  ldarg.1
0x10310  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage
0x10315  stloc.0
0x10316  ldloc.0
0x10317  brtrue.s loc_10324
0x10319  ldstr    aTarget// "target"
0x1031e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10323  throw
0x10324  ldarg.2
0x10325  brtrue.s loc_10332
0x10327  ldstr    aPropname// "propName"
0x1032c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10331  throw
0x10332  ldarg.0
0x10333  ldarg.2
0x10334  ldarg.s  4
0x10336  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1033b  starg.s  2
0x1033d  ldarg.2
0x1033e  dup
0x1033f  stloc.1
0x10340  brfalse.s loc_103BF
0x10342  ldloc.1
0x10343  ldstr    aCanvascontent1// "CanvasContent1"
0x10348  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1034d  brtrue.s loc_1036B
0x1034f  ldloc.1
0x10350  ldstr    aCanvasjson1// "CanvasJson1"
0x10355  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1035a  brtrue.s loc_10387
0x1035c  ldloc.1
0x1035d  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x10362  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10367  brtrue.s loc_103A3
0x10369  br.s     loc_103BF
0x1036b  ldarg.0
0x1036c  ldstr    aCanvascontent1// "CanvasContent1"
0x10371  ldarg.s  4
0x10373  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10378  ldloc.0
0x10379  ldarg.3
0x1037a  ldarg.s  4
0x1037c  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10381  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage::set_CanvasContent1(string)
0x10386  ret
0x10387  ldarg.0
0x10388  ldstr    aCanvasjson1// "CanvasJson1"
0x1038d  ldarg.s  4
0x1038f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10394  ldloc.0
0x10395  ldarg.3
0x10396  ldarg.s  4
0x10398  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1039d  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage::set_CanvasJson1(string)
0x103a2  ret
0x103a3  ldarg.0
0x103a4  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x103a9  ldarg.s  4
0x103ab  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x103b0  ldloc.0
0x103b1  ldarg.3
0x103b2  ldarg.s  4
0x103b4  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x103b9  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage::set_LayoutWebpartsContent(string)
0x103be  ret
0x103bf  ldarg.0
0x103c0  ldarg.1
0x103c1  ldarg.2
0x103c2  ldarg.3
0x103c3  ldarg.s  4
0x103c5  call     instance void Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::SetProperty(object target, string propName, class [System.Xml]System.Xml.XmlNode node, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x103ca  ret
```
