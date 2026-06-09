# <GetProperties>d__d::MoveNext_3

- ea: `0xd2900`
- end: `0xd34ec`
- name: `<GetProperties>d__d::MoveNext_3`
- size: `3052`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x12860`
- `0xd2900`
- `0xd3510`
- `0xd3570`

## string_xrefs

- `0xd2db9`: `Delete`
- `0xd2ce0`: `Create`
- `0xd2b9a`: `comment`
- `0xd2c73`: `create`
- `0xd2d4c`: `delete`
- `0xd318c`: `rename`
- `0xd2c07`: `Comment`
- `0xd31f9`: `Rename`

## pseudocode

```c

```

## disassembly

```asm
0xd2900  ldarg.0
0xd2901  ldfld    int32 <GetProperties>d__d::<>1__state
0xd2906  stloc.1
0xd2907  ldloc.1
0xd2908  switch   loc_D2952, loc_D34DF, loc_D29BC, loc_D2AA8, loc_D2B81, loc_D2C5A, loc_D2D33, loc_D2E0C, loc_D2EE5, loc_D2FBF, loc_D3099, loc_D3173, loc_D324D, loc_D3327, loc_D3401, loc_D34D8
0xd294d  br       loc_D34DF
0xd2952  ldarg.0
0xd2953  ldc.i4.m1
0xd2954  stfld    int32 <GetProperties>d__d::<>1__state
0xd2959  ldarg.0
0xd295a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__d::proxyContext
0xd295f  brtrue.s loc_D296C
0xd2961  ldstr    aProxycontext// "proxyContext"
0xd2966  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd296b  throw
0xd296c  ldarg.0
0xd296d  ldarg.0
0xd296e  ldfld    class Microsoft.SharePoint.Activities.ActionFacetValueTypeConverter <GetProperties>d__d::<>4__this
0xd2973  ldarg.0
0xd2974  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__d::proxyContext
0xd2979  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Activities.ActionFacetValueTypeConverter::<>n__FabricatedMethod11(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0xd297e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0xd2983  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__d::<>7__wrapf
0xd2988  ldarg.0
0xd2989  ldc.i4.1
0xd298a  stfld    int32 <GetProperties>d__d::<>1__state
0xd298f  br.s     loc_D29C3
0xd2991  ldarg.0
0xd2992  ldarg.0
0xd2993  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__d::<>7__wrapf
0xd2998  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0xd299d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<item>5__e
0xd29a2  ldarg.0
0xd29a3  ldarg.0
0xd29a4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<item>5__e
0xd29a9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>2__current
0xd29ae  ldarg.0
0xd29af  ldc.i4.2
0xd29b0  stfld    int32 <GetProperties>d__d::<>1__state
0xd29b5  ldc.i4.1
0xd29b6  stloc.0
0xd29b7  leave    loc_D34EA
0xd29bc  ldarg.0
0xd29bd  ldc.i4.1
0xd29be  stfld    int32 <GetProperties>d__d::<>1__state
0xd29c3  ldarg.0
0xd29c4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__d::<>7__wrapf
0xd29c9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd29ce  brtrue.s loc_D2991
0xd29d0  ldarg.0
0xd29d1  call     instance void <GetProperties>d__d::<>m__Finally10()
0xd29d6  ldarg.0
0xd29d7  ldarg.0
0xd29d8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xd29dd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0xd29e2  ldarg.0
0xd29e3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0xd29e8  ldstr    aCheckin// "checkin"
0xd29ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xd29f2  ldarg.0
0xd29f3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0xd29f8  ldc.i4.0
0xd29f9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xd29fe  ldarg.0
0xd29ff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0xd2a04  ldc.i4.2
0xd2a05  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xd2a0a  ldarg.0
0xd2a0b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0xd2a10  ldc.i4.0
0xd2a11  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xd2a16  ldarg.0
0xd2a17  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0xd2a1c  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Activities.CheckinFacet
0xd2a21  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd2a26  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xd2a2b  ldarg.0
0xd2a2c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0xd2a31  ldc.i4.0
0xd2a32  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xd2a37  ldarg.0
0xd2a38  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0xd2a3d  ldc.i4.1
0xd2a3e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xd2a43  ldarg.0
0xd2a44  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0xd2a49  ldnull
0xd2a4a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xd2a4f  ldarg.0
0xd2a50  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0xd2a55  ldstr    aCheckin_0// "Checkin"
0xd2a5a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xd2a5f  ldarg.0
0xd2a60  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0xd2a65  ldnull
0xd2a66  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xd2a6b  ldarg.0
0xd2a6c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0xd2a71  ldc.i4.0
0xd2a72  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xd2a77  ldarg.0
0xd2a78  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0xd2a7d  ldc.i4.0
0xd2a7e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xd2a83  ldarg.0
0xd2a84  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0xd2a89  ldc.i4.0
0xd2a8a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xd2a8f  ldarg.0
0xd2a90  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0xd2a95  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>2__current
0xd2a9a  ldarg.0
0xd2a9b  ldc.i4.3
0xd2a9c  stfld    int32 <GetProperties>d__d::<>1__state
0xd2aa1  ldc.i4.1
0xd2aa2  stloc.0
0xd2aa3  leave    loc_D34EA
0xd2aa8  ldarg.0
0xd2aa9  ldc.i4.m1
0xd2aaa  stfld    int32 <GetProperties>d__d::<>1__state
0xd2aaf  ldarg.0
0xd2ab0  ldarg.0
0xd2ab1  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xd2ab6  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0xd2abb  ldarg.0
0xd2abc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0xd2ac1  ldstr    aCheckout// "checkout"
0xd2ac6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xd2acb  ldarg.0
0xd2acc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0xd2ad1  ldc.i4.0
0xd2ad2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xd2ad7  ldarg.0
0xd2ad8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0xd2add  ldc.i4.2
0xd2ade  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xd2ae3  ldarg.0
0xd2ae4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0xd2ae9  ldc.i4.0
0xd2aea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xd2aef  ldarg.0
0xd2af0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0xd2af5  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Activities.CheckoutFacet
0xd2afa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd2aff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xd2b04  ldarg.0
0xd2b05  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0xd2b0a  ldc.i4.0
0xd2b0b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xd2b10  ldarg.0
0xd2b11  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0xd2b16  ldc.i4.1
0xd2b17  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xd2b1c  ldarg.0
0xd2b1d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0xd2b22  ldnull
0xd2b23  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xd2b28  ldarg.0
0xd2b29  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0xd2b2e  ldstr    aCheckout_0// "Checkout"
0xd2b33  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xd2b38  ldarg.0
0xd2b39  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0xd2b3e  ldnull
0xd2b3f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xd2b44  ldarg.0
0xd2b45  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0xd2b4a  ldc.i4.0
0xd2b4b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xd2b50  ldarg.0
0xd2b51  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0xd2b56  ldc.i4.0
0xd2b57  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xd2b5c  ldarg.0
0xd2b5d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0xd2b62  ldc.i4.0
0xd2b63  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xd2b68  ldarg.0
0xd2b69  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0xd2b6e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>2__current
0xd2b73  ldarg.0
0xd2b74  ldc.i4.4
0xd2b75  stfld    int32 <GetProperties>d__d::<>1__state
0xd2b7a  ldc.i4.1
0xd2b7b  stloc.0
0xd2b7c  leave    loc_D34EA
0xd2b81  ldarg.0
0xd2b82  ldc.i4.m1
0xd2b83  stfld    int32 <GetProperties>d__d::<>1__state
0xd2b88  ldarg.0
0xd2b89  ldarg.0
0xd2b8a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xd2b8f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0xd2b94  ldarg.0
0xd2b95  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0xd2b9a  ldstr    aComment// "comment"
0xd2b9f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xd2ba4  ldarg.0
0xd2ba5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0xd2baa  ldc.i4.0
0xd2bab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xd2bb0  ldarg.0
0xd2bb1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0xd2bb6  ldc.i4.2
0xd2bb7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xd2bbc  ldarg.0
0xd2bbd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0xd2bc2  ldc.i4.0
0xd2bc3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xd2bc8  ldarg.0
0xd2bc9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0xd2bce  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Activities.GetCommentFacet
0xd2bd3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd2bd8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xd2bdd  ldarg.0
0xd2bde  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0xd2be3  ldc.i4.0
0xd2be4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xd2be9  ldarg.0
0xd2bea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0xd2bef  ldc.i4.1
0xd2bf0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xd2bf5  ldarg.0
0xd2bf6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0xd2bfb  ldnull
0xd2bfc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xd2c01  ldarg.0
0xd2c02  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0xd2c07  ldstr    aComment_0// "Comment"
0xd2c0c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xd2c11  ldarg.0
0xd2c12  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0xd2c17  ldnull
0xd2c18  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xd2c1d  ldarg.0
0xd2c1e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0xd2c23  ldc.i4.0
0xd2c24  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xd2c29  ldarg.0
0xd2c2a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0xd2c2f  ldc.i4.0
0xd2c30  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xd2c35  ldarg.0
0xd2c36  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0xd2c3b  ldc.i4.0
0xd2c3c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xd2c41  ldarg.0
0xd2c42  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0xd2c47  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>2__current
0xd2c4c  ldarg.0
0xd2c4d  ldc.i4.5
0xd2c4e  stfld    int32 <GetProperties>d__d::<>1__state
0xd2c53  ldc.i4.1
0xd2c54  stloc.0
0xd2c55  leave    loc_D34EA
0xd2c5a  ldarg.0
0xd2c5b  ldc.i4.m1
0xd2c5c  stfld    int32 <GetProperties>d__d::<>1__state
0xd2c61  ldarg.0
0xd2c62  ldarg.0
0xd2c63  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xd2c68  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0xd2c6d  ldarg.0
0xd2c6e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0xd2c73  ldstr    aCreate_0// "create"
0xd2c78  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xd2c7d  ldarg.0
0xd2c7e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0xd2c83  ldc.i4.0
0xd2c84  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xd2c89  ldarg.0
0xd2c8a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0xd2c8f  ldc.i4.2
0xd2c90  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xd2c95  ldarg.0
0xd2c96  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0xd2c9b  ldc.i4.0
0xd2c9c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xd2ca1  ldarg.0
0xd2ca2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0xd2ca7  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Activities.CreateFacet
0xd2cac  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd2cb1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xd2cb6  ldarg.0
0xd2cb7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0xd2cbc  ldc.i4.0
0xd2cbd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xd2cc2  ldarg.0
0xd2cc3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0xd2cc8  ldc.i4.1
0xd2cc9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xd2cce  ldarg.0
0xd2ccf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0xd2cd4  ldnull
0xd2cd5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xd2cda  ldarg.0
0xd2cdb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0xd2ce0  ldstr    aCreate// "Create"
0xd2ce5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xd2cea  ldarg.0
  ... truncated ...
```
