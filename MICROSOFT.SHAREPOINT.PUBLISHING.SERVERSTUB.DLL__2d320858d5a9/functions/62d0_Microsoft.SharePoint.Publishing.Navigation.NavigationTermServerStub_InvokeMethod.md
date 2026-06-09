# Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::InvokeMethod

- ea: `0x62d0`
- end: `0x64ff`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::InvokeMethod`
- size: `559`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x5690`
- `0x61e0`
- `0x6200`
- `0x6220`
- `0x6250`
- `0x6260`
- `0x6270`
- `0x6280`
- `0x6290`
- `0x62a0`
- `0x62c0`
- `0x62d0`

## string_xrefs

- `0x6387`: `DeleteObject`
- `0x64da`: `DeleteObject`

## pseudocode

```c

```

## disassembly

```asm
0x62d0  ldarg.s  4
0x62d2  brtrue.s loc_62DF
0x62d4  ldstr    aProxycontext// "proxyContext"
0x62d9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x62de  throw
0x62df  ldarg.1
0x62e0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm
0x62e5  stloc.0
0x62e6  ldloc.0
0x62e7  brtrue.s loc_62F4
0x62e9  ldstr    aTarget// "target"
0x62ee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x62f3  throw
0x62f4  ldarg.0
0x62f5  ldarg.2
0x62f6  ldarg.s  4
0x62f8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x62fd  starg.s  2
0x62ff  ldarg.2
0x6300  dup
0x6301  stloc.1
0x6302  brfalse  loc_64F1
0x6307  volatile.
0x6309  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000100-1
0x630e  brtrue   loc_639A
0x6313  ldc.i4.s 0xA
0x6315  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x631a  dup
0x631b  ldstr    aGetaseditable// "GetAsEditable"
0x6320  ldc.i4.0
0x6321  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6326  dup
0x6327  ldstr    aGetwithnewview// "GetWithNewView"
0x632c  ldc.i4.1
0x632d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6332  dup
0x6333  ldstr    aGetresolvedtar// "GetResolvedTargetUrl"
0x6338  ldc.i4.2
0x6339  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x633e  dup
0x633f  ldstr    aGetresolvedtar_0// "GetResolvedTargetUrlWithoutQuery"
0x6344  ldc.i4.3
0x6345  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x634a  dup
0x634b  ldstr    aGetresolvedass// "GetResolvedAssociatedFolderUrl"
0x6350  ldc.i4.4
0x6351  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6356  dup
0x6357  ldstr    aGetwebrelative// "GetWebRelativeFriendlyUrl"
0x635c  ldc.i4.5
0x635d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6362  dup
0x6363  ldstr    aGetallparentte// "GetAllParentTerms"
0x6368  ldc.i4.6
0x6369  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x636e  dup
0x636f  ldstr    aGettaxonomyter_0// "GetTaxonomyTerm"
0x6374  ldc.i4.7
0x6375  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x637a  dup
0x637b  ldstr    aMove// "Move"
0x6380  ldc.i4.8
0x6381  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6386  dup
0x6387  ldstr    aDeleteobject// "DeleteObject"
0x638c  ldc.i4.s 9
0x638e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6393  volatile.
0x6395  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000100-1
0x639a  volatile.
0x639c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000100-1
0x63a1  ldloc.1
0x63a2  ldloca.s 2
0x63a4  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x63a9  brfalse  loc_64F1
0x63ae  ldloc.2
0x63af  switch   loc_63E1, loc_63FC, loc_6417, loc_6432, loc_644D, loc_6468, loc_6483, loc_649E, loc_64B9, loc_64D5
0x63dc  br       loc_64F1
0x63e1  ldarg.s  5
0x63e3  ldc.i4.0
0x63e4  stind.i1
0x63e5  ldarg.0
0x63e6  ldstr    aGetaseditable// "GetAsEditable"
0x63eb  ldarg.s  4
0x63ed  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x63f2  ldloc.0
0x63f3  ldarg.3
0x63f4  ldarg.s  4
0x63f6  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetAsEditable_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x63fb  ret
0x63fc  ldarg.s  5
0x63fe  ldc.i4.0
0x63ff  stind.i1
0x6400  ldarg.0
0x6401  ldstr    aGetwithnewview// "GetWithNewView"
0x6406  ldarg.s  4
0x6408  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x640d  ldloc.0
0x640e  ldarg.3
0x640f  ldarg.s  4
0x6411  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetWithNewView_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6416  ret
0x6417  ldarg.s  5
0x6419  ldc.i4.0
0x641a  stind.i1
0x641b  ldarg.0
0x641c  ldstr    aGetresolvedtar// "GetResolvedTargetUrl"
0x6421  ldarg.s  4
0x6423  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6428  ldloc.0
0x6429  ldarg.3
0x642a  ldarg.s  4
0x642c  call     string Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetResolvedTargetUrl_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6431  ret
0x6432  ldarg.s  5
0x6434  ldc.i4.0
0x6435  stind.i1
0x6436  ldarg.0
0x6437  ldstr    aGetresolvedtar_0// "GetResolvedTargetUrlWithoutQuery"
0x643c  ldarg.s  4
0x643e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6443  ldloc.0
0x6444  ldarg.3
0x6445  ldarg.s  4
0x6447  call     string Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetResolvedTargetUrlWithoutQuery_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x644c  ret
0x644d  ldarg.s  5
0x644f  ldc.i4.0
0x6450  stind.i1
0x6451  ldarg.0
0x6452  ldstr    aGetresolvedass// "GetResolvedAssociatedFolderUrl"
0x6457  ldarg.s  4
0x6459  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x645e  ldloc.0
0x645f  ldarg.3
0x6460  ldarg.s  4
0x6462  call     string Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetResolvedAssociatedFolderUrl_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6467  ret
0x6468  ldarg.s  5
0x646a  ldc.i4.0
0x646b  stind.i1
0x646c  ldarg.0
0x646d  ldstr    aGetwebrelative// "GetWebRelativeFriendlyUrl"
0x6472  ldarg.s  4
0x6474  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6479  ldloc.0
0x647a  ldarg.3
0x647b  ldarg.s  4
0x647d  call     string Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetWebRelativeFriendlyUrl_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6482  ret
0x6483  ldarg.s  5
0x6485  ldc.i4.0
0x6486  stind.i1
0x6487  ldarg.0
0x6488  ldstr    aGetallparentte// "GetAllParentTerms"
0x648d  ldarg.s  4
0x648f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6494  ldloc.0
0x6495  ldarg.3
0x6496  ldarg.s  4
0x6498  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermCollectionCsom Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetAllParentTerms_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x649d  ret
0x649e  ldarg.s  5
0x64a0  ldc.i4.0
0x64a1  stind.i1
0x64a2  ldarg.0
0x64a3  ldstr    aGettaxonomyter_0// "GetTaxonomyTerm"
0x64a8  ldarg.s  4
0x64aa  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64af  ldloc.0
0x64b0  ldarg.3
0x64b1  ldarg.s  4
0x64b3  call     class [Microsoft.SharePoint.Taxonomy]Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetTaxonomyTerm_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x64b8  ret
0x64b9  ldarg.s  5
0x64bb  ldc.i4.1
0x64bc  stind.i1
0x64bd  ldarg.0
0x64be  ldstr    aMove// "Move"
0x64c3  ldarg.s  4
0x64c5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64ca  ldloc.0
0x64cb  ldarg.3
0x64cc  ldarg.s  4
0x64ce  call     void Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::Move_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x64d3  ldnull
0x64d4  ret
0x64d5  ldarg.s  5
0x64d7  ldc.i4.1
0x64d8  stind.i1
0x64d9  ldarg.0
0x64da  ldstr    aDeleteobject// "DeleteObject"
0x64df  ldarg.s  4
0x64e1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64e6  ldloc.0
0x64e7  ldarg.3
0x64e8  ldarg.s  4
0x64ea  call     void Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::DeleteObject_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x64ef  ldnull
0x64f0  ret
0x64f1  ldarg.0
0x64f2  ldarg.1
0x64f3  ldarg.2
0x64f4  ldarg.3
0x64f5  ldarg.s  4
0x64f7  ldarg.s  5
0x64f9  call     instance object Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::InvokeMethod(object target, string methodName, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext, [out] bool& isVoid)
0x64fe  ret
```
