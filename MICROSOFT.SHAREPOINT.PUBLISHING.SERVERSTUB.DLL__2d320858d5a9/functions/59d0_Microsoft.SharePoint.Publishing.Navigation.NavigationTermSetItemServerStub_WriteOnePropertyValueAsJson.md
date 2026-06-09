# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::WriteOnePropertyValueAsJson

- ea: `0x59d0`
- end: `0x5d7f`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::WriteOnePropertyValueAsJson`
- size: `943`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6a60`
- `0x7ed0`

## callees

- `0x59d0`

## string_xrefs

- `0x5a1d`: `IsReadOnly`
- `0x5b7e`: `IsReadOnly`
- `0x5a29`: `LinkType`
- `0x5bc8`: `LinkType`

## pseudocode

```c

```

## disassembly

```asm
0x59d0  ldc.i4.0
0x59d1  stloc.0
0x59d2  ldarg.2
0x59d3  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem
0x59d8  stloc.1
0x59d9  ldloc.1
0x59da  brtrue.s loc_59E7
0x59dc  ldstr    aTarget// "target"
0x59e1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x59e6  throw
0x59e7  ldarg.3
0x59e8  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x59ed  dup
0x59ee  stloc.2
0x59ef  brfalse  loc_5D71
0x59f4  volatile.
0x59f6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60000e4-1
0x59fb  brtrue.s loc_5A77
0x59fd  ldc.i4.s 9
0x59ff  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x5a04  dup
0x5a05  ldstr    aCatalogtargetu// "CatalogTargetUrlForChildTerms"
0x5a0a  ldc.i4.0
0x5a0b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5a10  dup
0x5a11  ldstr    aId// "Id"
0x5a16  ldc.i4.1
0x5a17  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5a1c  dup
0x5a1d  ldstr    aIsreadonly// "IsReadOnly"
0x5a22  ldc.i4.2
0x5a23  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5a28  dup
0x5a29  ldstr    aLinktype// "LinkType"
0x5a2e  ldc.i4.3
0x5a2f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5a34  dup
0x5a35  ldstr    aTargeturlforch// "TargetUrlForChildTerms"
0x5a3a  ldc.i4.4
0x5a3b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5a40  dup
0x5a41  ldstr    aTaxonomyname// "TaxonomyName"
0x5a46  ldc.i4.5
0x5a47  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5a4c  dup
0x5a4d  ldstr    aTerms// "Terms"
0x5a52  ldc.i4.6
0x5a53  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5a58  dup
0x5a59  ldstr    aTitle// "Title"
0x5a5e  ldc.i4.7
0x5a5f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5a64  dup
0x5a65  ldstr    aView// "View"
0x5a6a  ldc.i4.8
0x5a6b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5a70  volatile.
0x5a72  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60000e4-1
0x5a77  volatile.
0x5a79  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60000e4-1
0x5a7e  ldloc.2
0x5a7f  ldloca.s 3
0x5a81  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x5a86  brfalse  loc_5D71
0x5a8b  ldloc.3
0x5a8c  switch   loc_5ABA, loc_5B0B, loc_5B55, loc_5B9F, loc_5BE9, loc_5C3A, loc_5C84, loc_5CD5, loc_5D23
0x5ab5  br       loc_5D71
0x5aba  ldarg.3
0x5abb  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5ac0  stloc.s  4
0x5ac2  ldloca.s 4
0x5ac4  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5ac9  brfalse.s loc_5AE2
0x5acb  ldarg.3
0x5acc  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5ad1  stloc.s  5
0x5ad3  ldloca.s 5
0x5ad5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5ada  brfalse.s loc_5AE2
0x5adc  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5ae1  throw
0x5ae2  ldarg.0
0x5ae3  ldstr    aCatalogtargetu// "CatalogTargetUrlForChildTerms"
0x5ae8  ldarg.s  4
0x5aea  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5aef  ldc.i4.1
0x5af0  stloc.0
0x5af1  ldarg.0
0x5af2  ldarg.1
0x5af3  ldloc.1
0x5af4  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_CatalogTargetUrlForChildTerms()
0x5af9  ldarg.3
0x5afa  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x5aff  ldarg.s  4
0x5b01  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5b06  br       loc_5D7D
0x5b0b  ldarg.3
0x5b0c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5b11  stloc.s  6
0x5b13  ldloca.s 6
0x5b15  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5b1a  brfalse.s loc_5B33
0x5b1c  ldarg.3
0x5b1d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5b22  stloc.s  7
0x5b24  ldloca.s 7
0x5b26  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5b2b  brtrue.s loc_5B33
0x5b2d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5b32  throw
0x5b33  ldarg.0
0x5b34  ldstr    aId// "Id"
0x5b39  ldarg.s  4
0x5b3b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5b40  ldc.i4.1
0x5b41  stloc.0
0x5b42  ldarg.1
0x5b43  ldloc.1
0x5b44  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_Id()
0x5b49  ldarg.s  4
0x5b4b  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5b50  br       loc_5D7D
0x5b55  ldarg.3
0x5b56  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5b5b  stloc.s  8
0x5b5d  ldloca.s 8
0x5b5f  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5b64  brfalse.s loc_5B7D
0x5b66  ldarg.3
0x5b67  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5b6c  stloc.s  9
0x5b6e  ldloca.s 9
0x5b70  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5b75  brtrue.s loc_5B7D
0x5b77  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5b7c  throw
0x5b7d  ldarg.0
0x5b7e  ldstr    aIsreadonly// "IsReadOnly"
0x5b83  ldarg.s  4
0x5b85  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5b8a  ldc.i4.1
0x5b8b  stloc.0
0x5b8c  ldarg.1
0x5b8d  ldloc.1
0x5b8e  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_IsReadOnly()
0x5b93  ldarg.s  4
0x5b95  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5b9a  br       loc_5D7D
0x5b9f  ldarg.3
0x5ba0  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5ba5  stloc.s  0xA
0x5ba7  ldloca.s 0xA
0x5ba9  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5bae  brfalse.s loc_5BC7
0x5bb0  ldarg.3
0x5bb1  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5bb6  stloc.s  0xB
0x5bb8  ldloca.s 0xB
0x5bba  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5bbf  brtrue.s loc_5BC7
0x5bc1  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5bc6  throw
0x5bc7  ldarg.0
0x5bc8  ldstr    aLinktype// "LinkType"
0x5bcd  ldarg.s  4
0x5bcf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5bd4  ldc.i4.1
0x5bd5  stloc.0
0x5bd6  ldarg.1
0x5bd7  ldloc.1
0x5bd8  callvirt instance valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationLinkType [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_LinkType()
0x5bdd  ldarg.s  4
0x5bdf  call     T0x2B000013
0x5be4  br       loc_5D7D
0x5be9  ldarg.3
0x5bea  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5bef  stloc.s  0xC
0x5bf1  ldloca.s 0xC
0x5bf3  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5bf8  brfalse.s loc_5C11
0x5bfa  ldarg.3
0x5bfb  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c00  stloc.s  0xD
0x5c02  ldloca.s 0xD
0x5c04  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5c09  brfalse.s loc_5C11
0x5c0b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5c10  throw
0x5c11  ldarg.0
0x5c12  ldstr    aTargeturlforch// "TargetUrlForChildTerms"
0x5c17  ldarg.s  4
0x5c19  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c1e  ldc.i4.1
0x5c1f  stloc.0
0x5c20  ldarg.0
0x5c21  ldarg.1
0x5c22  ldloc.1
0x5c23  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_TargetUrlForChildTerms()
0x5c28  ldarg.3
0x5c29  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x5c2e  ldarg.s  4
0x5c30  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c35  br       loc_5D7D
0x5c3a  ldarg.3
0x5c3b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c40  stloc.s  0xE
0x5c42  ldloca.s 0xE
0x5c44  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5c49  brfalse.s loc_5C62
0x5c4b  ldarg.3
0x5c4c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c51  stloc.s  0xF
0x5c53  ldloca.s 0xF
0x5c55  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5c5a  brtrue.s loc_5C62
0x5c5c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5c61  throw
0x5c62  ldarg.0
0x5c63  ldstr    aTaxonomyname// "TaxonomyName"
0x5c68  ldarg.s  4
0x5c6a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c6f  ldc.i4.1
0x5c70  stloc.0
0x5c71  ldarg.1
0x5c72  ldloc.1
0x5c73  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_TaxonomyName()
0x5c78  ldarg.s  4
0x5c7a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c7f  br       loc_5D7D
0x5c84  ldarg.3
0x5c85  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c8a  stloc.s  0x10
0x5c8c  ldloca.s 0x10
0x5c8e  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5c93  brfalse.s loc_5CAC
0x5c95  ldarg.3
0x5c96  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c9b  stloc.s  0x11
0x5c9d  ldloca.s 0x11
0x5c9f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5ca4  brfalse.s loc_5CAC
0x5ca6  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5cab  throw
0x5cac  ldarg.0
0x5cad  ldstr    aTerms// "Terms"
0x5cb2  ldarg.s  4
0x5cb4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cb9  ldc.i4.1
0x5cba  stloc.0
0x5cbb  ldarg.0
0x5cbc  ldarg.1
0x5cbd  ldloc.1
0x5cbe  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermCollectionCsom [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_TermsCsom()
0x5cc3  ldarg.3
0x5cc4  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x5cc9  ldarg.s  4
0x5ccb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cd0  br       loc_5D7D
0x5cd5  ldarg.3
0x5cd6  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5cdb  stloc.s  0x12
0x5cdd  ldloca.s 0x12
0x5cdf  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5ce4  brfalse.s loc_5CFD
0x5ce6  ldarg.3
0x5ce7  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5cec  stloc.s  0x13
0x5cee  ldloca.s 0x13
0x5cf0  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5cf5  brfalse.s loc_5CFD
0x5cf7  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5cfc  throw
0x5cfd  ldarg.0
0x5cfe  ldstr    aTitle// "Title"
0x5d03  ldarg.s  4
0x5d05  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5d0a  ldc.i4.1
0x5d0b  stloc.0
0x5d0c  ldarg.0
0x5d0d  ldarg.1
0x5d0e  ldloc.1
0x5d0f  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_Title()
0x5d14  ldarg.3
0x5d15  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x5d1a  ldarg.s  4
0x5d1c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5d21  br.s     loc_5D7D
0x5d23  ldarg.3
0x5d24  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5d29  stloc.s  0x14
0x5d2b  ldloca.s 0x14
0x5d2d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5d32  brfalse.s loc_5D4B
0x5d34  ldarg.3
0x5d35  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5d3a  stloc.s  0x15
0x5d3c  ldloca.s 0x15
0x5d3e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5d43  brfalse.s loc_5D4B
0x5d45  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
  ... truncated ...
```
