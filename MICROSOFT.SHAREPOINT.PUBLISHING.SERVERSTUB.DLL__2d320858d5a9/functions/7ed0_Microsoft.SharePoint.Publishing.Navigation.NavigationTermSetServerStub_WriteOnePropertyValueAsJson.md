# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetServerStub::WriteOnePropertyValueAsJson

- ea: `0x7ed0`
- end: `0x80bc`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetServerStub::WriteOnePropertyValueAsJson`
- size: `492`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x59d0`
- `0x7ed0`

## pseudocode

```c

```

## disassembly

```asm
0x7ed0  ldc.i4.0
0x7ed1  stloc.0
0x7ed2  ldarg.2
0x7ed3  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet
0x7ed8  stloc.1
0x7ed9  ldloc.1
0x7eda  brtrue.s loc_7EE7
0x7edc  ldstr    aTarget// "target"
0x7ee1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7ee6  throw
0x7ee7  ldarg.3
0x7ee8  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x7eed  dup
0x7eee  stloc.2
0x7eef  brfalse  loc_80AE
0x7ef4  ldloc.2
0x7ef5  ldstr    aIsnavigationte// "IsNavigationTermSet"
0x7efa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7eff  brtrue.s loc_7F43
0x7f01  ldloc.2
0x7f02  ldstr    aLcid// "Lcid"
0x7f07  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7f0c  brtrue.s loc_7F8C
0x7f0e  ldloc.2
0x7f0f  ldstr    aLoadedfrompers// "LoadedFromPersistedData"
0x7f14  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7f19  brtrue   loc_7FD6
0x7f1e  ldloc.2
0x7f1f  ldstr    aTermgroupid// "TermGroupId"
0x7f24  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7f29  brtrue   loc_8020
0x7f2e  ldloc.2
0x7f2f  ldstr    aTermstoreid// "TermStoreId"
0x7f34  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7f39  brtrue   loc_8067
0x7f3e  br       loc_80AE
0x7f43  ldarg.3
0x7f44  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x7f49  stloc.3
0x7f4a  ldloca.s 3
0x7f4c  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x7f51  brfalse.s loc_7F6A
0x7f53  ldarg.3
0x7f54  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x7f59  stloc.s  4
0x7f5b  ldloca.s 4
0x7f5d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x7f62  brtrue.s loc_7F6A
0x7f64  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x7f69  throw
0x7f6a  ldarg.0
0x7f6b  ldstr    aIsnavigationte// "IsNavigationTermSet"
0x7f70  ldarg.s  4
0x7f72  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7f77  ldc.i4.1
0x7f78  stloc.0
0x7f79  ldarg.1
0x7f7a  ldloc.1
0x7f7b  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet::get_IsNavigationTermSet()
0x7f80  ldarg.s  4
0x7f82  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7f87  br       loc_80BA
0x7f8c  ldarg.3
0x7f8d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x7f92  stloc.s  5
0x7f94  ldloca.s 5
0x7f96  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x7f9b  brfalse.s loc_7FB4
0x7f9d  ldarg.3
0x7f9e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x7fa3  stloc.s  6
0x7fa5  ldloca.s 6
0x7fa7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x7fac  brtrue.s loc_7FB4
0x7fae  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x7fb3  throw
0x7fb4  ldarg.0
0x7fb5  ldstr    aLcid// "Lcid"
0x7fba  ldarg.s  4
0x7fbc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7fc1  ldc.i4.1
0x7fc2  stloc.0
0x7fc3  ldarg.1
0x7fc4  ldloc.1
0x7fc5  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet::get_Lcid()
0x7fca  ldarg.s  4
0x7fcc  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7fd1  br       loc_80BA
0x7fd6  ldarg.3
0x7fd7  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x7fdc  stloc.s  7
0x7fde  ldloca.s 7
0x7fe0  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x7fe5  brfalse.s loc_7FFE
0x7fe7  ldarg.3
0x7fe8  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x7fed  stloc.s  8
0x7fef  ldloca.s 8
0x7ff1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x7ff6  brtrue.s loc_7FFE
0x7ff8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x7ffd  throw
0x7ffe  ldarg.0
0x7fff  ldstr    aLoadedfrompers// "LoadedFromPersistedData"
0x8004  ldarg.s  4
0x8006  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x800b  ldc.i4.1
0x800c  stloc.0
0x800d  ldarg.1
0x800e  ldloc.1
0x800f  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet::get_LoadedFromPersistedData()
0x8014  ldarg.s  4
0x8016  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x801b  br       loc_80BA
0x8020  ldarg.3
0x8021  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8026  stloc.s  9
0x8028  ldloca.s 9
0x802a  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x802f  brfalse.s loc_8048
0x8031  ldarg.3
0x8032  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8037  stloc.s  0xA
0x8039  ldloca.s 0xA
0x803b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x8040  brtrue.s loc_8048
0x8042  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x8047  throw
0x8048  ldarg.0
0x8049  ldstr    aTermgroupid// "TermGroupId"
0x804e  ldarg.s  4
0x8050  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8055  ldc.i4.1
0x8056  stloc.0
0x8057  ldarg.1
0x8058  ldloc.1
0x8059  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet::get_TermGroupId()
0x805e  ldarg.s  4
0x8060  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8065  br.s     loc_80BA
0x8067  ldarg.3
0x8068  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x806d  stloc.s  0xB
0x806f  ldloca.s 0xB
0x8071  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x8076  brfalse.s loc_808F
0x8078  ldarg.3
0x8079  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x807e  stloc.s  0xC
0x8080  ldloca.s 0xC
0x8082  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x8087  brtrue.s loc_808F
0x8089  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x808e  throw
0x808f  ldarg.0
0x8090  ldstr    aTermstoreid// "TermStoreId"
0x8095  ldarg.s  4
0x8097  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x809c  ldc.i4.1
0x809d  stloc.0
0x809e  ldarg.1
0x809f  ldloc.1
0x80a0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet::get_TermStoreId()
0x80a5  ldarg.s  4
0x80a7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80ac  br.s     loc_80BA
0x80ae  ldarg.0
0x80af  ldarg.1
0x80b0  ldarg.2
0x80b1  ldarg.3
0x80b2  ldarg.s  4
0x80b4  call     instance bool Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::WriteOnePropertyValueAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter writer, object target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty field, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x80b9  stloc.0
0x80ba  ldloc.0
0x80bb  ret
```
