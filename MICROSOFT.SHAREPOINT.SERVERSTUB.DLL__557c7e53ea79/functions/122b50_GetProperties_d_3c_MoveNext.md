# <GetProperties>d__3c::MoveNext

- ea: `0x122b50`
- end: `0x124e2d`
- name: `<GetProperties>d__3c::MoveNext`
- size: `8925`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x4dbd0`
- `0x122b50`
- `0x124e50`
- `0x124eb0`

## string_xrefs

- `0x12415b`: `SchemaXml`
- `0x1241c8`: `SchemaXml`
- `0x123d05`: `JSLink`
- `0x123d72`: `JSLink`
- `0x124235`: `SchemaXmlWithResourceTokens`
- `0x1242a2`: `SchemaXmlWithResourceTokens`
- `0x122e5c`: `ClientSideComponentId`
- `0x122ed6`: `ClientSideComponentId`
- `0x122f42`: `ClientSideComponentProperties`
- `0x122faf`: `ClientSideComponentProperties`
- `0x122d7e`: `CanBeDeleted`
- `0x122df0`: `CanBeDeleted`
- `0x123f9d`: `ReadOnlyField`
- `0x12400f`: `ReadOnlyField`

## pseudocode

```c

```

## disassembly

```asm
0x122b50  ldarg.0
0x122b51  ldfld    int32 <GetProperties>d__3c::<>1__state
0x122b56  stloc.1
0x122b57  ldloc.1
0x122b58  switch   loc_122C0A, loc_124E20, loc_122C74, loc_122D65, loc_122E43, loc_122F29, loc_123002, loc_1230DB, loc_1231B4, loc_12328E, loc_123368, loc_123442, loc_12351C, loc_1235FB, loc_1236D5, loc_1237B4, loc_123893, loc_12396D, loc_123A4C, loc_123B33, loc_123C12, loc_123CEC, loc_123DC6, loc_123EA5, loc_123F84, loc_124063, loc_124142, loc_12421C, loc_1242F6, loc_1243D0, loc_1244AF, loc_12458E, loc_12466D, loc_124747, loc_124821, loc_1248FB, loc_1249DA, loc_124AB4, loc_124B8E, loc_124C68, loc_124D42, loc_124E19
0x122c05  br       loc_124E20
0x122c0a  ldarg.0
0x122c0b  ldc.i4.m1
0x122c0c  stfld    int32 <GetProperties>d__3c::<>1__state
0x122c11  ldarg.0
0x122c12  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__3c::proxyContext
0x122c17  brtrue.s loc_122C24
0x122c19  ldstr    aProxycontext// "proxyContext"
0x122c1e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x122c23  throw
0x122c24  ldarg.0
0x122c25  ldarg.0
0x122c26  ldfld    class Microsoft.SharePoint.ServerStub.SPFieldServerStub <GetProperties>d__3c::<>4__this
0x122c2b  ldarg.0
0x122c2c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__3c::proxyContext
0x122c31  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPFieldServerStub::<>n__FabricatedMethod40(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x122c36  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x122c3b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3c::<>7__wrap3e
0x122c40  ldarg.0
0x122c41  ldc.i4.1
0x122c42  stfld    int32 <GetProperties>d__3c::<>1__state
0x122c47  br.s     loc_122C7B
0x122c49  ldarg.0
0x122c4a  ldarg.0
0x122c4b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3c::<>7__wrap3e
0x122c50  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x122c55  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<item>5__3d
0x122c5a  ldarg.0
0x122c5b  ldarg.0
0x122c5c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<item>5__3d
0x122c61  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>2__current
0x122c66  ldarg.0
0x122c67  ldc.i4.2
0x122c68  stfld    int32 <GetProperties>d__3c::<>1__state
0x122c6d  ldc.i4.1
0x122c6e  stloc.0
0x122c6f  leave    loc_124E2B
0x122c74  ldarg.0
0x122c75  ldc.i4.1
0x122c76  stfld    int32 <GetProperties>d__3c::<>1__state
0x122c7b  ldarg.0
0x122c7c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3c::<>7__wrap3e
0x122c81  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x122c86  brtrue.s loc_122C49
0x122c88  ldarg.0
0x122c89  call     instance void <GetProperties>d__3c::<>m__Finally3f()
0x122c8e  ldarg.0
0x122c8f  ldarg.0
0x122c90  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x122c95  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal15
0x122c9a  ldarg.0
0x122c9b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal15
0x122ca0  ldstr    aAutoindexed// "AutoIndexed"
0x122ca5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x122caa  ldarg.0
0x122cab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal15
0x122cb0  ldc.i4.0
0x122cb1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x122cb6  ldarg.0
0x122cb7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal15
0x122cbc  ldc.i4.1
0x122cbd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x122cc2  ldarg.0
0x122cc3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal15
0x122cc8  ldc.i4.0
0x122cc9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x122cce  ldarg.0
0x122ccf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal15
0x122cd4  ldtoken  [mscorlib]System.Boolean
0x122cd9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x122cde  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x122ce3  ldarg.0
0x122ce4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal15
0x122ce9  ldc.i4.1
0x122cea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x122cef  ldarg.0
0x122cf0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal15
0x122cf5  ldc.i4.1
0x122cf6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x122cfb  ldarg.0
0x122cfc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal15
0x122d01  ldc.i4.0
0x122d02  box      [mscorlib]System.Boolean
0x122d07  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x122d0c  ldarg.0
0x122d0d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal15
0x122d12  ldstr    aAutoindexed// "AutoIndexed"
0x122d17  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x122d1c  ldarg.0
0x122d1d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal15
0x122d22  ldnull
0x122d23  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x122d28  ldarg.0
0x122d29  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal15
0x122d2e  ldc.i4.0
0x122d2f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x122d34  ldarg.0
0x122d35  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal15
0x122d3a  ldc.i4.0
0x122d3b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x122d40  ldarg.0
0x122d41  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal15
0x122d46  ldc.i4.0
0x122d47  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x122d4c  ldarg.0
0x122d4d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal15
0x122d52  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>2__current
0x122d57  ldarg.0
0x122d58  ldc.i4.3
0x122d59  stfld    int32 <GetProperties>d__3c::<>1__state
0x122d5e  ldc.i4.1
0x122d5f  stloc.0
0x122d60  leave    loc_124E2B
0x122d65  ldarg.0
0x122d66  ldc.i4.m1
0x122d67  stfld    int32 <GetProperties>d__3c::<>1__state
0x122d6c  ldarg.0
0x122d6d  ldarg.0
0x122d6e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x122d73  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal16
0x122d78  ldarg.0
0x122d79  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal16
0x122d7e  ldstr    aCanbedeleted// "CanBeDeleted"
0x122d83  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x122d88  ldarg.0
0x122d89  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal16
0x122d8e  ldc.i4.0
0x122d8f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x122d94  ldarg.0
0x122d95  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal16
0x122d9a  ldc.i4.1
0x122d9b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x122da0  ldarg.0
0x122da1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal16
0x122da6  ldc.i4.0
0x122da7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x122dac  ldarg.0
0x122dad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal16
0x122db2  ldtoken  [mscorlib]System.Boolean
0x122db7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x122dbc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x122dc1  ldarg.0
0x122dc2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal16
0x122dc7  ldc.i4.1
0x122dc8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x122dcd  ldarg.0
0x122dce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal16
0x122dd3  ldc.i4.1
0x122dd4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x122dd9  ldarg.0
0x122dda  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal16
0x122ddf  ldc.i4.0
0x122de0  box      [mscorlib]System.Boolean
0x122de5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x122dea  ldarg.0
0x122deb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal16
0x122df0  ldstr    aCanbedeleted// "CanBeDeleted"
0x122df5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x122dfa  ldarg.0
0x122dfb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal16
0x122e00  ldnull
0x122e01  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x122e06  ldarg.0
0x122e07  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal16
0x122e0c  ldc.i4.0
0x122e0d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x122e12  ldarg.0
0x122e13  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal16
0x122e18  ldc.i4.0
0x122e19  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x122e1e  ldarg.0
0x122e1f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal16
0x122e24  ldc.i4.0
0x122e25  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x122e2a  ldarg.0
0x122e2b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal16
0x122e30  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>2__current
0x122e35  ldarg.0
0x122e36  ldc.i4.4
0x122e37  stfld    int32 <GetProperties>d__3c::<>1__state
0x122e3c  ldc.i4.1
0x122e3d  stloc.0
0x122e3e  leave    loc_124E2B
0x122e43  ldarg.0
0x122e44  ldc.i4.m1
0x122e45  stfld    int32 <GetProperties>d__3c::<>1__state
0x122e4a  ldarg.0
0x122e4b  ldarg.0
0x122e4c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x122e51  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal17
0x122e56  ldarg.0
0x122e57  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal17
0x122e5c  ldstr    aClientsidecomp// "ClientSideComponentId"
0x122e61  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x122e66  ldarg.0
0x122e67  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal17
0x122e6c  ldc.i4.0
0x122e6d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x122e72  ldarg.0
0x122e73  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal17
0x122e78  ldc.i4.1
0x122e79  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x122e7e  ldarg.0
0x122e7f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal17
0x122e84  ldc.i4.0
0x122e85  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x122e8a  ldarg.0
0x122e8b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal17
0x122e90  ldtoken  [mscorlib]System.Guid
0x122e95  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x122e9a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x122e9f  ldarg.0
0x122ea0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal17
0x122ea5  ldc.i4.0
0x122ea6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x122eab  ldarg.0
0x122eac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal17
0x122eb1  ldc.i4.1
0x122eb2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x122eb7  ldarg.0
0x122eb8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal17
0x122ebd  ldloca.s 2
0x122ebf  initobj  [mscorlib]System.Guid
0x122ec5  ldloc.2
0x122ec6  box      [mscorlib]System.Guid
0x122ecb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x122ed0  ldarg.0
0x122ed1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal17
0x122ed6  ldstr    aClientsidecomp// "ClientSideComponentId"
0x122edb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x122ee0  ldarg.0
0x122ee1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal17
0x122ee6  ldnull
0x122ee7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x122eec  ldarg.0
0x122eed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal17
0x122ef2  ldc.i4.0
0x122ef3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x122ef8  ldarg.0
0x122ef9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal17
0x122efe  ldc.i4.1
0x122eff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x122f04  ldarg.0
0x122f05  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal17
0x122f0a  ldc.i4.0
0x122f0b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x122f10  ldarg.0
0x122f11  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal17
0x122f16  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>2__current
0x122f1b  ldarg.0
0x122f1c  ldc.i4.5
0x122f1d  stfld    int32 <GetProperties>d__3c::<>1__state
0x122f22  ldc.i4.1
0x122f23  stloc.0
0x122f24  leave    loc_124E2B
0x122f29  ldarg.0
0x122f2a  ldc.i4.m1
0x122f2b  stfld    int32 <GetProperties>d__3c::<>1__state
0x122f30  ldarg.0
0x122f31  ldarg.0
0x122f32  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x122f37  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal18
0x122f3c  ldarg.0
0x122f3d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal18
0x122f42  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x122f47  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x122f4c  ldarg.0
0x122f4d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal18
0x122f52  ldc.i4.0
0x122f53  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x122f58  ldarg.0
0x122f59  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal18
0x122f5e  ldc.i4.1
0x122f5f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x122f64  ldarg.0
0x122f65  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal18
0x122f6a  ldc.i4.0
0x122f6b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x122f70  ldarg.0
0x122f71  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal18
0x122f76  ldtoken  [mscorlib]System.String
0x122f7b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x122f80  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x122f85  ldarg.0
0x122f86  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal18
0x122f8b  ldc.i4.0
0x122f8c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x122f91  ldarg.0
0x122f92  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal18
0x122f97  ldc.i4.1
0x122f98  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x122f9d  ldarg.0
0x122f9e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3c::<>g__initLocal18
0x122fa3  ldnull
0x122fa4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
  ... truncated ...
```
