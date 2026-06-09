# Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::SetProperty

- ea: `0x67c0`
- end: `0x694e`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::SetProperty`
- size: `398`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x5920`
- `0x67c0`

## string_xrefs

- `0x6851`: `SimpleLinkUrl`
- `0x6927`: `SimpleLinkUrl`

## pseudocode

```c

```

## disassembly

```asm
0x67c0  ldarg.s  4
0x67c2  brtrue.s loc_67CF
0x67c4  ldstr    aProxycontext// "proxyContext"
0x67c9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x67ce  throw
0x67cf  ldarg.1
0x67d0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm
0x67d5  stloc.0
0x67d6  ldloc.0
0x67d7  brtrue.s loc_67E4
0x67d9  ldstr    aTarget// "target"
0x67de  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x67e3  throw
0x67e4  ldarg.2
0x67e5  brtrue.s loc_67F2
0x67e7  ldstr    aPropname// "propName"
0x67ec  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x67f1  throw
0x67f2  ldarg.0
0x67f3  ldarg.2
0x67f4  ldarg.s  4
0x67f6  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x67fb  starg.s  2
0x67fd  ldarg.2
0x67fe  dup
0x67ff  stloc.1
0x6800  brfalse  loc_6942
0x6805  volatile.
0x6807  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000102-1
0x680c  brtrue.s loc_6863
0x680e  ldc.i4.6
0x680f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x6814  dup
0x6815  ldstr    aAssociatedfold// "AssociatedFolderUrl"
0x681a  ldc.i4.0
0x681b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6820  dup
0x6821  ldstr    aCategoryimageu// "CategoryImageUrl"
0x6826  ldc.i4.1
0x6827  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x682c  dup
0x682d  ldstr    aExcludefromcur// "ExcludeFromCurrentNavigation"
0x6832  ldc.i4.2
0x6833  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6838  dup
0x6839  ldstr    aExcludefromglo// "ExcludeFromGlobalNavigation"
0x683e  ldc.i4.3
0x683f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6844  dup
0x6845  ldstr    aHovertext// "HoverText"
0x684a  ldc.i4.4
0x684b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6850  dup
0x6851  ldstr    aSimplelinkurl// "SimpleLinkUrl"
0x6856  ldc.i4.5
0x6857  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x685c  volatile.
0x685e  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000102-1
0x6863  volatile.
0x6865  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000102-1
0x686a  ldloc.1
0x686b  ldloca.s 2
0x686d  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x6872  brfalse  loc_6942
0x6877  ldloc.2
0x6878  switch   loc_689A, loc_68B6, loc_68D2, loc_68EE, loc_690A, loc_6926
0x6895  br       loc_6942
0x689a  ldarg.0
0x689b  ldstr    aAssociatedfold// "AssociatedFolderUrl"
0x68a0  ldarg.s  4
0x68a2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x68a7  ldloc.0
0x68a8  ldarg.3
0x68a9  ldarg.s  4
0x68ab  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x68b0  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::set_AssociatedFolderUrl(string)
0x68b5  ret
0x68b6  ldarg.0
0x68b7  ldstr    aCategoryimageu// "CategoryImageUrl"
0x68bc  ldarg.s  4
0x68be  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x68c3  ldloc.0
0x68c4  ldarg.3
0x68c5  ldarg.s  4
0x68c7  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x68cc  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::set_CategoryImageUrl(string)
0x68d1  ret
0x68d2  ldarg.0
0x68d3  ldstr    aExcludefromcur// "ExcludeFromCurrentNavigation"
0x68d8  ldarg.s  4
0x68da  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x68df  ldloc.0
0x68e0  ldarg.3
0x68e1  ldarg.s  4
0x68e3  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x68e8  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::set_ExcludeFromCurrentNavigation(bool)
0x68ed  ret
0x68ee  ldarg.0
0x68ef  ldstr    aExcludefromglo// "ExcludeFromGlobalNavigation"
0x68f4  ldarg.s  4
0x68f6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x68fb  ldloc.0
0x68fc  ldarg.3
0x68fd  ldarg.s  4
0x68ff  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6904  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::set_ExcludeFromGlobalNavigation(bool)
0x6909  ret
0x690a  ldarg.0
0x690b  ldstr    aHovertext// "HoverText"
0x6910  ldarg.s  4
0x6912  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6917  ldloc.0
0x6918  ldarg.3
0x6919  ldarg.s  4
0x691b  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6920  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::set_HoverText(string)
0x6925  ret
0x6926  ldarg.0
0x6927  ldstr    aSimplelinkurl// "SimpleLinkUrl"
0x692c  ldarg.s  4
0x692e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6933  ldloc.0
0x6934  ldarg.3
0x6935  ldarg.s  4
0x6937  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x693c  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::set_SimpleLinkUrl(string)
0x6941  ret
0x6942  ldarg.0
0x6943  ldarg.1
0x6944  ldarg.2
0x6945  ldarg.3
0x6946  ldarg.s  4
0x6948  call     instance void Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::SetProperty(object target, string propName, class [System.Xml]System.Xml.XmlNode node, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x694d  ret
```
