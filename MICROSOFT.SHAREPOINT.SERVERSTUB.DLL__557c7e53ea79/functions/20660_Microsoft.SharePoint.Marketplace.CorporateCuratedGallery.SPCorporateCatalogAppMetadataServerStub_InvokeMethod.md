# Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::InvokeMethod

- ea: `0x20660`
- end: `0x207e2`
- name: `Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::InvokeMethod`
- size: `386`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x205f0`
- `0x20610`
- `0x20620`
- `0x20630`
- `0x20640`
- `0x20650`
- `0x20660`

## string_xrefs

- `0x206cb`: `Uninstall`
- `0x20785`: `Uninstall`
- `0x206bf`: `Install`
- `0x20769`: `Install`
- `0x206e3`: `Remove`
- `0x207bd`: `Remove`

## pseudocode

```c

```

## disassembly

```asm
0x20660  ldarg.s  4
0x20662  brtrue.s loc_2066F
0x20664  ldstr    aProxycontext// "proxyContext"
0x20669  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2066e  throw
0x2066f  ldarg.1
0x20670  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata
0x20675  stloc.0
0x20676  ldloc.0
0x20677  brtrue.s loc_20684
0x20679  ldstr    aTarget// "target"
0x2067e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x20683  throw
0x20684  ldarg.0
0x20685  ldarg.2
0x20686  ldarg.s  4
0x20688  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2068d  starg.s  2
0x2068f  ldarg.2
0x20690  dup
0x20691  stloc.1
0x20692  brfalse  loc_207D4
0x20697  volatile.
0x20699  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600064e-1
0x2069e  brtrue.s loc_206F5
0x206a0  ldc.i4.6
0x206a1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x206a6  dup
0x206a7  ldstr    aDeploy// "Deploy"
0x206ac  ldc.i4.0
0x206ad  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x206b2  dup
0x206b3  ldstr    aRetract// "Retract"
0x206b8  ldc.i4.1
0x206b9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x206be  dup
0x206bf  ldstr    aInstall// "Install"
0x206c4  ldc.i4.2
0x206c5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x206ca  dup
0x206cb  ldstr    aUninstall// "Uninstall"
0x206d0  ldc.i4.3
0x206d1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x206d6  dup
0x206d7  ldstr    aUpgrade// "Upgrade"
0x206dc  ldc.i4.4
0x206dd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x206e2  dup
0x206e3  ldstr    aRemove// "Remove"
0x206e8  ldc.i4.5
0x206e9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x206ee  volatile.
0x206f0  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600064e-1
0x206f5  volatile.
0x206f7  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600064e-1
0x206fc  ldloc.1
0x206fd  ldloca.s 2
0x206ff  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x20704  brfalse  loc_207D4
0x20709  ldloc.2
0x2070a  switch   loc_2072C, loc_20748, loc_20764, loc_20780, loc_2079C, loc_207B8
0x20727  br       loc_207D4
0x2072c  ldarg.s  5
0x2072e  ldc.i4.1
0x2072f  stind.i1
0x20730  ldarg.0
0x20731  ldstr    aDeploy// "Deploy"
0x20736  ldarg.s  4
0x20738  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2073d  ldloc.0
0x2073e  ldarg.3
0x2073f  ldarg.s  4
0x20741  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::Deploy_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x20746  ldnull
0x20747  ret
0x20748  ldarg.s  5
0x2074a  ldc.i4.1
0x2074b  stind.i1
0x2074c  ldarg.0
0x2074d  ldstr    aRetract// "Retract"
0x20752  ldarg.s  4
0x20754  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20759  ldloc.0
0x2075a  ldarg.3
0x2075b  ldarg.s  4
0x2075d  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::Retract_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x20762  ldnull
0x20763  ret
0x20764  ldarg.s  5
0x20766  ldc.i4.1
0x20767  stind.i1
0x20768  ldarg.0
0x20769  ldstr    aInstall// "Install"
0x2076e  ldarg.s  4
0x20770  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20775  ldloc.0
0x20776  ldarg.3
0x20777  ldarg.s  4
0x20779  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::Install_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2077e  ldnull
0x2077f  ret
0x20780  ldarg.s  5
0x20782  ldc.i4.1
0x20783  stind.i1
0x20784  ldarg.0
0x20785  ldstr    aUninstall// "Uninstall"
0x2078a  ldarg.s  4
0x2078c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20791  ldloc.0
0x20792  ldarg.3
0x20793  ldarg.s  4
0x20795  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::Uninstall_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2079a  ldnull
0x2079b  ret
0x2079c  ldarg.s  5
0x2079e  ldc.i4.1
0x2079f  stind.i1
0x207a0  ldarg.0
0x207a1  ldstr    aUpgrade// "Upgrade"
0x207a6  ldarg.s  4
0x207a8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x207ad  ldloc.0
0x207ae  ldarg.3
0x207af  ldarg.s  4
0x207b1  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::Upgrade_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x207b6  ldnull
0x207b7  ret
0x207b8  ldarg.s  5
0x207ba  ldc.i4.1
0x207bb  stind.i1
0x207bc  ldarg.0
0x207bd  ldstr    aRemove// "Remove"
0x207c2  ldarg.s  4
0x207c4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x207c9  ldloc.0
0x207ca  ldarg.3
0x207cb  ldarg.s  4
0x207cd  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::Remove_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x207d2  ldnull
0x207d3  ret
0x207d4  ldarg.0
0x207d5  ldarg.1
0x207d6  ldarg.2
0x207d7  ldarg.3
0x207d8  ldarg.s  4
0x207da  ldarg.s  5
0x207dc  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x207e1  ret
```
