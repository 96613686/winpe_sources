# Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::InvokeStaticMethod_0

- ea: `0xb14d0`
- end: `0xb16c3`
- name: `Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::InvokeStaticMethod_0`
- size: `499`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0xb11e0`
- `0xb1210`
- `0xb1240`
- `0xb1270`
- `0xb1330`
- `0xb1380`
- `0xb13b0`
- `0xb1440`
- `0xb1460`
- `0xb1490`
- `0xb14d0`

## string_xrefs

- `0xb1534`: `ForwardObjectLink`
- `0xb162f`: `ForwardObjectLink`
- `0xb154c`: `UpdateDocumentSharingInfo`
- `0xb165f`: `UpdateDocumentSharingInfo`
- `0xb1504`: `ShareLink`
- `0xb15cf`: `ShareLink`
- `0xb1564`: `DeleteLinkByKind`
- `0xb168f`: `DeleteLinkByKind`
- `0xb1570`: `UnshareLink`
- `0xb16a8`: `UnshareLink`

## pseudocode

```c

```

## disassembly

```asm
0xb14d0  ldarg.3
0xb14d1  brtrue.s loc_B14DE
0xb14d3  ldstr    aProxycontext// "proxyContext"
0xb14d8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb14dd  throw
0xb14de  ldarg.0
0xb14df  ldarg.1
0xb14e0  ldarg.3
0xb14e1  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb14e6  starg.s  1
0xb14e8  ldarg.1
0xb14e9  dup
0xb14ea  stloc.0
0xb14eb  brfalse  loc_B16BC
0xb14f0  volatile.
0xb14f2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001ce4-1
0xb14f7  brtrue   loc_B1583
0xb14fc  ldc.i4.s 0xA
0xb14fe  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xb1503  dup
0xb1504  ldstr    aSharelink// "ShareLink"
0xb1509  ldc.i4.0
0xb150a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb150f  dup
0xb1510  ldstr    aCheckpermissio_0// "CheckPermissions"
0xb1515  ldc.i4.1
0xb1516  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb151b  dup
0xb151c  ldstr    aGetsharinginfo// "GetSharingInformation"
0xb1521  ldc.i4.2
0xb1522  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb1527  dup
0xb1528  ldstr    aShareobject// "ShareObject"
0xb152d  ldc.i4.3
0xb152e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb1533  dup
0xb1534  ldstr    aForwardobjectl// "ForwardObjectLink"
0xb1539  ldc.i4.4
0xb153a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb153f  dup
0xb1540  ldstr    aGetobjectshari_2// "GetObjectSharingSettings"
0xb1545  ldc.i4.5
0xb1546  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb154b  dup
0xb154c  ldstr    aUpdatedocument// "UpdateDocumentSharingInfo"
0xb1551  ldc.i4.6
0xb1552  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb1557  dup
0xb1558  ldstr    aUnshareobject// "UnshareObject"
0xb155d  ldc.i4.7
0xb155e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb1563  dup
0xb1564  ldstr    aDeletelinkbyki// "DeleteLinkByKind"
0xb1569  ldc.i4.8
0xb156a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb156f  dup
0xb1570  ldstr    aUnsharelink// "UnshareLink"
0xb1575  ldc.i4.s 9
0xb1577  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb157c  volatile.
0xb157e  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001ce4-1
0xb1583  volatile.
0xb1585  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001ce4-1
0xb158a  ldloc.0
0xb158b  ldloca.s 1
0xb158d  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xb1592  brfalse  loc_B16BC
0xb1597  ldloc.1
0xb1598  switch   loc_B15CA, loc_B15E2, loc_B15FA, loc_B1612, loc_B162A, loc_B1642, loc_B165A, loc_B1672, loc_B168A, loc_B16A3
0xb15c5  br       loc_B16BC
0xb15ca  ldarg.s  4
0xb15cc  ldc.i4.0
0xb15cd  stind.i1
0xb15ce  ldarg.0
0xb15cf  ldstr    aSharelink// "ShareLink"
0xb15d4  ldarg.3
0xb15d5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb15da  ldarg.2
0xb15db  ldarg.3
0xb15dc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.ShareLinkResponse Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::ShareLink_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb15e1  ret
0xb15e2  ldarg.s  4
0xb15e4  ldc.i4.0
0xb15e5  stind.i1
0xb15e6  ldarg.0
0xb15e7  ldstr    aCheckpermissio_0// "CheckPermissions"
0xb15ec  ldarg.3
0xb15ed  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb15f2  ldarg.2
0xb15f3  ldarg.3
0xb15f4  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.EntityPermission> Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::CheckPermissions_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb15f9  ret
0xb15fa  ldarg.s  4
0xb15fc  ldc.i4.0
0xb15fd  stind.i1
0xb15fe  ldarg.0
0xb15ff  ldstr    aGetsharinginfo// "GetSharingInformation"
0xb1604  ldarg.3
0xb1605  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb160a  ldarg.2
0xb160b  ldarg.3
0xb160c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::GetSharingInformation_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb1611  ret
0xb1612  ldarg.s  4
0xb1614  ldc.i4.0
0xb1615  stind.i1
0xb1616  ldarg.0
0xb1617  ldstr    aShareobject// "ShareObject"
0xb161c  ldarg.3
0xb161d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb1622  ldarg.2
0xb1623  ldarg.3
0xb1624  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SharingResult Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::ShareObject_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb1629  ret
0xb162a  ldarg.s  4
0xb162c  ldc.i4.0
0xb162d  stind.i1
0xb162e  ldarg.0
0xb162f  ldstr    aForwardobjectl// "ForwardObjectLink"
0xb1634  ldarg.3
0xb1635  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb163a  ldarg.2
0xb163b  ldarg.3
0xb163c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SharingResult Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::ForwardObjectLink_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb1641  ret
0xb1642  ldarg.s  4
0xb1644  ldc.i4.0
0xb1645  stind.i1
0xb1646  ldarg.0
0xb1647  ldstr    aGetobjectshari_2// "GetObjectSharingSettings"
0xb164c  ldarg.3
0xb164d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb1652  ldarg.2
0xb1653  ldarg.3
0xb1654  call     class [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::GetObjectSharingSettings_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb1659  ret
0xb165a  ldarg.s  4
0xb165c  ldc.i4.0
0xb165d  stind.i1
0xb165e  ldarg.0
0xb165f  ldstr    aUpdatedocument// "UpdateDocumentSharingInfo"
0xb1664  ldarg.3
0xb1665  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb166a  ldarg.2
0xb166b  ldarg.3
0xb166c  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.UserSharingResult> Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::UpdateDocumentSharingInfo_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb1671  ret
0xb1672  ldarg.s  4
0xb1674  ldc.i4.0
0xb1675  stind.i1
0xb1676  ldarg.0
0xb1677  ldstr    aUnshareobject// "UnshareObject"
0xb167c  ldarg.3
0xb167d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb1682  ldarg.2
0xb1683  ldarg.3
0xb1684  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SharingResult Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::UnshareObject_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb1689  ret
0xb168a  ldarg.s  4
0xb168c  ldc.i4.1
0xb168d  stind.i1
0xb168e  ldarg.0
0xb168f  ldstr    aDeletelinkbyki// "DeleteLinkByKind"
0xb1694  ldarg.3
0xb1695  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb169a  ldarg.2
0xb169b  ldarg.3
0xb169c  call     void Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::DeleteLinkByKind_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb16a1  ldnull
0xb16a2  ret
0xb16a3  ldarg.s  4
0xb16a5  ldc.i4.1
0xb16a6  stind.i1
0xb16a7  ldarg.0
0xb16a8  ldstr    aUnsharelink// "UnshareLink"
0xb16ad  ldarg.3
0xb16ae  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb16b3  ldarg.2
0xb16b4  ldarg.3
0xb16b5  call     void Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::UnshareLink_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb16ba  ldnull
0xb16bb  ret
0xb16bc  ldarg.1
0xb16bd  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xb16c2  throw
```
