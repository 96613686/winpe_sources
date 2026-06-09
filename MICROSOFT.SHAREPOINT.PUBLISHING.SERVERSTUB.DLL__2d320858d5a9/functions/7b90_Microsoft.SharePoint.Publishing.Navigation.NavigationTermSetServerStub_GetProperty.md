# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetServerStub::GetProperty

- ea: `0x7b90`
- end: `0x7d02`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetServerStub::GetProperty`
- size: `370`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x5750`
- `0x7b90`

## string_xrefs

- `0x7bfb`: `LinkType`
- `0x7c99`: `LinkType`

## pseudocode

```c

```

## disassembly

```asm
0x7b90  ldarg.2
0x7b91  brtrue.s loc_7B9E
0x7b93  ldstr    aPropname// "propName"
0x7b98  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7b9d  throw
0x7b9e  ldarg.3
0x7b9f  brtrue.s loc_7BAC
0x7ba1  ldstr    aProxycontext// "proxyContext"
0x7ba6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7bab  throw
0x7bac  ldarg.1
0x7bad  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet
0x7bb2  stloc.0
0x7bb3  ldloc.0
0x7bb4  brtrue.s loc_7BC1
0x7bb6  ldstr    aTarget// "target"
0x7bbb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7bc0  throw
0x7bc1  ldarg.0
0x7bc2  ldarg.2
0x7bc3  ldarg.3
0x7bc4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7bc9  starg.s  2
0x7bcb  ldarg.2
0x7bcc  dup
0x7bcd  stloc.1
0x7bce  brfalse  loc_7CF8
0x7bd3  volatile.
0x7bd5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600012a-1
0x7bda  brtrue.s loc_7C31
0x7bdc  ldc.i4.6
0x7bdd  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x7be2  dup
0x7be3  ldstr    aIsnavigationte// "IsNavigationTermSet"
0x7be8  ldc.i4.0
0x7be9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7bee  dup
0x7bef  ldstr    aLcid// "Lcid"
0x7bf4  ldc.i4.1
0x7bf5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7bfa  dup
0x7bfb  ldstr    aLinktype// "LinkType"
0x7c00  ldc.i4.2
0x7c01  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7c06  dup
0x7c07  ldstr    aLoadedfrompers// "LoadedFromPersistedData"
0x7c0c  ldc.i4.3
0x7c0d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7c12  dup
0x7c13  ldstr    aTermgroupid// "TermGroupId"
0x7c18  ldc.i4.4
0x7c19  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7c1e  dup
0x7c1f  ldstr    aTermstoreid// "TermStoreId"
0x7c24  ldc.i4.5
0x7c25  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7c2a  volatile.
0x7c2c  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600012a-1
0x7c31  volatile.
0x7c33  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600012a-1
0x7c38  ldloc.1
0x7c39  ldloca.s 2
0x7c3b  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x7c40  brfalse  loc_7CF8
0x7c45  ldloc.2
0x7c46  switch   loc_7C68, loc_7C80, loc_7C98, loc_7CB0, loc_7CC8, loc_7CE0
0x7c63  br       loc_7CF8
0x7c68  ldarg.0
0x7c69  ldstr    aIsnavigationte// "IsNavigationTermSet"
0x7c6e  ldarg.3
0x7c6f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7c74  ldloc.0
0x7c75  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet::get_IsNavigationTermSet()
0x7c7a  box      [mscorlib]System.Boolean
0x7c7f  ret
0x7c80  ldarg.0
0x7c81  ldstr    aLcid// "Lcid"
0x7c86  ldarg.3
0x7c87  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7c8c  ldloc.0
0x7c8d  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet::get_Lcid()
0x7c92  box      [mscorlib]System.Int32
0x7c97  ret
0x7c98  ldarg.0
0x7c99  ldstr    aLinktype// "LinkType"
0x7c9e  ldarg.3
0x7c9f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7ca4  ldloc.0
0x7ca5  callvirt instance valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationLinkType [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_LinkType()
0x7caa  box      [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationLinkType
0x7caf  ret
0x7cb0  ldarg.0
0x7cb1  ldstr    aLoadedfrompers// "LoadedFromPersistedData"
0x7cb6  ldarg.3
0x7cb7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7cbc  ldloc.0
0x7cbd  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet::get_LoadedFromPersistedData()
0x7cc2  box      [mscorlib]System.Boolean
0x7cc7  ret
0x7cc8  ldarg.0
0x7cc9  ldstr    aTermgroupid// "TermGroupId"
0x7cce  ldarg.3
0x7ccf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7cd4  ldloc.0
0x7cd5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet::get_TermGroupId()
0x7cda  box      [mscorlib]System.Guid
0x7cdf  ret
0x7ce0  ldarg.0
0x7ce1  ldstr    aTermstoreid// "TermStoreId"
0x7ce6  ldarg.3
0x7ce7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7cec  ldloc.0
0x7ced  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet::get_TermStoreId()
0x7cf2  box      [mscorlib]System.Guid
0x7cf7  ret
0x7cf8  ldarg.0
0x7cf9  ldarg.1
0x7cfa  ldarg.2
0x7cfb  ldarg.3
0x7cfc  call     instance object Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::GetProperty(object target, string propName, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7d01  ret
```
