# <GetProperties>d__3::MoveNext_0

- ea: `0x1eb70`
- end: `0x1eed2`
- name: `<GetProperties>d__3::MoveNext_0`
- size: `866`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x9910`
- `0x1eb70`
- `0x1ef00`
- `0x1ef60`

## pseudocode

```c

```

## disassembly

```asm
0x1eb70  ldarg.0
0x1eb71  ldfld    int32 <GetProperties>d__3::<>1__state
0x1eb76  stloc.1
0x1eb77  ldloc.1
0x1eb78  switch   loc_1EB9A, loc_1EEC5, loc_1EC04, loc_1ECF5, loc_1EDDB, loc_1EEBE
0x1eb95  br       loc_1EEC5
0x1eb9a  ldarg.0
0x1eb9b  ldc.i4.m1
0x1eb9c  stfld    int32 <GetProperties>d__3::<>1__state
0x1eba1  ldarg.0
0x1eba2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__3::proxyContext
0x1eba7  brtrue.s loc_1EBB4
0x1eba9  ldstr    aProxycontext// "proxyContext"
0x1ebae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1ebb3  throw
0x1ebb4  ldarg.0
0x1ebb5  ldarg.0
0x1ebb6  ldfld    class Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettingsServerStub <GetProperties>d__3::<>4__this
0x1ebbb  ldarg.0
0x1ebbc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__3::proxyContext
0x1ebc1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettingsServerStub::<>n__FabricatedMethod7(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext xmlargs)
0x1ebc6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x1ebcb  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3::<>7__wrap5
0x1ebd0  ldarg.0
0x1ebd1  ldc.i4.1
0x1ebd2  stfld    int32 <GetProperties>d__3::<>1__state
0x1ebd7  br.s     loc_1EC0B
0x1ebd9  ldarg.0
0x1ebda  ldarg.0
0x1ebdb  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3::<>7__wrap5
0x1ebe0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x1ebe5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<item>5__4
0x1ebea  ldarg.0
0x1ebeb  ldarg.0
0x1ebec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<item>5__4
0x1ebf1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x1ebf6  ldarg.0
0x1ebf7  ldc.i4.2
0x1ebf8  stfld    int32 <GetProperties>d__3::<>1__state
0x1ebfd  ldc.i4.1
0x1ebfe  stloc.0
0x1ebff  leave    loc_1EED0
0x1ec04  ldarg.0
0x1ec05  ldc.i4.1
0x1ec06  stfld    int32 <GetProperties>d__3::<>1__state
0x1ec0b  ldarg.0
0x1ec0c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3::<>7__wrap5
0x1ec11  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1ec16  brtrue.s loc_1EBD9
0x1ec18  ldarg.0
0x1ec19  call     instance void <GetProperties>d__3::<>m__Finally6()
0x1ec1e  ldarg.0
0x1ec1f  ldarg.0
0x1ec20  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1ec25  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1ec2a  ldarg.0
0x1ec2b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1ec30  ldstr    aSource// "Source"
0x1ec35  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1ec3a  ldarg.0
0x1ec3b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1ec40  ldc.i4.0
0x1ec41  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1ec46  ldarg.0
0x1ec47  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1ec4c  ldc.i4.1
0x1ec4d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ec52  ldarg.0
0x1ec53  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1ec58  ldc.i4.0
0x1ec59  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1ec5e  ldarg.0
0x1ec5f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1ec64  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSource
0x1ec69  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ec6e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1ec73  ldarg.0
0x1ec74  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1ec79  ldc.i4.0
0x1ec7a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1ec7f  ldarg.0
0x1ec80  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1ec85  ldc.i4.1
0x1ec86  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1ec8b  ldarg.0
0x1ec8c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1ec91  ldc.i4.0
0x1ec92  box      [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSource
0x1ec97  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1ec9c  ldarg.0
0x1ec9d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1eca2  ldstr    aSource// "Source"
0x1eca7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1ecac  ldarg.0
0x1ecad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1ecb2  ldnull
0x1ecb3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1ecb8  ldarg.0
0x1ecb9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1ecbe  ldc.i4.0
0x1ecbf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1ecc4  ldarg.0
0x1ecc5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1ecca  ldc.i4.0
0x1eccb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1ecd0  ldarg.0
0x1ecd1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1ecd6  ldc.i4.0
0x1ecd7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1ecdc  ldarg.0
0x1ecdd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x1ece2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x1ece7  ldarg.0
0x1ece8  ldc.i4.3
0x1ece9  stfld    int32 <GetProperties>d__3::<>1__state
0x1ecee  ldc.i4.1
0x1ecef  stloc.0
0x1ecf0  leave    loc_1EED0
0x1ecf5  ldarg.0
0x1ecf6  ldc.i4.m1
0x1ecf7  stfld    int32 <GetProperties>d__3::<>1__state
0x1ecfc  ldarg.0
0x1ecfd  ldarg.0
0x1ecfe  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1ed03  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x1ed08  ldarg.0
0x1ed09  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x1ed0e  ldstr    aTermsetid// "TermSetId"
0x1ed13  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1ed18  ldarg.0
0x1ed19  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x1ed1e  ldc.i4.0
0x1ed1f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1ed24  ldarg.0
0x1ed25  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x1ed2a  ldc.i4.1
0x1ed2b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ed30  ldarg.0
0x1ed31  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x1ed36  ldc.i4.0
0x1ed37  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1ed3c  ldarg.0
0x1ed3d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x1ed42  ldtoken  [mscorlib]System.Guid
0x1ed47  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ed4c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1ed51  ldarg.0
0x1ed52  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x1ed57  ldc.i4.0
0x1ed58  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1ed5d  ldarg.0
0x1ed5e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x1ed63  ldc.i4.1
0x1ed64  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1ed69  ldarg.0
0x1ed6a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x1ed6f  ldloca.s 2
0x1ed71  initobj  [mscorlib]System.Guid
0x1ed77  ldloc.2
0x1ed78  box      [mscorlib]System.Guid
0x1ed7d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1ed82  ldarg.0
0x1ed83  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x1ed88  ldstr    aTermsetid// "TermSetId"
0x1ed8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1ed92  ldarg.0
0x1ed93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x1ed98  ldnull
0x1ed99  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1ed9e  ldarg.0
0x1ed9f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x1eda4  ldc.i4.0
0x1eda5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1edaa  ldarg.0
0x1edab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x1edb0  ldc.i4.0
0x1edb1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1edb6  ldarg.0
0x1edb7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x1edbc  ldc.i4.0
0x1edbd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1edc2  ldarg.0
0x1edc3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x1edc8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x1edcd  ldarg.0
0x1edce  ldc.i4.4
0x1edcf  stfld    int32 <GetProperties>d__3::<>1__state
0x1edd4  ldc.i4.1
0x1edd5  stloc.0
0x1edd6  leave    loc_1EED0
0x1eddb  ldarg.0
0x1eddc  ldc.i4.m1
0x1eddd  stfld    int32 <GetProperties>d__3::<>1__state
0x1ede2  ldarg.0
0x1ede3  ldarg.0
0x1ede4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1ede9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1edee  ldarg.0
0x1edef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1edf4  ldstr    aTermstoreid// "TermStoreId"
0x1edf9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1edfe  ldarg.0
0x1edff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1ee04  ldc.i4.0
0x1ee05  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1ee0a  ldarg.0
0x1ee0b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1ee10  ldc.i4.1
0x1ee11  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ee16  ldarg.0
0x1ee17  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1ee1c  ldc.i4.0
0x1ee1d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1ee22  ldarg.0
0x1ee23  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1ee28  ldtoken  [mscorlib]System.Guid
0x1ee2d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ee32  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1ee37  ldarg.0
0x1ee38  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1ee3d  ldc.i4.0
0x1ee3e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1ee43  ldarg.0
0x1ee44  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1ee49  ldc.i4.1
0x1ee4a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1ee4f  ldarg.0
0x1ee50  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1ee55  ldloca.s 3
0x1ee57  initobj  [mscorlib]System.Guid
0x1ee5d  ldloc.3
0x1ee5e  box      [mscorlib]System.Guid
0x1ee63  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1ee68  ldarg.0
0x1ee69  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1ee6e  ldstr    aTermstoreid// "TermStoreId"
0x1ee73  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1ee78  ldarg.0
0x1ee79  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1ee7e  ldnull
0x1ee7f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1ee84  ldarg.0
0x1ee85  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1ee8a  ldc.i4.0
0x1ee8b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1ee90  ldarg.0
0x1ee91  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1ee96  ldc.i4.0
0x1ee97  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1ee9c  ldarg.0
0x1ee9d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1eea2  ldc.i4.0
0x1eea3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1eea8  ldarg.0
0x1eea9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x1eeae  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x1eeb3  ldarg.0
0x1eeb4  ldc.i4.5
0x1eeb5  stfld    int32 <GetProperties>d__3::<>1__state
0x1eeba  ldc.i4.1
0x1eebb  stloc.0
0x1eebc  leave.s  loc_1EED0
0x1eebe  ldarg.0
0x1eebf  ldc.i4.m1
0x1eec0  stfld    int32 <GetProperties>d__3::<>1__state
0x1eec5  ldc.i4.0
0x1eec6  stloc.0
0x1eec7  leave.s  loc_1EED0
0x1eec9  ldarg.0
0x1eeca  call     instance void <GetProperties>d__3::System.IDisposable.Dispose()
0x1eecf  endfinally
0x1eed0  ldloc.0
0x1eed1  ret
```
