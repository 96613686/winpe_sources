# Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::InvokeMethod

- ea: `0x11320`
- end: `0x11524`
- name: `Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::InvokeMethod`
- size: `516`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x11210`
- `0x11240`
- `0x11270`
- `0x112a0`
- `0x112b0`
- `0x112c0`
- `0x112d0`
- `0x112f0`
- `0x11300`
- `0x11320`

## string_xrefs

- `0x113a4`: `Update`
- `0x114ad`: `Update`
- `0x11398`: `DeleteObject`
- `0x11491`: `DeleteObject`
- `0x11374`: `CreateInstance`
- `0x1143e`: `CreateInstance`
- `0x11380`: `CreateCollectionInstance`
- `0x1145a`: `CreateCollectionInstance`
- `0x113b0`: `FromXml`
- `0x114c9`: `FromXml`
- `0x113bc`: `ToXml`
- `0x114e5`: `ToXml`

## pseudocode

```c

```

## disassembly

```asm
0x11320  ldarg.s  4
0x11322  brtrue.s loc_1132F
0x11324  ldstr    aProxycontext// "proxyContext"
0x11329  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1132e  throw
0x1132f  ldarg.1
0x11330  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance
0x11335  stloc.0
0x11336  ldloc.0
0x11337  brtrue.s loc_11344
0x11339  ldstr    aTarget// "target"
0x1133e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11343  throw
0x11344  ldarg.0
0x11345  ldarg.2
0x11346  ldarg.s  4
0x11348  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1134d  starg.s  2
0x1134f  ldarg.2
0x11350  dup
0x11351  stloc.1
0x11352  brfalse  loc_11516
0x11357  volatile.
0x11359  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60002cf-1
0x1135e  brtrue.s loc_113DA
0x11360  ldc.i4.s 9
0x11362  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x11367  dup
0x11368  ldstr    aSetfieldvalue// "SetFieldValue"
0x1136d  ldc.i4.0
0x1136e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11373  dup
0x11374  ldstr    aCreateinstance// "CreateInstance"
0x11379  ldc.i4.1
0x1137a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1137f  dup
0x11380  ldstr    aCreatecollecti// "CreateCollectionInstance"
0x11385  ldc.i4.2
0x11386  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1138b  dup
0x1138c  ldstr    aGetidentity// "GetIdentity"
0x11391  ldc.i4.3
0x11392  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11397  dup
0x11398  ldstr    aDeleteobject// "DeleteObject"
0x1139d  ldc.i4.4
0x1139e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x113a3  dup
0x113a4  ldstr    aUpdate// "Update"
0x113a9  ldc.i4.5
0x113aa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x113af  dup
0x113b0  ldstr    aFromxml// "FromXml"
0x113b5  ldc.i4.6
0x113b6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x113bb  dup
0x113bc  ldstr    aToxml// "ToXml"
0x113c1  ldc.i4.7
0x113c2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x113c7  dup
0x113c8  ldstr    aGetfieldvalue// "GetFieldValue"
0x113cd  ldc.i4.8
0x113ce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x113d3  volatile.
0x113d5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60002cf-1
0x113da  volatile.
0x113dc  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60002cf-1
0x113e1  ldloc.1
0x113e2  ldloca.s 2
0x113e4  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x113e9  brfalse  loc_11516
0x113ee  ldloc.2
0x113ef  switch   loc_1141D, loc_11439, loc_11455, loc_11471, loc_1148C, loc_114A8, loc_114C4, loc_114E0, loc_114FB
0x11418  br       loc_11516
0x1141d  ldarg.s  5
0x1141f  ldc.i4.1
0x11420  stind.i1
0x11421  ldarg.0
0x11422  ldstr    aSetfieldvalue// "SetFieldValue"
0x11427  ldarg.s  4
0x11429  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1142e  ldloc.0
0x1142f  ldarg.3
0x11430  ldarg.s  4
0x11432  call     void Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::SetFieldValue_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11437  ldnull
0x11438  ret
0x11439  ldarg.s  5
0x1143b  ldc.i4.1
0x1143c  stind.i1
0x1143d  ldarg.0
0x1143e  ldstr    aCreateinstance// "CreateInstance"
0x11443  ldarg.s  4
0x11445  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1144a  ldloc.0
0x1144b  ldarg.3
0x1144c  ldarg.s  4
0x1144e  call     void Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::CreateInstance_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11453  ldnull
0x11454  ret
0x11455  ldarg.s  5
0x11457  ldc.i4.1
0x11458  stind.i1
0x11459  ldarg.0
0x1145a  ldstr    aCreatecollecti// "CreateCollectionInstance"
0x1145f  ldarg.s  4
0x11461  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11466  ldloc.0
0x11467  ldarg.3
0x11468  ldarg.s  4
0x1146a  call     void Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::CreateCollectionInstance_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1146f  ldnull
0x11470  ret
0x11471  ldarg.s  5
0x11473  ldc.i4.0
0x11474  stind.i1
0x11475  ldarg.0
0x11476  ldstr    aGetidentity// "GetIdentity"
0x1147b  ldarg.s  4
0x1147d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11482  ldloc.0
0x11483  ldarg.3
0x11484  ldarg.s  4
0x11486  call     class [Microsoft.BusinessData]Microsoft.BusinessData.Runtime.Identity Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::GetIdentity_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1148b  ret
0x1148c  ldarg.s  5
0x1148e  ldc.i4.1
0x1148f  stind.i1
0x11490  ldarg.0
0x11491  ldstr    aDeleteobject// "DeleteObject"
0x11496  ldarg.s  4
0x11498  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1149d  ldloc.0
0x1149e  ldarg.3
0x1149f  ldarg.s  4
0x114a1  call     void Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::DeleteObject_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x114a6  ldnull
0x114a7  ret
0x114a8  ldarg.s  5
0x114aa  ldc.i4.1
0x114ab  stind.i1
0x114ac  ldarg.0
0x114ad  ldstr    aUpdate// "Update"
0x114b2  ldarg.s  4
0x114b4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x114b9  ldloc.0
0x114ba  ldarg.3
0x114bb  ldarg.s  4
0x114bd  call     void Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::Update_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x114c2  ldnull
0x114c3  ret
0x114c4  ldarg.s  5
0x114c6  ldc.i4.1
0x114c7  stind.i1
0x114c8  ldarg.0
0x114c9  ldstr    aFromxml// "FromXml"
0x114ce  ldarg.s  4
0x114d0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x114d5  ldloc.0
0x114d6  ldarg.3
0x114d7  ldarg.s  4
0x114d9  call     void Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::FromXml_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x114de  ldnull
0x114df  ret
0x114e0  ldarg.s  5
0x114e2  ldc.i4.0
0x114e3  stind.i1
0x114e4  ldarg.0
0x114e5  ldstr    aToxml// "ToXml"
0x114ea  ldarg.s  4
0x114ec  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x114f1  ldloc.0
0x114f2  ldarg.3
0x114f3  ldarg.s  4
0x114f5  call     string Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::ToXml_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x114fa  ret
0x114fb  ldarg.s  5
0x114fd  ldc.i4.0
0x114fe  stind.i1
0x114ff  ldarg.0
0x11500  ldstr    aGetfieldvalue// "GetFieldValue"
0x11505  ldarg.s  4
0x11507  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1150c  ldloc.0
0x1150d  ldarg.3
0x1150e  ldarg.s  4
0x11510  call     object Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::GetFieldValue_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11515  ret
0x11516  ldarg.0
0x11517  ldarg.1
0x11518  ldarg.2
0x11519  ldarg.3
0x1151a  ldarg.s  4
0x1151c  ldarg.s  5
0x1151e  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x11523  ret
```
