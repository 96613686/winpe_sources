# Microsoft.SharePoint.Publishing.SitePageServiceServerStub::InvokeMethod_0

- ea: `0x11380`
- end: `0x1146d`
- name: `Microsoft.SharePoint.Publishing.SitePageServiceServerStub::InvokeMethod_0`
- size: `237`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x112d0`
- `0x112e0`
- `0x11320`
- `0x11370`
- `0x11380`

## string_xrefs

- `0x113b8`: `Update`
- `0x113f2`: `Update`
- `0x113df`: `CanCreatePromotedPage`
- `0x11444`: `CanCreatePromotedPage`

## pseudocode

```c

```

## disassembly

```asm
0x11380  ldarg.s  4
0x11382  brtrue.s loc_1138F
0x11384  ldstr    aProxycontext// "proxyContext"
0x11389  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1138e  throw
0x1138f  ldarg.1
0x11390  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService
0x11395  stloc.0
0x11396  ldloc.0
0x11397  brtrue.s loc_113A4
0x11399  ldstr    aTarget// "target"
0x1139e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x113a3  throw
0x113a4  ldarg.0
0x113a5  ldarg.2
0x113a6  ldarg.s  4
0x113a8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x113ad  starg.s  2
0x113af  ldarg.2
0x113b0  dup
0x113b1  stloc.1
0x113b2  brfalse  loc_1145F
0x113b7  ldloc.1
0x113b8  ldstr    aUpdate// "Update"
0x113bd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x113c2  brtrue.s loc_113ED
0x113c4  ldloc.1
0x113c5  ldstr    aAddimage// "AddImage"
0x113ca  call     bool [mscorlib]System.String::op_Equality(string, string)
0x113cf  brtrue.s loc_11409
0x113d1  ldloc.1
0x113d2  ldstr    aAddimagefromex// "AddImageFromExternalUrl"
0x113d7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x113dc  brtrue.s loc_11424
0x113de  ldloc.1
0x113df  ldstr    aCancreatepromo// "CanCreatePromotedPage"
0x113e4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x113e9  brtrue.s loc_1143F
0x113eb  br.s     loc_1145F
0x113ed  ldarg.s  5
0x113ef  ldc.i4.1
0x113f0  stind.i1
0x113f1  ldarg.0
0x113f2  ldstr    aUpdate// "Update"
0x113f7  ldarg.s  4
0x113f9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x113fe  ldloc.0
0x113ff  ldarg.3
0x11400  ldarg.s  4
0x11402  call     void Microsoft.SharePoint.Publishing.SitePageServiceServerStub::Update_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11407  ldnull
0x11408  ret
0x11409  ldarg.s  5
0x1140b  ldc.i4.0
0x1140c  stind.i1
0x1140d  ldarg.0
0x1140e  ldstr    aAddimage// "AddImage"
0x11413  ldarg.s  4
0x11415  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1141a  ldloc.0
0x1141b  ldarg.3
0x1141c  ldarg.s  4
0x1141e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.Publishing.SitePageServiceServerStub::AddImage_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11423  ret
0x11424  ldarg.s  5
0x11426  ldc.i4.0
0x11427  stind.i1
0x11428  ldarg.0
0x11429  ldstr    aAddimagefromex// "AddImageFromExternalUrl"
0x1142e  ldarg.s  4
0x11430  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11435  ldloc.0
0x11436  ldarg.3
0x11437  ldarg.s  4
0x11439  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.Publishing.SitePageServiceServerStub::AddImageFromExternalUrl_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1143e  ret
0x1143f  ldarg.s  5
0x11441  ldc.i4.0
0x11442  stind.i1
0x11443  ldarg.0
0x11444  ldstr    aCancreatepromo// "CanCreatePromotedPage"
0x11449  ldarg.s  4
0x1144b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11450  ldloc.0
0x11451  ldarg.3
0x11452  ldarg.s  4
0x11454  call     bool Microsoft.SharePoint.Publishing.SitePageServiceServerStub::CanCreatePromotedPage_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11459  box      [mscorlib]System.Boolean
0x1145e  ret
0x1145f  ldarg.0
0x11460  ldarg.1
0x11461  ldarg.2
0x11462  ldarg.3
0x11463  ldarg.s  4
0x11465  ldarg.s  5
0x11467  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x1146c  ret
```
