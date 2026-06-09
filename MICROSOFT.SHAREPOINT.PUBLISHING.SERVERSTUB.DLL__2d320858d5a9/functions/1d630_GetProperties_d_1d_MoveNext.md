# <GetProperties>d__1d::MoveNext

- ea: `0x1d630`
- end: `0x1dc38`
- name: `<GetProperties>d__1d::MoveNext`
- size: `1544`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x8600`
- `0x1d630`
- `0x1dc60`
- `0x1dcc0`

## string_xrefs

- `0x1d8b8`: `LinkType`
- `0x1d92a`: `LinkType`

## pseudocode

```c

```

## disassembly

```asm
0x1d630  ldarg.0
0x1d631  ldfld    int32 <GetProperties>d__1d::<>1__state
0x1d636  stloc.1
0x1d637  ldloc.1
0x1d638  switch   loc_1D666, loc_1DC2B, loc_1D6D0, loc_1D7C1, loc_1D89F, loc_1D97D, loc_1DA5B, loc_1DB41, loc_1DC24
0x1d661  br       loc_1DC2B
0x1d666  ldarg.0
0x1d667  ldc.i4.m1
0x1d668  stfld    int32 <GetProperties>d__1d::<>1__state
0x1d66d  ldarg.0
0x1d66e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__1d::proxyContext
0x1d673  brtrue.s loc_1D680
0x1d675  ldstr    aProxycontext// "proxyContext"
0x1d67a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1d67f  throw
0x1d680  ldarg.0
0x1d681  ldarg.0
0x1d682  ldfld    class Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetServerStub <GetProperties>d__1d::<>4__this
0x1d687  ldarg.0
0x1d688  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__1d::proxyContext
0x1d68d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetServerStub::<>n__FabricatedMethod21(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x1d692  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x1d697  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1d::<>7__wrap1f
0x1d69c  ldarg.0
0x1d69d  ldc.i4.1
0x1d69e  stfld    int32 <GetProperties>d__1d::<>1__state
0x1d6a3  br.s     loc_1D6D7
0x1d6a5  ldarg.0
0x1d6a6  ldarg.0
0x1d6a7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1d::<>7__wrap1f
0x1d6ac  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x1d6b1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<item>5__1e
0x1d6b6  ldarg.0
0x1d6b7  ldarg.0
0x1d6b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<item>5__1e
0x1d6bd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>2__current
0x1d6c2  ldarg.0
0x1d6c3  ldc.i4.2
0x1d6c4  stfld    int32 <GetProperties>d__1d::<>1__state
0x1d6c9  ldc.i4.1
0x1d6ca  stloc.0
0x1d6cb  leave    loc_1DC36
0x1d6d0  ldarg.0
0x1d6d1  ldc.i4.1
0x1d6d2  stfld    int32 <GetProperties>d__1d::<>1__state
0x1d6d7  ldarg.0
0x1d6d8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1d::<>7__wrap1f
0x1d6dd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d6e2  brtrue.s loc_1D6A5
0x1d6e4  ldarg.0
0x1d6e5  call     instance void <GetProperties>d__1d::<>m__Finally20()
0x1d6ea  ldarg.0
0x1d6eb  ldarg.0
0x1d6ec  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1d6f1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal17
0x1d6f6  ldarg.0
0x1d6f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal17
0x1d6fc  ldstr    aIsnavigationte// "IsNavigationTermSet"
0x1d701  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1d706  ldarg.0
0x1d707  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal17
0x1d70c  ldc.i4.0
0x1d70d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1d712  ldarg.0
0x1d713  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal17
0x1d718  ldc.i4.1
0x1d719  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1d71e  ldarg.0
0x1d71f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal17
0x1d724  ldc.i4.0
0x1d725  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1d72a  ldarg.0
0x1d72b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal17
0x1d730  ldtoken  [mscorlib]System.Boolean
0x1d735  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d73a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1d73f  ldarg.0
0x1d740  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal17
0x1d745  ldc.i4.0
0x1d746  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1d74b  ldarg.0
0x1d74c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal17
0x1d751  ldc.i4.1
0x1d752  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1d757  ldarg.0
0x1d758  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal17
0x1d75d  ldc.i4.0
0x1d75e  box      [mscorlib]System.Boolean
0x1d763  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1d768  ldarg.0
0x1d769  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal17
0x1d76e  ldstr    aIsnavigationte// "IsNavigationTermSet"
0x1d773  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1d778  ldarg.0
0x1d779  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal17
0x1d77e  ldnull
0x1d77f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1d784  ldarg.0
0x1d785  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal17
0x1d78a  ldc.i4.0
0x1d78b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1d790  ldarg.0
0x1d791  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal17
0x1d796  ldc.i4.0
0x1d797  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1d79c  ldarg.0
0x1d79d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal17
0x1d7a2  ldc.i4.0
0x1d7a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1d7a8  ldarg.0
0x1d7a9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal17
0x1d7ae  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>2__current
0x1d7b3  ldarg.0
0x1d7b4  ldc.i4.3
0x1d7b5  stfld    int32 <GetProperties>d__1d::<>1__state
0x1d7ba  ldc.i4.1
0x1d7bb  stloc.0
0x1d7bc  leave    loc_1DC36
0x1d7c1  ldarg.0
0x1d7c2  ldc.i4.m1
0x1d7c3  stfld    int32 <GetProperties>d__1d::<>1__state
0x1d7c8  ldarg.0
0x1d7c9  ldarg.0
0x1d7ca  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1d7cf  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal18
0x1d7d4  ldarg.0
0x1d7d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal18
0x1d7da  ldstr    aLcid// "Lcid"
0x1d7df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1d7e4  ldarg.0
0x1d7e5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal18
0x1d7ea  ldc.i4.0
0x1d7eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1d7f0  ldarg.0
0x1d7f1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal18
0x1d7f6  ldc.i4.1
0x1d7f7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1d7fc  ldarg.0
0x1d7fd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal18
0x1d802  ldc.i4.0
0x1d803  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1d808  ldarg.0
0x1d809  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal18
0x1d80e  ldtoken  [mscorlib]System.Int32
0x1d813  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d818  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1d81d  ldarg.0
0x1d81e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal18
0x1d823  ldc.i4.1
0x1d824  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1d829  ldarg.0
0x1d82a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal18
0x1d82f  ldc.i4.1
0x1d830  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1d835  ldarg.0
0x1d836  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal18
0x1d83b  ldc.i4.0
0x1d83c  box      [mscorlib]System.Int32
0x1d841  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1d846  ldarg.0
0x1d847  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal18
0x1d84c  ldstr    aLcid// "Lcid"
0x1d851  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1d856  ldarg.0
0x1d857  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal18
0x1d85c  ldnull
0x1d85d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1d862  ldarg.0
0x1d863  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal18
0x1d868  ldc.i4.0
0x1d869  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1d86e  ldarg.0
0x1d86f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal18
0x1d874  ldc.i4.0
0x1d875  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1d87a  ldarg.0
0x1d87b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal18
0x1d880  ldc.i4.0
0x1d881  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1d886  ldarg.0
0x1d887  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal18
0x1d88c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>2__current
0x1d891  ldarg.0
0x1d892  ldc.i4.4
0x1d893  stfld    int32 <GetProperties>d__1d::<>1__state
0x1d898  ldc.i4.1
0x1d899  stloc.0
0x1d89a  leave    loc_1DC36
0x1d89f  ldarg.0
0x1d8a0  ldc.i4.m1
0x1d8a1  stfld    int32 <GetProperties>d__1d::<>1__state
0x1d8a6  ldarg.0
0x1d8a7  ldarg.0
0x1d8a8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1d8ad  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x1d8b2  ldarg.0
0x1d8b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x1d8b8  ldstr    aLinktype// "LinkType"
0x1d8bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1d8c2  ldarg.0
0x1d8c3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x1d8c8  ldc.i4.0
0x1d8c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1d8ce  ldarg.0
0x1d8cf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x1d8d4  ldc.i4.1
0x1d8d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1d8da  ldarg.0
0x1d8db  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x1d8e0  ldc.i4.0
0x1d8e1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1d8e6  ldarg.0
0x1d8e7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x1d8ec  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationLinkType
0x1d8f1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d8f6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1d8fb  ldarg.0
0x1d8fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x1d901  ldc.i4.0
0x1d902  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1d907  ldarg.0
0x1d908  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x1d90d  ldc.i4.1
0x1d90e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1d913  ldarg.0
0x1d914  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x1d919  ldc.i4.0
0x1d91a  box      [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationLinkType
0x1d91f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1d924  ldarg.0
0x1d925  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x1d92a  ldstr    aLinktype// "LinkType"
0x1d92f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1d934  ldarg.0
0x1d935  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x1d93a  ldnull
0x1d93b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1d940  ldarg.0
0x1d941  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x1d946  ldc.i4.0
0x1d947  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1d94c  ldarg.0
0x1d94d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x1d952  ldc.i4.0
0x1d953  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1d958  ldarg.0
0x1d959  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x1d95e  ldc.i4.0
0x1d95f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1d964  ldarg.0
0x1d965  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x1d96a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>2__current
0x1d96f  ldarg.0
0x1d970  ldc.i4.5
0x1d971  stfld    int32 <GetProperties>d__1d::<>1__state
0x1d976  ldc.i4.1
0x1d977  stloc.0
0x1d978  leave    loc_1DC36
0x1d97d  ldarg.0
0x1d97e  ldc.i4.m1
0x1d97f  stfld    int32 <GetProperties>d__1d::<>1__state
0x1d984  ldarg.0
0x1d985  ldarg.0
0x1d986  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1d98b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x1d990  ldarg.0
0x1d991  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x1d996  ldstr    aLoadedfrompers// "LoadedFromPersistedData"
0x1d99b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1d9a0  ldarg.0
0x1d9a1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x1d9a6  ldc.i4.0
0x1d9a7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1d9ac  ldarg.0
0x1d9ad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x1d9b2  ldc.i4.1
0x1d9b3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1d9b8  ldarg.0
0x1d9b9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x1d9be  ldc.i4.0
0x1d9bf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1d9c4  ldarg.0
0x1d9c5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x1d9ca  ldtoken  [mscorlib]System.Boolean
0x1d9cf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d9d4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1d9d9  ldarg.0
0x1d9da  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x1d9df  ldc.i4.1
0x1d9e0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1d9e5  ldarg.0
0x1d9e6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x1d9eb  ldc.i4.1
0x1d9ec  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1d9f1  ldarg.0
0x1d9f2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x1d9f7  ldc.i4.0
0x1d9f8  box      [mscorlib]System.Boolean
0x1d9fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1da02  ldarg.0
  ... truncated ...
```
