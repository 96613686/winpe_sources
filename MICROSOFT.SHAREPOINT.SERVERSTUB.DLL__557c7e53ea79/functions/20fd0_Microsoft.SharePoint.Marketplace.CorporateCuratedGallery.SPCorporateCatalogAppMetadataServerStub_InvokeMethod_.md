# Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::InvokeMethod_0

- ea: `0x20fd0`
- end: `0x21152`
- name: `Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::InvokeMethod_0`
- size: `386`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x20f60`
- `0x20f80`
- `0x20f90`
- `0x20fa0`
- `0x20fb0`
- `0x20fc0`
- `0x20fd0`

## string_xrefs

- `0x2103b`: `Uninstall`
- `0x210f5`: `Uninstall`
- `0x2102f`: `Install`
- `0x210d9`: `Install`
- `0x21053`: `Remove`
- `0x2112d`: `Remove`

## pseudocode

```c

```

## disassembly

```asm
0x20fd0  ldarg.s  4
0x20fd2  brtrue.s loc_20FDF
0x20fd4  ldstr    aProxycontext// "proxyContext"
0x20fd9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x20fde  throw
0x20fdf  ldarg.1
0x20fe0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata
0x20fe5  stloc.0
0x20fe6  ldloc.0
0x20fe7  brtrue.s loc_20FF4
0x20fe9  ldstr    aTarget// "target"
0x20fee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x20ff3  throw
0x20ff4  ldarg.0
0x20ff5  ldarg.2
0x20ff6  ldarg.s  4
0x20ff8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20ffd  starg.s  2
0x20fff  ldarg.2
0x21000  dup
0x21001  stloc.1
0x21002  brfalse  loc_21144
0x21007  volatile.
0x21009  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600065c-1
0x2100e  brtrue.s loc_21065
0x21010  ldc.i4.6
0x21011  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x21016  dup
0x21017  ldstr    aDeploy// "Deploy"
0x2101c  ldc.i4.0
0x2101d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x21022  dup
0x21023  ldstr    aRetract// "Retract"
0x21028  ldc.i4.1
0x21029  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2102e  dup
0x2102f  ldstr    aInstall// "Install"
0x21034  ldc.i4.2
0x21035  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2103a  dup
0x2103b  ldstr    aUninstall// "Uninstall"
0x21040  ldc.i4.3
0x21041  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x21046  dup
0x21047  ldstr    aUpgrade// "Upgrade"
0x2104c  ldc.i4.4
0x2104d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x21052  dup
0x21053  ldstr    aRemove// "Remove"
0x21058  ldc.i4.5
0x21059  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2105e  volatile.
0x21060  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600065c-1
0x21065  volatile.
0x21067  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600065c-1
0x2106c  ldloc.1
0x2106d  ldloca.s 2
0x2106f  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x21074  brfalse  loc_21144
0x21079  ldloc.2
0x2107a  switch   loc_2109C, loc_210B8, loc_210D4, loc_210F0, loc_2110C, loc_21128
0x21097  br       loc_21144
0x2109c  ldarg.s  5
0x2109e  ldc.i4.1
0x2109f  stind.i1
0x210a0  ldarg.0
0x210a1  ldstr    aDeploy// "Deploy"
0x210a6  ldarg.s  4
0x210a8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x210ad  ldloc.0
0x210ae  ldarg.3
0x210af  ldarg.s  4
0x210b1  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::Deploy_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x210b6  ldnull
0x210b7  ret
0x210b8  ldarg.s  5
0x210ba  ldc.i4.1
0x210bb  stind.i1
0x210bc  ldarg.0
0x210bd  ldstr    aRetract// "Retract"
0x210c2  ldarg.s  4
0x210c4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x210c9  ldloc.0
0x210ca  ldarg.3
0x210cb  ldarg.s  4
0x210cd  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::Retract_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x210d2  ldnull
0x210d3  ret
0x210d4  ldarg.s  5
0x210d6  ldc.i4.1
0x210d7  stind.i1
0x210d8  ldarg.0
0x210d9  ldstr    aInstall// "Install"
0x210de  ldarg.s  4
0x210e0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x210e5  ldloc.0
0x210e6  ldarg.3
0x210e7  ldarg.s  4
0x210e9  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::Install_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x210ee  ldnull
0x210ef  ret
0x210f0  ldarg.s  5
0x210f2  ldc.i4.1
0x210f3  stind.i1
0x210f4  ldarg.0
0x210f5  ldstr    aUninstall// "Uninstall"
0x210fa  ldarg.s  4
0x210fc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x21101  ldloc.0
0x21102  ldarg.3
0x21103  ldarg.s  4
0x21105  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::Uninstall_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2110a  ldnull
0x2110b  ret
0x2110c  ldarg.s  5
0x2110e  ldc.i4.1
0x2110f  stind.i1
0x21110  ldarg.0
0x21111  ldstr    aUpgrade// "Upgrade"
0x21116  ldarg.s  4
0x21118  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2111d  ldloc.0
0x2111e  ldarg.3
0x2111f  ldarg.s  4
0x21121  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::Upgrade_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x21126  ldnull
0x21127  ret
0x21128  ldarg.s  5
0x2112a  ldc.i4.1
0x2112b  stind.i1
0x2112c  ldarg.0
0x2112d  ldstr    aRemove// "Remove"
0x21132  ldarg.s  4
0x21134  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x21139  ldloc.0
0x2113a  ldarg.3
0x2113b  ldarg.s  4
0x2113d  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::Remove_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x21142  ldnull
0x21143  ret
0x21144  ldarg.0
0x21145  ldarg.1
0x21146  ldarg.2
0x21147  ldarg.3
0x21148  ldarg.s  4
0x2114a  ldarg.s  5
0x2114c  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x21151  ret
```
