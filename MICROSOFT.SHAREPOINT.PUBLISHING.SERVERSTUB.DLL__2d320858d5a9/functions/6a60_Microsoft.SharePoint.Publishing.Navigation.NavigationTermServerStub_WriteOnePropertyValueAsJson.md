# Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::WriteOnePropertyValueAsJson

- ea: `0x6a60`
- end: `0x703b`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::WriteOnePropertyValueAsJson`
- size: `1499`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x59d0`
- `0x6a60`

## string_xrefs

- `0x6b2b`: `SimpleLinkUrl`
- `0x6f70`: `SimpleLinkUrl`

## pseudocode

```c

```

## disassembly

```asm
0x6a60  ldc.i4.0
0x6a61  stloc.0
0x6a62  ldarg.2
0x6a63  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm
0x6a68  stloc.1
0x6a69  ldloc.1
0x6a6a  brtrue.s loc_6A77
0x6a6c  ldstr    aTarget// "target"
0x6a71  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6a76  throw
0x6a77  ldarg.3
0x6a78  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x6a7d  dup
0x6a7e  stloc.2
0x6a7f  brfalse  loc_702D
0x6a84  volatile.
0x6a86  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000107-1
0x6a8b  brtrue   loc_6B58
0x6a90  ldc.i4.s 0xF
0x6a92  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x6a97  dup
0x6a98  ldstr    aAssociatedfold// "AssociatedFolderUrl"
0x6a9d  ldc.i4.0
0x6a9e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6aa3  dup
0x6aa4  ldstr    aCatalogtargetu_0// "CatalogTargetUrl"
0x6aa9  ldc.i4.1
0x6aaa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6aaf  dup
0x6ab0  ldstr    aCategoryimageu// "CategoryImageUrl"
0x6ab5  ldc.i4.2
0x6ab6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6abb  dup
0x6abc  ldstr    aExcludedprovid// "ExcludedProviders"
0x6ac1  ldc.i4.3
0x6ac2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6ac7  dup
0x6ac8  ldstr    aExcludefromcur// "ExcludeFromCurrentNavigation"
0x6acd  ldc.i4.4
0x6ace  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6ad3  dup
0x6ad4  ldstr    aExcludefromglo// "ExcludeFromGlobalNavigation"
0x6ad9  ldc.i4.5
0x6ada  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6adf  dup
0x6ae0  ldstr    aFriendlyurlseg// "FriendlyUrlSegment"
0x6ae5  ldc.i4.6
0x6ae6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6aeb  dup
0x6aec  ldstr    aHovertext// "HoverText"
0x6af1  ldc.i4.7
0x6af2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6af7  dup
0x6af8  ldstr    aIsdeprecated// "IsDeprecated"
0x6afd  ldc.i4.8
0x6afe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6b03  dup
0x6b04  ldstr    aIspinned// "IsPinned"
0x6b09  ldc.i4.s 9
0x6b0b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6b10  dup
0x6b11  ldstr    aIspinnedroot// "IsPinnedRoot"
0x6b16  ldc.i4.s 0xA
0x6b18  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6b1d  dup
0x6b1e  ldstr    aParent// "Parent"
0x6b23  ldc.i4.s 0xB
0x6b25  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6b2a  dup
0x6b2b  ldstr    aSimplelinkurl// "SimpleLinkUrl"
0x6b30  ldc.i4.s 0xC
0x6b32  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6b37  dup
0x6b38  ldstr    aTargeturl// "TargetUrl"
0x6b3d  ldc.i4.s 0xD
0x6b3f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6b44  dup
0x6b45  ldstr    aTermset// "TermSet"
0x6b4a  ldc.i4.s 0xE
0x6b4c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6b51  volatile.
0x6b53  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000107-1
0x6b58  volatile.
0x6b5a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000107-1
0x6b5f  ldloc.2
0x6b60  ldloca.s 3
0x6b62  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x6b67  brfalse  loc_702D
0x6b6c  ldloc.3
0x6b6d  switch   loc_6BB3, loc_6BFD, loc_6C4E, loc_6C98, loc_6CE9, loc_6D33, loc_6D7D, loc_6DCE, loc_6E18, loc_6E62, loc_6EAC, loc_6EF6, loc_6F47, loc_6F91, loc_6FDF
0x6bae  br       loc_702D
0x6bb3  ldarg.3
0x6bb4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6bb9  stloc.s  4
0x6bbb  ldloca.s 4
0x6bbd  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6bc2  brfalse.s loc_6BDB
0x6bc4  ldarg.3
0x6bc5  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6bca  stloc.s  5
0x6bcc  ldloca.s 5
0x6bce  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6bd3  brtrue.s loc_6BDB
0x6bd5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6bda  throw
0x6bdb  ldarg.0
0x6bdc  ldstr    aAssociatedfold// "AssociatedFolderUrl"
0x6be1  ldarg.s  4
0x6be3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6be8  ldc.i4.1
0x6be9  stloc.0
0x6bea  ldarg.1
0x6beb  ldloc.1
0x6bec  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_AssociatedFolderUrl()
0x6bf1  ldarg.s  4
0x6bf3  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6bf8  br       loc_7039
0x6bfd  ldarg.3
0x6bfe  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6c03  stloc.s  6
0x6c05  ldloca.s 6
0x6c07  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6c0c  brfalse.s loc_6C25
0x6c0e  ldarg.3
0x6c0f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6c14  stloc.s  7
0x6c16  ldloca.s 7
0x6c18  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6c1d  brfalse.s loc_6C25
0x6c1f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6c24  throw
0x6c25  ldarg.0
0x6c26  ldstr    aCatalogtargetu_0// "CatalogTargetUrl"
0x6c2b  ldarg.s  4
0x6c2d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6c32  ldc.i4.1
0x6c33  stloc.0
0x6c34  ldarg.0
0x6c35  ldarg.1
0x6c36  ldloc.1
0x6c37  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_CatalogTargetUrl()
0x6c3c  ldarg.3
0x6c3d  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x6c42  ldarg.s  4
0x6c44  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6c49  br       loc_7039
0x6c4e  ldarg.3
0x6c4f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6c54  stloc.s  8
0x6c56  ldloca.s 8
0x6c58  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6c5d  brfalse.s loc_6C76
0x6c5f  ldarg.3
0x6c60  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6c65  stloc.s  9
0x6c67  ldloca.s 9
0x6c69  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6c6e  brtrue.s loc_6C76
0x6c70  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6c75  throw
0x6c76  ldarg.0
0x6c77  ldstr    aCategoryimageu// "CategoryImageUrl"
0x6c7c  ldarg.s  4
0x6c7e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6c83  ldc.i4.1
0x6c84  stloc.0
0x6c85  ldarg.1
0x6c86  ldloc.1
0x6c87  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_CategoryImageUrl()
0x6c8c  ldarg.s  4
0x6c8e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6c93  br       loc_7039
0x6c98  ldarg.3
0x6c99  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6c9e  stloc.s  0xA
0x6ca0  ldloca.s 0xA
0x6ca2  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6ca7  brfalse.s loc_6CC0
0x6ca9  ldarg.3
0x6caa  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6caf  stloc.s  0xB
0x6cb1  ldloca.s 0xB
0x6cb3  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6cb8  brfalse.s loc_6CC0
0x6cba  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6cbf  throw
0x6cc0  ldarg.0
0x6cc1  ldstr    aExcludedprovid// "ExcludedProviders"
0x6cc6  ldarg.s  4
0x6cc8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6ccd  ldc.i4.1
0x6cce  stloc.0
0x6ccf  ldarg.0
0x6cd0  ldarg.1
0x6cd1  ldloc.1
0x6cd2  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsom [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_ExcludedProvidersCsom()
0x6cd7  ldarg.3
0x6cd8  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x6cdd  ldarg.s  4
0x6cdf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6ce4  br       loc_7039
0x6ce9  ldarg.3
0x6cea  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6cef  stloc.s  0xC
0x6cf1  ldloca.s 0xC
0x6cf3  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6cf8  brfalse.s loc_6D11
0x6cfa  ldarg.3
0x6cfb  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6d00  stloc.s  0xD
0x6d02  ldloca.s 0xD
0x6d04  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6d09  brtrue.s loc_6D11
0x6d0b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6d10  throw
0x6d11  ldarg.0
0x6d12  ldstr    aExcludefromcur// "ExcludeFromCurrentNavigation"
0x6d17  ldarg.s  4
0x6d19  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d1e  ldc.i4.1
0x6d1f  stloc.0
0x6d20  ldarg.1
0x6d21  ldloc.1
0x6d22  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_ExcludeFromCurrentNavigation()
0x6d27  ldarg.s  4
0x6d29  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d2e  br       loc_7039
0x6d33  ldarg.3
0x6d34  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6d39  stloc.s  0xE
0x6d3b  ldloca.s 0xE
0x6d3d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6d42  brfalse.s loc_6D5B
0x6d44  ldarg.3
0x6d45  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6d4a  stloc.s  0xF
0x6d4c  ldloca.s 0xF
0x6d4e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6d53  brtrue.s loc_6D5B
0x6d55  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6d5a  throw
0x6d5b  ldarg.0
0x6d5c  ldstr    aExcludefromglo// "ExcludeFromGlobalNavigation"
0x6d61  ldarg.s  4
0x6d63  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d68  ldc.i4.1
0x6d69  stloc.0
0x6d6a  ldarg.1
0x6d6b  ldloc.1
0x6d6c  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_ExcludeFromGlobalNavigation()
0x6d71  ldarg.s  4
0x6d73  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d78  br       loc_7039
0x6d7d  ldarg.3
0x6d7e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6d83  stloc.s  0x10
0x6d85  ldloca.s 0x10
0x6d87  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6d8c  brfalse.s loc_6DA5
0x6d8e  ldarg.3
0x6d8f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6d94  stloc.s  0x11
0x6d96  ldloca.s 0x11
0x6d98  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6d9d  brfalse.s loc_6DA5
0x6d9f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6da4  throw
0x6da5  ldarg.0
0x6da6  ldstr    aFriendlyurlseg// "FriendlyUrlSegment"
0x6dab  ldarg.s  4
0x6dad  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6db2  ldc.i4.1
0x6db3  stloc.0
0x6db4  ldarg.0
0x6db5  ldarg.1
0x6db6  ldloc.1
0x6db7  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_FriendlyUrlSegment()
0x6dbc  ldarg.3
0x6dbd  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x6dc2  ldarg.s  4
0x6dc4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6dc9  br       loc_7039
0x6dce  ldarg.3
0x6dcf  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6dd4  stloc.s  0x12
0x6dd6  ldloca.s 0x12
0x6dd8  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6ddd  brfalse.s loc_6DF6
0x6ddf  ldarg.3
0x6de0  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6de5  stloc.s  0x13
0x6de7  ldloca.s 0x13
0x6de9  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6dee  brtrue.s loc_6DF6
0x6df0  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6df5  throw
0x6df6  ldarg.0
0x6df7  ldstr    aHovertext// "HoverText"
0x6dfc  ldarg.s  4
0x6dfe  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
  ... truncated ...
```
