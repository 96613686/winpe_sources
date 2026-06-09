# <GetProperties>d__18::MoveNext

- ea: `0x1a0e0`
- end: `0x1a96b`
- name: `<GetProperties>d__18::MoveNext`
- size: `2187`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x60f0`
- `0x1a0e0`
- `0x1a990`
- `0x1a9f0`

## string_xrefs

- `0x1a377`: `IsReadOnly`
- `0x1a3e9`: `IsReadOnly`
- `0x1a455`: `LinkType`
- `0x1a4c7`: `LinkType`

## pseudocode

```c

```

## disassembly

```asm
0x1a0e0  ldarg.0
0x1a0e1  ldfld    int32 <GetProperties>d__18::<>1__state
0x1a0e6  stloc.1
0x1a0e7  ldloc.1
0x1a0e8  switch   loc_1A122, loc_1A95E, loc_1A18C, loc_1A278, loc_1A35E, loc_1A43C, loc_1A51A, loc_1A5F3, loc_1A6CC, loc_1A7A6, loc_1A880, loc_1A957
0x1a11d  br       loc_1A95E
0x1a122  ldarg.0
0x1a123  ldc.i4.m1
0x1a124  stfld    int32 <GetProperties>d__18::<>1__state
0x1a129  ldarg.0
0x1a12a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__18::proxyContext
0x1a12f  brtrue.s loc_1A13C
0x1a131  ldstr    aProxycontext// "proxyContext"
0x1a136  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1a13b  throw
0x1a13c  ldarg.0
0x1a13d  ldarg.0
0x1a13e  ldfld    class Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub <GetProperties>d__18::<>4__this
0x1a143  ldarg.0
0x1a144  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__18::proxyContext
0x1a149  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::<>n__FabricatedMethod1c(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x1a14e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x1a153  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__18::<>7__wrap1a
0x1a158  ldarg.0
0x1a159  ldc.i4.1
0x1a15a  stfld    int32 <GetProperties>d__18::<>1__state
0x1a15f  br.s     loc_1A193
0x1a161  ldarg.0
0x1a162  ldarg.0
0x1a163  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__18::<>7__wrap1a
0x1a168  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x1a16d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<item>5__19
0x1a172  ldarg.0
0x1a173  ldarg.0
0x1a174  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<item>5__19
0x1a179  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>2__current
0x1a17e  ldarg.0
0x1a17f  ldc.i4.2
0x1a180  stfld    int32 <GetProperties>d__18::<>1__state
0x1a185  ldc.i4.1
0x1a186  stloc.0
0x1a187  leave    loc_1A969
0x1a18c  ldarg.0
0x1a18d  ldc.i4.1
0x1a18e  stfld    int32 <GetProperties>d__18::<>1__state
0x1a193  ldarg.0
0x1a194  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__18::<>7__wrap1a
0x1a199  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a19e  brtrue.s loc_1A161
0x1a1a0  ldarg.0
0x1a1a1  call     instance void <GetProperties>d__18::<>m__Finally1b()
0x1a1a6  ldarg.0
0x1a1a7  ldarg.0
0x1a1a8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a1ad  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocalf
0x1a1b2  ldarg.0
0x1a1b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocalf
0x1a1b8  ldstr    aCatalogtargetu// "CatalogTargetUrlForChildTerms"
0x1a1bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a1c2  ldarg.0
0x1a1c3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocalf
0x1a1c8  ldc.i4.0
0x1a1c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a1ce  ldarg.0
0x1a1cf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocalf
0x1a1d4  ldc.i4.4
0x1a1d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a1da  ldarg.0
0x1a1db  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocalf
0x1a1e0  ldc.i4.0
0x1a1e1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1a1e6  ldarg.0
0x1a1e7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocalf
0x1a1ec  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString
0x1a1f1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a1f6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1a1fb  ldarg.0
0x1a1fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocalf
0x1a201  ldc.i4.1
0x1a202  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1a207  ldarg.0
0x1a208  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocalf
0x1a20d  ldc.i4.1
0x1a20e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1a213  ldarg.0
0x1a214  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocalf
0x1a219  ldnull
0x1a21a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1a21f  ldarg.0
0x1a220  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocalf
0x1a225  ldstr    aCatalogtargetu// "CatalogTargetUrlForChildTerms"
0x1a22a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1a22f  ldarg.0
0x1a230  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocalf
0x1a235  ldnull
0x1a236  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1a23b  ldarg.0
0x1a23c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocalf
0x1a241  ldc.i4.0
0x1a242  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1a247  ldarg.0
0x1a248  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocalf
0x1a24d  ldc.i4.0
0x1a24e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1a253  ldarg.0
0x1a254  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocalf
0x1a259  ldc.i4.0
0x1a25a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1a25f  ldarg.0
0x1a260  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocalf
0x1a265  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>2__current
0x1a26a  ldarg.0
0x1a26b  ldc.i4.3
0x1a26c  stfld    int32 <GetProperties>d__18::<>1__state
0x1a271  ldc.i4.1
0x1a272  stloc.0
0x1a273  leave    loc_1A969
0x1a278  ldarg.0
0x1a279  ldc.i4.m1
0x1a27a  stfld    int32 <GetProperties>d__18::<>1__state
0x1a27f  ldarg.0
0x1a280  ldarg.0
0x1a281  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a286  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal10
0x1a28b  ldarg.0
0x1a28c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal10
0x1a291  ldstr    aId// "Id"
0x1a296  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a29b  ldarg.0
0x1a29c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal10
0x1a2a1  ldc.i4.0
0x1a2a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a2a7  ldarg.0
0x1a2a8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal10
0x1a2ad  ldc.i4.1
0x1a2ae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a2b3  ldarg.0
0x1a2b4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal10
0x1a2b9  ldc.i4.0
0x1a2ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1a2bf  ldarg.0
0x1a2c0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal10
0x1a2c5  ldtoken  [mscorlib]System.Guid
0x1a2ca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a2cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1a2d4  ldarg.0
0x1a2d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal10
0x1a2da  ldc.i4.1
0x1a2db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1a2e0  ldarg.0
0x1a2e1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal10
0x1a2e6  ldc.i4.1
0x1a2e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1a2ec  ldarg.0
0x1a2ed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal10
0x1a2f2  ldloca.s 2
0x1a2f4  initobj  [mscorlib]System.Guid
0x1a2fa  ldloc.2
0x1a2fb  box      [mscorlib]System.Guid
0x1a300  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1a305  ldarg.0
0x1a306  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal10
0x1a30b  ldstr    aId// "Id"
0x1a310  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1a315  ldarg.0
0x1a316  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal10
0x1a31b  ldnull
0x1a31c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1a321  ldarg.0
0x1a322  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal10
0x1a327  ldc.i4.0
0x1a328  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1a32d  ldarg.0
0x1a32e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal10
0x1a333  ldc.i4.0
0x1a334  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1a339  ldarg.0
0x1a33a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal10
0x1a33f  ldc.i4.0
0x1a340  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1a345  ldarg.0
0x1a346  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal10
0x1a34b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>2__current
0x1a350  ldarg.0
0x1a351  ldc.i4.4
0x1a352  stfld    int32 <GetProperties>d__18::<>1__state
0x1a357  ldc.i4.1
0x1a358  stloc.0
0x1a359  leave    loc_1A969
0x1a35e  ldarg.0
0x1a35f  ldc.i4.m1
0x1a360  stfld    int32 <GetProperties>d__18::<>1__state
0x1a365  ldarg.0
0x1a366  ldarg.0
0x1a367  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a36c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal11
0x1a371  ldarg.0
0x1a372  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal11
0x1a377  ldstr    aIsreadonly// "IsReadOnly"
0x1a37c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a381  ldarg.0
0x1a382  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal11
0x1a387  ldc.i4.0
0x1a388  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a38d  ldarg.0
0x1a38e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal11
0x1a393  ldc.i4.1
0x1a394  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a399  ldarg.0
0x1a39a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal11
0x1a39f  ldc.i4.0
0x1a3a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1a3a5  ldarg.0
0x1a3a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal11
0x1a3ab  ldtoken  [mscorlib]System.Boolean
0x1a3b0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a3b5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1a3ba  ldarg.0
0x1a3bb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal11
0x1a3c0  ldc.i4.1
0x1a3c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1a3c6  ldarg.0
0x1a3c7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal11
0x1a3cc  ldc.i4.1
0x1a3cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1a3d2  ldarg.0
0x1a3d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal11
0x1a3d8  ldc.i4.0
0x1a3d9  box      [mscorlib]System.Boolean
0x1a3de  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1a3e3  ldarg.0
0x1a3e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal11
0x1a3e9  ldstr    aIsreadonly// "IsReadOnly"
0x1a3ee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1a3f3  ldarg.0
0x1a3f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal11
0x1a3f9  ldnull
0x1a3fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1a3ff  ldarg.0
0x1a400  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal11
0x1a405  ldc.i4.0
0x1a406  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1a40b  ldarg.0
0x1a40c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal11
0x1a411  ldc.i4.0
0x1a412  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1a417  ldarg.0
0x1a418  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal11
0x1a41d  ldc.i4.0
0x1a41e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1a423  ldarg.0
0x1a424  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal11
0x1a429  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>2__current
0x1a42e  ldarg.0
0x1a42f  ldc.i4.5
0x1a430  stfld    int32 <GetProperties>d__18::<>1__state
0x1a435  ldc.i4.1
0x1a436  stloc.0
0x1a437  leave    loc_1A969
0x1a43c  ldarg.0
0x1a43d  ldc.i4.m1
0x1a43e  stfld    int32 <GetProperties>d__18::<>1__state
0x1a443  ldarg.0
0x1a444  ldarg.0
0x1a445  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a44a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal12
0x1a44f  ldarg.0
0x1a450  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal12
0x1a455  ldstr    aLinktype// "LinkType"
0x1a45a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a45f  ldarg.0
0x1a460  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal12
0x1a465  ldc.i4.0
0x1a466  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a46b  ldarg.0
0x1a46c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal12
0x1a471  ldc.i4.1
0x1a472  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a477  ldarg.0
0x1a478  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal12
0x1a47d  ldc.i4.0
0x1a47e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1a483  ldarg.0
0x1a484  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal12
0x1a489  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationLinkType
0x1a48e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a493  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1a498  ldarg.0
0x1a499  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal12
0x1a49e  ldc.i4.0
0x1a49f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1a4a4  ldarg.0
0x1a4a5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal12
0x1a4aa  ldc.i4.1
0x1a4ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1a4b0  ldarg.0
0x1a4b1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__18::<>g__initLocal12
0x1a4b6  ldc.i4.0
0x1a4b7  box      [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationLinkType
0x1a4bc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
  ... truncated ...
```
