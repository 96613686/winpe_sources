# <GetProperties>d__9::MoveNext_6

- ea: `0x1a87f0`
- end: `0x1a908a`
- name: `<GetProperties>d__9::MoveNext_6`
- size: `2202`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0xadc80`
- `0x1a87f0`
- `0x1a90b0`
- `0x1a9110`

## string_xrefs

- `0x1a8bca`: `LinkKind`
- `0x1a8b58`: `linkKind`
- `0x1a88c8`: `allowAnonymousAccess`
- `0x1a8a7f`: `inviteesToRemove`
- `0x1a8fb3`: `updatePassword`
- `0x1a893a`: `AllowAnonymousAccess`
- `0x1a8aec`: `InviteesToRemove`
- `0x1a9025`: `UpdatePassword`

## pseudocode

```c

```

## disassembly

```asm
0x1a87f0  ldarg.0
0x1a87f1  ldfld    int32 <GetProperties>d__9::<>1__state
0x1a87f6  stloc.1
0x1a87f7  ldloc.1
0x1a87f8  switch   loc_1A8832, loc_1A907D, loc_1A889C, loc_1A898D, loc_1A8A66, loc_1A8B3F, loc_1A8C1D, loc_1A8CF6, loc_1A8DD4, loc_1A8EB3, loc_1A8F9A, loc_1A9076
0x1a882d  br       loc_1A907D
0x1a8832  ldarg.0
0x1a8833  ldc.i4.m1
0x1a8834  stfld    int32 <GetProperties>d__9::<>1__state
0x1a8839  ldarg.0
0x1a883a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__9::proxyContext
0x1a883f  brtrue.s loc_1A884C
0x1a8841  ldstr    aProxycontext// "proxyContext"
0x1a8846  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1a884b  throw
0x1a884c  ldarg.0
0x1a884d  ldarg.0
0x1a884e  ldfld    class Microsoft.SharePoint.Sharing.ShareLinkSettingsValueTypeConverter <GetProperties>d__9::<>4__this
0x1a8853  ldarg.0
0x1a8854  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__9::proxyContext
0x1a8859  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Sharing.ShareLinkSettingsValueTypeConverter::<>n__FabricatedMethodd(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x1a885e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x1a8863  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__9::<>7__wrapb
0x1a8868  ldarg.0
0x1a8869  ldc.i4.1
0x1a886a  stfld    int32 <GetProperties>d__9::<>1__state
0x1a886f  br.s     loc_1A88A3
0x1a8871  ldarg.0
0x1a8872  ldarg.0
0x1a8873  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__9::<>7__wrapb
0x1a8878  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x1a887d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<item>5__a
0x1a8882  ldarg.0
0x1a8883  ldarg.0
0x1a8884  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<item>5__a
0x1a8889  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>2__current
0x1a888e  ldarg.0
0x1a888f  ldc.i4.2
0x1a8890  stfld    int32 <GetProperties>d__9::<>1__state
0x1a8895  ldc.i4.1
0x1a8896  stloc.0
0x1a8897  leave    loc_1A9088
0x1a889c  ldarg.0
0x1a889d  ldc.i4.1
0x1a889e  stfld    int32 <GetProperties>d__9::<>1__state
0x1a88a3  ldarg.0
0x1a88a4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__9::<>7__wrapb
0x1a88a9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a88ae  brtrue.s loc_1A8871
0x1a88b0  ldarg.0
0x1a88b1  call     instance void <GetProperties>d__9::<>m__Finallyc()
0x1a88b6  ldarg.0
0x1a88b7  ldarg.0
0x1a88b8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a88bd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x1a88c2  ldarg.0
0x1a88c3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x1a88c8  ldstr    aAllowanonymous// "allowAnonymousAccess"
0x1a88cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a88d2  ldarg.0
0x1a88d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x1a88d8  ldc.i4.0
0x1a88d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a88de  ldarg.0
0x1a88df  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x1a88e4  ldc.i4.1
0x1a88e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a88ea  ldarg.0
0x1a88eb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x1a88f0  ldc.i4.0
0x1a88f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1a88f6  ldarg.0
0x1a88f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x1a88fc  ldtoken  [mscorlib]System.Boolean
0x1a8901  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a8906  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1a890b  ldarg.0
0x1a890c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x1a8911  ldc.i4.0
0x1a8912  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1a8917  ldarg.0
0x1a8918  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x1a891d  ldc.i4.1
0x1a891e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1a8923  ldarg.0
0x1a8924  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x1a8929  ldc.i4.0
0x1a892a  box      [mscorlib]System.Boolean
0x1a892f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1a8934  ldarg.0
0x1a8935  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x1a893a  ldstr    aAllowanonymous_0// "AllowAnonymousAccess"
0x1a893f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1a8944  ldarg.0
0x1a8945  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x1a894a  ldnull
0x1a894b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1a8950  ldarg.0
0x1a8951  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x1a8956  ldc.i4.0
0x1a8957  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1a895c  ldarg.0
0x1a895d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x1a8962  ldc.i4.0
0x1a8963  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1a8968  ldarg.0
0x1a8969  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x1a896e  ldc.i4.0
0x1a896f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1a8974  ldarg.0
0x1a8975  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal0
0x1a897a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>2__current
0x1a897f  ldarg.0
0x1a8980  ldc.i4.3
0x1a8981  stfld    int32 <GetProperties>d__9::<>1__state
0x1a8986  ldc.i4.1
0x1a8987  stloc.0
0x1a8988  leave    loc_1A9088
0x1a898d  ldarg.0
0x1a898e  ldc.i4.m1
0x1a898f  stfld    int32 <GetProperties>d__9::<>1__state
0x1a8994  ldarg.0
0x1a8995  ldarg.0
0x1a8996  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a899b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x1a89a0  ldarg.0
0x1a89a1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x1a89a6  ldstr    aExpiration_0// "expiration"
0x1a89ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a89b0  ldarg.0
0x1a89b1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x1a89b6  ldc.i4.0
0x1a89b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a89bc  ldarg.0
0x1a89bd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x1a89c2  ldc.i4.1
0x1a89c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a89c8  ldarg.0
0x1a89c9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x1a89ce  ldc.i4.0
0x1a89cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1a89d4  ldarg.0
0x1a89d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x1a89da  ldtoken  [mscorlib]System.String
0x1a89df  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a89e4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1a89e9  ldarg.0
0x1a89ea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x1a89ef  ldc.i4.0
0x1a89f0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1a89f5  ldarg.0
0x1a89f6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x1a89fb  ldc.i4.1
0x1a89fc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1a8a01  ldarg.0
0x1a8a02  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x1a8a07  ldnull
0x1a8a08  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1a8a0d  ldarg.0
0x1a8a0e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x1a8a13  ldstr    aExpiration// "Expiration"
0x1a8a18  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1a8a1d  ldarg.0
0x1a8a1e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x1a8a23  ldnull
0x1a8a24  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1a8a29  ldarg.0
0x1a8a2a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x1a8a2f  ldc.i4.0
0x1a8a30  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1a8a35  ldarg.0
0x1a8a36  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x1a8a3b  ldc.i4.0
0x1a8a3c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1a8a41  ldarg.0
0x1a8a42  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x1a8a47  ldc.i4.0
0x1a8a48  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1a8a4d  ldarg.0
0x1a8a4e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal1
0x1a8a53  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>2__current
0x1a8a58  ldarg.0
0x1a8a59  ldc.i4.4
0x1a8a5a  stfld    int32 <GetProperties>d__9::<>1__state
0x1a8a5f  ldc.i4.1
0x1a8a60  stloc.0
0x1a8a61  leave    loc_1A9088
0x1a8a66  ldarg.0
0x1a8a67  ldc.i4.m1
0x1a8a68  stfld    int32 <GetProperties>d__9::<>1__state
0x1a8a6d  ldarg.0
0x1a8a6e  ldarg.0
0x1a8a6f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a8a74  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x1a8a79  ldarg.0
0x1a8a7a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x1a8a7f  ldstr    aInviteestoremo// "inviteesToRemove"
0x1a8a84  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a8a89  ldarg.0
0x1a8a8a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x1a8a8f  ldc.i4.0
0x1a8a90  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a8a95  ldarg.0
0x1a8a96  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x1a8a9b  ldc.i4.3
0x1a8a9c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a8aa1  ldarg.0
0x1a8aa2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x1a8aa7  ldc.i4.0
0x1a8aa8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1a8aad  ldarg.0
0x1a8aae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x1a8ab3  ldtoken  class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal>
0x1a8ab8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a8abd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1a8ac2  ldarg.0
0x1a8ac3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x1a8ac8  ldc.i4.0
0x1a8ac9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1a8ace  ldarg.0
0x1a8acf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x1a8ad4  ldc.i4.1
0x1a8ad5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1a8ada  ldarg.0
0x1a8adb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x1a8ae0  ldnull
0x1a8ae1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1a8ae6  ldarg.0
0x1a8ae7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x1a8aec  ldstr    aInviteestoremo_0// "InviteesToRemove"
0x1a8af1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1a8af6  ldarg.0
0x1a8af7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x1a8afc  ldnull
0x1a8afd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1a8b02  ldarg.0
0x1a8b03  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x1a8b08  ldc.i4.0
0x1a8b09  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1a8b0e  ldarg.0
0x1a8b0f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x1a8b14  ldc.i4.0
0x1a8b15  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1a8b1a  ldarg.0
0x1a8b1b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x1a8b20  ldc.i4.0
0x1a8b21  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1a8b26  ldarg.0
0x1a8b27  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal2
0x1a8b2c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>2__current
0x1a8b31  ldarg.0
0x1a8b32  ldc.i4.5
0x1a8b33  stfld    int32 <GetProperties>d__9::<>1__state
0x1a8b38  ldc.i4.1
0x1a8b39  stloc.0
0x1a8b3a  leave    loc_1A9088
0x1a8b3f  ldarg.0
0x1a8b40  ldc.i4.m1
0x1a8b41  stfld    int32 <GetProperties>d__9::<>1__state
0x1a8b46  ldarg.0
0x1a8b47  ldarg.0
0x1a8b48  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a8b4d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x1a8b52  ldarg.0
0x1a8b53  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x1a8b58  ldstr    aLinkkind_0// "linkKind"
0x1a8b5d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a8b62  ldarg.0
0x1a8b63  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x1a8b68  ldc.i4.0
0x1a8b69  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a8b6e  ldarg.0
0x1a8b6f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x1a8b74  ldc.i4.1
0x1a8b75  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a8b7a  ldarg.0
0x1a8b7b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x1a8b80  ldc.i4.0
0x1a8b81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1a8b86  ldarg.0
0x1a8b87  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x1a8b8c  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkKind
0x1a8b91  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a8b96  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1a8b9b  ldarg.0
0x1a8b9c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x1a8ba1  ldc.i4.0
0x1a8ba2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1a8ba7  ldarg.0
0x1a8ba8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x1a8bad  ldc.i4.1
0x1a8bae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1a8bb3  ldarg.0
0x1a8bb4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x1a8bb9  ldc.i4.0
0x1a8bba  box      [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkKind
0x1a8bbf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1a8bc4  ldarg.0
0x1a8bc5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__9::<>g__initLocal3
0x1a8bca  ldstr    aLinkkind// "LinkKind"
  ... truncated ...
```
