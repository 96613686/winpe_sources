# Microsoft.SharePoint.Publishing.SitePageServiceServerStub::InvokeMethod

- ea: `0x10db0`
- end: `0x10e9d`
- name: `Microsoft.SharePoint.Publishing.SitePageServiceServerStub::InvokeMethod`
- size: `237`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x10d00`
- `0x10d10`
- `0x10d50`
- `0x10da0`
- `0x10db0`

## string_xrefs

- `0x10de8`: `Update`
- `0x10e22`: `Update`
- `0x10e0f`: `CanCreatePromotedPage`
- `0x10e74`: `CanCreatePromotedPage`

## pseudocode

```c

```

## disassembly

```asm
0x10db0  ldarg.s  4
0x10db2  brtrue.s loc_10DBF
0x10db4  ldstr    aProxycontext// "proxyContext"
0x10db9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10dbe  throw
0x10dbf  ldarg.1
0x10dc0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService
0x10dc5  stloc.0
0x10dc6  ldloc.0
0x10dc7  brtrue.s loc_10DD4
0x10dc9  ldstr    aTarget// "target"
0x10dce  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10dd3  throw
0x10dd4  ldarg.0
0x10dd5  ldarg.2
0x10dd6  ldarg.s  4
0x10dd8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10ddd  starg.s  2
0x10ddf  ldarg.2
0x10de0  dup
0x10de1  stloc.1
0x10de2  brfalse  loc_10E8F
0x10de7  ldloc.1
0x10de8  ldstr    aUpdate// "Update"
0x10ded  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10df2  brtrue.s loc_10E1D
0x10df4  ldloc.1
0x10df5  ldstr    aAddimage// "AddImage"
0x10dfa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10dff  brtrue.s loc_10E39
0x10e01  ldloc.1
0x10e02  ldstr    aAddimagefromex// "AddImageFromExternalUrl"
0x10e07  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10e0c  brtrue.s loc_10E54
0x10e0e  ldloc.1
0x10e0f  ldstr    aCancreatepromo// "CanCreatePromotedPage"
0x10e14  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10e19  brtrue.s loc_10E6F
0x10e1b  br.s     loc_10E8F
0x10e1d  ldarg.s  5
0x10e1f  ldc.i4.1
0x10e20  stind.i1
0x10e21  ldarg.0
0x10e22  ldstr    aUpdate// "Update"
0x10e27  ldarg.s  4
0x10e29  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10e2e  ldloc.0
0x10e2f  ldarg.3
0x10e30  ldarg.s  4
0x10e32  call     void Microsoft.SharePoint.Publishing.SitePageServiceServerStub::Update_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10e37  ldnull
0x10e38  ret
0x10e39  ldarg.s  5
0x10e3b  ldc.i4.0
0x10e3c  stind.i1
0x10e3d  ldarg.0
0x10e3e  ldstr    aAddimage// "AddImage"
0x10e43  ldarg.s  4
0x10e45  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10e4a  ldloc.0
0x10e4b  ldarg.3
0x10e4c  ldarg.s  4
0x10e4e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.Publishing.SitePageServiceServerStub::AddImage_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10e53  ret
0x10e54  ldarg.s  5
0x10e56  ldc.i4.0
0x10e57  stind.i1
0x10e58  ldarg.0
0x10e59  ldstr    aAddimagefromex// "AddImageFromExternalUrl"
0x10e5e  ldarg.s  4
0x10e60  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10e65  ldloc.0
0x10e66  ldarg.3
0x10e67  ldarg.s  4
0x10e69  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.Publishing.SitePageServiceServerStub::AddImageFromExternalUrl_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10e6e  ret
0x10e6f  ldarg.s  5
0x10e71  ldc.i4.0
0x10e72  stind.i1
0x10e73  ldarg.0
0x10e74  ldstr    aCancreatepromo// "CanCreatePromotedPage"
0x10e79  ldarg.s  4
0x10e7b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10e80  ldloc.0
0x10e81  ldarg.3
0x10e82  ldarg.s  4
0x10e84  call     bool Microsoft.SharePoint.Publishing.SitePageServiceServerStub::CanCreatePromotedPage_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10e89  box      [mscorlib]System.Boolean
0x10e8e  ret
0x10e8f  ldarg.0
0x10e90  ldarg.1
0x10e91  ldarg.2
0x10e92  ldarg.3
0x10e93  ldarg.s  4
0x10e95  ldarg.s  5
0x10e97  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x10e9c  ret
```
