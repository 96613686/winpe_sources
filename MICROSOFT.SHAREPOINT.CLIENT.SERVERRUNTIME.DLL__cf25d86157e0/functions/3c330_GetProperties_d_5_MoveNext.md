# <GetProperties>d__5::MoveNext

- ea: `0x3c330`
- end: `0x3c83c`
- name: `<GetProperties>d__5::MoveNext`
- size: `1292`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x8b20`
- `0x8b40`
- `0x8b60`
- `0x8b80`
- `0x8ba0`
- `0x8bc0`
- `0x8be0`
- `0x8c00`
- `0x8c20`
- `0x8c40`
- `0x8c80`
- `0x8ca0`
- `0x8cc0`
- `0x8cd0`
- `0x34ba0`
- `0x3c330`
- `0x3c860`
- `0x3c8c0`

## string_xrefs

- `0x3c766`: `ReadOnly`
- `0x3c7d8`: `ReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x3c330  ldarg.0
0x3c331  ldfld    int32 <GetProperties>d__5::<>1__state
0x3c336  stloc.1
0x3c337  ldloc.1
0x3c338  switch   loc_3C362, loc_3C82F, loc_3C3CC, loc_3C4BD, loc_3C59B, loc_3C674, loc_3C74D, loc_3C828
0x3c35d  br       loc_3C82F
0x3c362  ldarg.0
0x3c363  ldc.i4.m1
0x3c364  stfld    int32 <GetProperties>d__5::<>1__state
0x3c369  ldarg.0
0x3c36a  ldfld    class Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__5::proxyContext
0x3c36f  brtrue.s loc_3C37C
0x3c371  ldstr    aProxycontext// "proxyContext"
0x3c376  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3c37b  throw
0x3c37c  ldarg.0
0x3c37d  ldarg.0
0x3c37e  ldfld    class Microsoft.SharePoint.Client.PropertyInformationValueTypeConverter <GetProperties>d__5::<>4__this
0x3c383  ldarg.0
0x3c384  ldfld    class Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__5::proxyContext
0x3c389  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Client.PropertyInformationValueTypeConverter::<>n__FabricatedMethod9(class Microsoft.SharePoint.Client.ProxyContext target)
0x3c38e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x3c393  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__5::<>7__wrap7
0x3c398  ldarg.0
0x3c399  ldc.i4.1
0x3c39a  stfld    int32 <GetProperties>d__5::<>1__state
0x3c39f  br.s     loc_3C3D3
0x3c3a1  ldarg.0
0x3c3a2  ldarg.0
0x3c3a3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__5::<>7__wrap7
0x3c3a8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x3c3ad  stfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<item>5__6
0x3c3b2  ldarg.0
0x3c3b3  ldarg.0
0x3c3b4  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<item>5__6
0x3c3b9  stfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>2__current
0x3c3be  ldarg.0
0x3c3bf  ldc.i4.2
0x3c3c0  stfld    int32 <GetProperties>d__5::<>1__state
0x3c3c5  ldc.i4.1
0x3c3c6  stloc.0
0x3c3c7  leave    loc_3C83A
0x3c3cc  ldarg.0
0x3c3cd  ldc.i4.1
0x3c3ce  stfld    int32 <GetProperties>d__5::<>1__state
0x3c3d3  ldarg.0
0x3c3d4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__5::<>7__wrap7
0x3c3d9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3c3de  brtrue.s loc_3C3A1
0x3c3e0  ldarg.0
0x3c3e1  call     instance void <GetProperties>d__5::<>m__Finally8()
0x3c3e6  ldarg.0
0x3c3e7  ldarg.0
0x3c3e8  newobj   instance void Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x3c3ed  stfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x3c3f2  ldarg.0
0x3c3f3  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x3c3f8  ldstr    aExcludefromdef// "ExcludeFromDefaultRetrieval"
0x3c3fd  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_Name(string value)
0x3c402  ldarg.0
0x3c403  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x3c408  ldc.i4.0
0x3c409  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool value)
0x3c40e  ldarg.0
0x3c40f  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x3c414  ldc.i4.1
0x3c415  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype Microsoft.SharePoint.Client.ODataType value)
0x3c41a  ldarg.0
0x3c41b  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x3c420  ldc.i4.0
0x3c421  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool value)
0x3c426  ldarg.0
0x3c427  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x3c42c  ldtoken  [mscorlib]System.Boolean
0x3c431  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c436  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type value)
0x3c43b  ldarg.0
0x3c43c  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x3c441  ldc.i4.1
0x3c442  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool value)
0x3c447  ldarg.0
0x3c448  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x3c44d  ldc.i4.1
0x3c44e  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool value)
0x3c453  ldarg.0
0x3c454  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x3c459  ldc.i4.0
0x3c45a  box      [mscorlib]System.Boolean
0x3c45f  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object value)
0x3c464  ldarg.0
0x3c465  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x3c46a  ldstr    aExcludefromdef// "ExcludeFromDefaultRetrieval"
0x3c46f  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string value)
0x3c474  ldarg.0
0x3c475  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x3c47a  ldnull
0x3c47b  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type value)
0x3c480  ldarg.0
0x3c481  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x3c486  ldc.i4.0
0x3c487  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype Microsoft.SharePoint.Client.ResourceRight value)
0x3c48c  ldarg.0
0x3c48d  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x3c492  ldc.i4.0
0x3c493  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool value)
0x3c498  ldarg.0
0x3c499  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x3c49e  ldc.i4.0
0x3c49f  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool value)
0x3c4a4  ldarg.0
0x3c4a5  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x3c4aa  stfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>2__current
0x3c4af  ldarg.0
0x3c4b0  ldc.i4.3
0x3c4b1  stfld    int32 <GetProperties>d__5::<>1__state
0x3c4b6  ldc.i4.1
0x3c4b7  stloc.0
0x3c4b8  leave    loc_3C83A
0x3c4bd  ldarg.0
0x3c4be  ldc.i4.m1
0x3c4bf  stfld    int32 <GetProperties>d__5::<>1__state
0x3c4c4  ldarg.0
0x3c4c5  ldarg.0
0x3c4c6  newobj   instance void Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x3c4cb  stfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x3c4d0  ldarg.0
0x3c4d1  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x3c4d6  ldstr    aIsbeta// "IsBeta"
0x3c4db  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_Name(string value)
0x3c4e0  ldarg.0
0x3c4e1  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x3c4e6  ldc.i4.0
0x3c4e7  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool value)
0x3c4ec  ldarg.0
0x3c4ed  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x3c4f2  ldc.i4.1
0x3c4f3  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype Microsoft.SharePoint.Client.ODataType value)
0x3c4f8  ldarg.0
0x3c4f9  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x3c4fe  ldc.i4.0
0x3c4ff  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool value)
0x3c504  ldarg.0
0x3c505  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x3c50a  ldtoken  [mscorlib]System.Boolean
0x3c50f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c514  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type value)
0x3c519  ldarg.0
0x3c51a  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x3c51f  ldc.i4.1
0x3c520  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool value)
0x3c525  ldarg.0
0x3c526  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x3c52b  ldc.i4.1
0x3c52c  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool value)
0x3c531  ldarg.0
0x3c532  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x3c537  ldc.i4.0
0x3c538  box      [mscorlib]System.Boolean
0x3c53d  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object value)
0x3c542  ldarg.0
0x3c543  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x3c548  ldstr    aIsbeta// "IsBeta"
0x3c54d  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string value)
0x3c552  ldarg.0
0x3c553  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x3c558  ldnull
0x3c559  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type value)
0x3c55e  ldarg.0
0x3c55f  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x3c564  ldc.i4.0
0x3c565  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype Microsoft.SharePoint.Client.ResourceRight value)
0x3c56a  ldarg.0
0x3c56b  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x3c570  ldc.i4.0
0x3c571  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool value)
0x3c576  ldarg.0
0x3c577  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x3c57c  ldc.i4.0
0x3c57d  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool value)
0x3c582  ldarg.0
0x3c583  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x3c588  stfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>2__current
0x3c58d  ldarg.0
0x3c58e  ldc.i4.4
0x3c58f  stfld    int32 <GetProperties>d__5::<>1__state
0x3c594  ldc.i4.1
0x3c595  stloc.0
0x3c596  leave    loc_3C83A
0x3c59b  ldarg.0
0x3c59c  ldc.i4.m1
0x3c59d  stfld    int32 <GetProperties>d__5::<>1__state
0x3c5a2  ldarg.0
0x3c5a3  ldarg.0
0x3c5a4  newobj   instance void Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x3c5a9  stfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x3c5ae  ldarg.0
0x3c5af  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x3c5b4  ldstr    aName// "Name"
0x3c5b9  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_Name(string value)
0x3c5be  ldarg.0
0x3c5bf  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x3c5c4  ldc.i4.0
0x3c5c5  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool value)
0x3c5ca  ldarg.0
0x3c5cb  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x3c5d0  ldc.i4.1
0x3c5d1  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype Microsoft.SharePoint.Client.ODataType value)
0x3c5d6  ldarg.0
0x3c5d7  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x3c5dc  ldc.i4.0
0x3c5dd  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool value)
0x3c5e2  ldarg.0
0x3c5e3  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x3c5e8  ldtoken  [mscorlib]System.String
0x3c5ed  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c5f2  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type value)
0x3c5f7  ldarg.0
0x3c5f8  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x3c5fd  ldc.i4.1
0x3c5fe  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool value)
0x3c603  ldarg.0
0x3c604  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x3c609  ldc.i4.1
0x3c60a  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool value)
0x3c60f  ldarg.0
0x3c610  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x3c615  ldnull
0x3c616  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object value)
0x3c61b  ldarg.0
0x3c61c  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x3c621  ldstr    aName// "Name"
0x3c626  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string value)
0x3c62b  ldarg.0
0x3c62c  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x3c631  ldnull
0x3c632  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type value)
0x3c637  ldarg.0
0x3c638  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x3c63d  ldc.i4.0
0x3c63e  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype Microsoft.SharePoint.Client.ResourceRight value)
0x3c643  ldarg.0
0x3c644  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x3c649  ldc.i4.0
0x3c64a  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool value)
0x3c64f  ldarg.0
0x3c650  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x3c655  ldc.i4.0
0x3c656  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool value)
0x3c65b  ldarg.0
0x3c65c  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x3c661  stfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>2__current
0x3c666  ldarg.0
0x3c667  ldc.i4.5
0x3c668  stfld    int32 <GetProperties>d__5::<>1__state
0x3c66d  ldc.i4.1
0x3c66e  stloc.0
0x3c66f  leave    loc_3C83A
0x3c674  ldarg.0
0x3c675  ldc.i4.m1
0x3c676  stfld    int32 <GetProperties>d__5::<>1__state
0x3c67b  ldarg.0
0x3c67c  ldarg.0
0x3c67d  newobj   instance void Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x3c682  stfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x3c687  ldarg.0
0x3c688  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x3c68d  ldstr    aPropertytypefu// "PropertyTypeFullName"
0x3c692  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_Name(string value)
0x3c697  ldarg.0
0x3c698  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x3c69d  ldc.i4.0
0x3c69e  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool value)
0x3c6a3  ldarg.0
0x3c6a4  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x3c6a9  ldc.i4.1
0x3c6aa  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype Microsoft.SharePoint.Client.ODataType value)
0x3c6af  ldarg.0
0x3c6b0  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x3c6b5  ldc.i4.0
0x3c6b6  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool value)
0x3c6bb  ldarg.0
0x3c6bc  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x3c6c1  ldtoken  [mscorlib]System.String
0x3c6c6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c6cb  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type value)
0x3c6d0  ldarg.0
0x3c6d1  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x3c6d6  ldc.i4.1
0x3c6d7  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool value)
0x3c6dc  ldarg.0
0x3c6dd  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x3c6e2  ldc.i4.1
0x3c6e3  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool value)
0x3c6e8  ldarg.0
0x3c6e9  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x3c6ee  ldnull
0x3c6ef  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object value)
0x3c6f4  ldarg.0
0x3c6f5  ldfld    class Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x3c6fa  ldstr    aPropertytypefu// "PropertyTypeFullName"
  ... truncated ...
```
