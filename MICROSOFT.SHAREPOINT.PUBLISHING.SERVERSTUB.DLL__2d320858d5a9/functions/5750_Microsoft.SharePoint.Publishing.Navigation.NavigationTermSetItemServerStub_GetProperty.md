# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::GetProperty

- ea: `0x5750`
- end: `0x591d`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::GetProperty`
- size: `461`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6500`
- `0x7b90`

## callees

- `0x5750`

## string_xrefs

- `0x57bc`: `IsReadOnly`
- `0x5885`: `IsReadOnly`
- `0x57c8`: `LinkType`
- `0x589d`: `LinkType`

## pseudocode

```c

```

## disassembly

```asm
0x5750  ldarg.2
0x5751  brtrue.s loc_575E
0x5753  ldstr    aPropname// "propName"
0x5758  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x575d  throw
0x575e  ldarg.3
0x575f  brtrue.s loc_576C
0x5761  ldstr    aProxycontext// "proxyContext"
0x5766  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x576b  throw
0x576c  ldarg.1
0x576d  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem
0x5772  stloc.0
0x5773  ldloc.0
0x5774  brtrue.s loc_5781
0x5776  ldstr    aTarget// "target"
0x577b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5780  throw
0x5781  ldarg.0
0x5782  ldarg.2
0x5783  ldarg.3
0x5784  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5789  starg.s  2
0x578b  ldarg.2
0x578c  dup
0x578d  stloc.1
0x578e  brfalse  loc_5913
0x5793  volatile.
0x5795  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60000e1-1
0x579a  brtrue.s loc_5816
0x579c  ldc.i4.s 9
0x579e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x57a3  dup
0x57a4  ldstr    aCatalogtargetu// "CatalogTargetUrlForChildTerms"
0x57a9  ldc.i4.0
0x57aa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x57af  dup
0x57b0  ldstr    aId// "Id"
0x57b5  ldc.i4.1
0x57b6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x57bb  dup
0x57bc  ldstr    aIsreadonly// "IsReadOnly"
0x57c1  ldc.i4.2
0x57c2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x57c7  dup
0x57c8  ldstr    aLinktype// "LinkType"
0x57cd  ldc.i4.3
0x57ce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x57d3  dup
0x57d4  ldstr    aTargeturlforch// "TargetUrlForChildTerms"
0x57d9  ldc.i4.4
0x57da  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x57df  dup
0x57e0  ldstr    aTaxonomyname// "TaxonomyName"
0x57e5  ldc.i4.5
0x57e6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x57eb  dup
0x57ec  ldstr    aTerms// "Terms"
0x57f1  ldc.i4.6
0x57f2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x57f7  dup
0x57f8  ldstr    aTitle// "Title"
0x57fd  ldc.i4.7
0x57fe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5803  dup
0x5804  ldstr    aView// "View"
0x5809  ldc.i4.8
0x580a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x580f  volatile.
0x5811  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60000e1-1
0x5816  volatile.
0x5818  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60000e1-1
0x581d  ldloc.1
0x581e  ldloca.s 2
0x5820  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x5825  brfalse  loc_5913
0x582a  ldloc.2
0x582b  switch   loc_5859, loc_586C, loc_5884, loc_589C, loc_58B4, loc_58C7, loc_58DA, loc_58ED, loc_5900
0x5854  br       loc_5913
0x5859  ldarg.0
0x585a  ldstr    aCatalogtargetu// "CatalogTargetUrlForChildTerms"
0x585f  ldarg.3
0x5860  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5865  ldloc.0
0x5866  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_CatalogTargetUrlForChildTerms()
0x586b  ret
0x586c  ldarg.0
0x586d  ldstr    aId// "Id"
0x5872  ldarg.3
0x5873  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5878  ldloc.0
0x5879  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_Id()
0x587e  box      [mscorlib]System.Guid
0x5883  ret
0x5884  ldarg.0
0x5885  ldstr    aIsreadonly// "IsReadOnly"
0x588a  ldarg.3
0x588b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5890  ldloc.0
0x5891  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_IsReadOnly()
0x5896  box      [mscorlib]System.Boolean
0x589b  ret
0x589c  ldarg.0
0x589d  ldstr    aLinktype// "LinkType"
0x58a2  ldarg.3
0x58a3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58a8  ldloc.0
0x58a9  callvirt instance valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationLinkType [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_LinkType()
0x58ae  box      [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationLinkType
0x58b3  ret
0x58b4  ldarg.0
0x58b5  ldstr    aTargeturlforch// "TargetUrlForChildTerms"
0x58ba  ldarg.3
0x58bb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58c0  ldloc.0
0x58c1  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_TargetUrlForChildTerms()
0x58c6  ret
0x58c7  ldarg.0
0x58c8  ldstr    aTaxonomyname// "TaxonomyName"
0x58cd  ldarg.3
0x58ce  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58d3  ldloc.0
0x58d4  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_TaxonomyName()
0x58d9  ret
0x58da  ldarg.0
0x58db  ldstr    aTerms// "Terms"
0x58e0  ldarg.3
0x58e1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58e6  ldloc.0
0x58e7  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermCollectionCsom [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_TermsCsom()
0x58ec  ret
0x58ed  ldarg.0
0x58ee  ldstr    aTitle// "Title"
0x58f3  ldarg.3
0x58f4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58f9  ldloc.0
0x58fa  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_Title()
0x58ff  ret
0x5900  ldarg.0
0x5901  ldstr    aView// "View"
0x5906  ldarg.3
0x5907  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x590c  ldloc.0
0x590d  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_View()
0x5912  ret
0x5913  ldarg.0
0x5914  ldarg.1
0x5915  ldarg.2
0x5916  ldarg.3
0x5917  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x591c  ret
```
