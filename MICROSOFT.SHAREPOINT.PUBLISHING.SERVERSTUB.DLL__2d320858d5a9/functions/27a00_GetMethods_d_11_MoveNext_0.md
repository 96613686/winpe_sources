# <GetMethods>d__11::MoveNext_0

- ea: `0x27a00`
- end: `0x287d5`
- name: `<GetMethods>d__11::MoveNext_0`
- size: `3541`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callees

- `0x10c00`
- `0x27a00`
- `0x28800`
- `0x28860`

## string_xrefs

- `0x27d73`: `Delete`
- `0x27da8`: `Delete`
- `0x28703`: `Update`
- `0x28737`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0x27a00  ldarg.0
0x27a01  ldfld    int32 <GetMethods>d__11::<>1__state
0x27a06  stloc.1
0x27a07  ldloc.1
0x27a08  switch   loc_27A52, loc_287C8, loc_27ABC, loc_27BA8, loc_27C81, loc_27D5A, loc_27E34, loc_27F0D, loc_27FE6, loc_280C0, loc_2819A, loc_282EE, loc_28442, loc_28596, loc_286EA, loc_287C1
0x27a4d  br       loc_287C8
0x27a52  ldarg.0
0x27a53  ldc.i4.m1
0x27a54  stfld    int32 <GetMethods>d__11::<>1__state
0x27a59  ldarg.0
0x27a5a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__11::proxyContext
0x27a5f  brtrue.s loc_27A6C
0x27a61  ldstr    aProxycontext// "proxyContext"
0x27a66  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x27a6b  throw
0x27a6c  ldarg.0
0x27a6d  ldarg.0
0x27a6e  ldfld    class Microsoft.SharePoint.Publishing.SitePageServerStub <GetMethods>d__11::<>4__this
0x27a73  ldarg.0
0x27a74  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__11::proxyContext
0x27a79  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Publishing.SitePageServerStub::<>n__FabricatedMethod16(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x27a7e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x27a83  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__11::<>7__wrap14
0x27a88  ldarg.0
0x27a89  ldc.i4.1
0x27a8a  stfld    int32 <GetMethods>d__11::<>1__state
0x27a8f  br.s     loc_27AC3
0x27a91  ldarg.0
0x27a92  ldarg.0
0x27a93  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__11::<>7__wrap14
0x27a98  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x27a9d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<itemBase>5__12
0x27aa2  ldarg.0
0x27aa3  ldarg.0
0x27aa4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<itemBase>5__12
0x27aa9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>2__current
0x27aae  ldarg.0
0x27aaf  ldc.i4.2
0x27ab0  stfld    int32 <GetMethods>d__11::<>1__state
0x27ab5  ldc.i4.1
0x27ab6  stloc.0
0x27ab7  leave    loc_287D3
0x27abc  ldarg.0
0x27abd  ldc.i4.1
0x27abe  stfld    int32 <GetMethods>d__11::<>1__state
0x27ac3  ldarg.0
0x27ac4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__11::<>7__wrap14
0x27ac9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x27ace  brtrue.s loc_27A91
0x27ad0  ldarg.0
0x27ad1  call     instance void <GetMethods>d__11::<>m__Finally15()
0x27ad6  ldarg.0
0x27ad7  ldarg.0
0x27ad8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x27add  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0x27ae2  ldarg.0
0x27ae3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0x27ae8  ldstr    aCheckout// "CheckOut"
0x27aed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x27af2  ldarg.0
0x27af3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0x27af8  ldc.i4.0
0x27af9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x27afe  ldarg.0
0x27aff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0x27b04  ldc.i4.0
0x27b05  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x27b0a  ldarg.0
0x27b0b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0x27b10  ldc.i4.8
0x27b11  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x27b16  ldarg.0
0x27b17  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0x27b1c  ldstr    aCheckout// "CheckOut"
0x27b21  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x27b26  ldarg.0
0x27b27  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0x27b2c  ldc.i4.0
0x27b2d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x27b32  ldarg.0
0x27b33  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0x27b38  ldtoken  [mscorlib]System.Boolean
0x27b3d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27b42  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x27b47  ldarg.0
0x27b48  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0x27b4d  ldc.i4.1
0x27b4e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x27b53  ldarg.0
0x27b54  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0x27b59  ldc.i4.0
0x27b5a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x27b5f  ldarg.0
0x27b60  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0x27b65  ldc.i4.0
0x27b66  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x27b6b  ldarg.0
0x27b6c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0x27b71  ldc.i4.0
0x27b72  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x27b77  ldarg.0
0x27b78  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0x27b7d  ldc.i4.1
0x27b7e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x27b83  ldarg.0
0x27b84  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0x27b89  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<item>5__13
0x27b8e  ldarg.0
0x27b8f  ldarg.0
0x27b90  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<item>5__13
0x27b95  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>2__current
0x27b9a  ldarg.0
0x27b9b  ldc.i4.3
0x27b9c  stfld    int32 <GetMethods>d__11::<>1__state
0x27ba1  ldc.i4.1
0x27ba2  stloc.0
0x27ba3  leave    loc_287D3
0x27ba8  ldarg.0
0x27ba9  ldc.i4.m1
0x27baa  stfld    int32 <GetMethods>d__11::<>1__state
0x27baf  ldarg.0
0x27bb0  ldarg.0
0x27bb1  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x27bb6  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal1
0x27bbb  ldarg.0
0x27bbc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal1
0x27bc1  ldstr    aCheckoutpage// "CheckoutPage"
0x27bc6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x27bcb  ldarg.0
0x27bcc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal1
0x27bd1  ldc.i4.0
0x27bd2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x27bd7  ldarg.0
0x27bd8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal1
0x27bdd  ldc.i4.0
0x27bde  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x27be3  ldarg.0
0x27be4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal1
0x27be9  ldc.i4.8
0x27bea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x27bef  ldarg.0
0x27bf0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal1
0x27bf5  ldstr    aCheckoutpage// "CheckoutPage"
0x27bfa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x27bff  ldarg.0
0x27c00  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal1
0x27c05  ldc.i4.0
0x27c06  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x27c0b  ldarg.0
0x27c0c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal1
0x27c11  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage
0x27c16  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27c1b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x27c20  ldarg.0
0x27c21  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal1
0x27c26  ldc.i4.4
0x27c27  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x27c2c  ldarg.0
0x27c2d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal1
0x27c32  ldc.i4.0
0x27c33  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x27c38  ldarg.0
0x27c39  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal1
0x27c3e  ldc.i4.0
0x27c3f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x27c44  ldarg.0
0x27c45  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal1
0x27c4a  ldc.i4.0
0x27c4b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x27c50  ldarg.0
0x27c51  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal1
0x27c56  ldc.i4.1
0x27c57  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x27c5c  ldarg.0
0x27c5d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal1
0x27c62  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<item>5__13
0x27c67  ldarg.0
0x27c68  ldarg.0
0x27c69  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<item>5__13
0x27c6e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>2__current
0x27c73  ldarg.0
0x27c74  ldc.i4.4
0x27c75  stfld    int32 <GetMethods>d__11::<>1__state
0x27c7a  ldc.i4.1
0x27c7b  stloc.0
0x27c7c  leave    loc_287D3
0x27c81  ldarg.0
0x27c82  ldc.i4.m1
0x27c83  stfld    int32 <GetMethods>d__11::<>1__state
0x27c88  ldarg.0
0x27c89  ldarg.0
0x27c8a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x27c8f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal2
0x27c94  ldarg.0
0x27c95  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal2
0x27c9a  ldstr    aCopy// "Copy"
0x27c9f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x27ca4  ldarg.0
0x27ca5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal2
0x27caa  ldc.i4.0
0x27cab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x27cb0  ldarg.0
0x27cb1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal2
0x27cb6  ldc.i4.0
0x27cb7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x27cbc  ldarg.0
0x27cbd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal2
0x27cc2  ldc.i4.8
0x27cc3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x27cc8  ldarg.0
0x27cc9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal2
0x27cce  ldstr    aCopy// "Copy"
0x27cd3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x27cd8  ldarg.0
0x27cd9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal2
0x27cde  ldc.i4.0
0x27cdf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x27ce4  ldarg.0
0x27ce5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal2
0x27cea  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage
0x27cef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27cf4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x27cf9  ldarg.0
0x27cfa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal2
0x27cff  ldc.i4.4
0x27d00  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x27d05  ldarg.0
0x27d06  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal2
0x27d0b  ldc.i4.0
0x27d0c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x27d11  ldarg.0
0x27d12  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal2
0x27d17  ldc.i4.0
0x27d18  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x27d1d  ldarg.0
0x27d1e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal2
0x27d23  ldc.i4.0
0x27d24  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x27d29  ldarg.0
0x27d2a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal2
0x27d2f  ldc.i4.1
0x27d30  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x27d35  ldarg.0
0x27d36  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal2
0x27d3b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<item>5__13
0x27d40  ldarg.0
0x27d41  ldarg.0
0x27d42  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<item>5__13
0x27d47  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>2__current
0x27d4c  ldarg.0
0x27d4d  ldc.i4.5
0x27d4e  stfld    int32 <GetMethods>d__11::<>1__state
0x27d53  ldc.i4.1
0x27d54  stloc.0
0x27d55  leave    loc_287D3
0x27d5a  ldarg.0
0x27d5b  ldc.i4.m1
0x27d5c  stfld    int32 <GetMethods>d__11::<>1__state
0x27d61  ldarg.0
0x27d62  ldarg.0
0x27d63  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x27d68  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0x27d6d  ldarg.0
0x27d6e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0x27d73  ldstr    aDelete// "Delete"
0x27d78  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x27d7d  ldarg.0
0x27d7e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0x27d83  ldc.i4.0
0x27d84  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x27d89  ldarg.0
0x27d8a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0x27d8f  ldc.i4.0
0x27d90  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x27d95  ldarg.0
0x27d96  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0x27d9b  ldc.i4.s 0x10
0x27d9d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x27da2  ldarg.0
0x27da3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0x27da8  ldstr    aDelete// "Delete"
0x27dad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x27db2  ldarg.0
0x27db3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0x27db8  ldc.i4.0
0x27db9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x27dbe  ldarg.0
0x27dbf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0x27dc4  ldtoken  [mscorlib]System.Void
0x27dc9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27dce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x27dd3  ldarg.0
0x27dd4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0x27dd9  ldc.i4.0
0x27dda  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x27ddf  ldarg.0
0x27de0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0x27de5  ldc.i4.0
0x27de6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x27deb  ldarg.0
  ... truncated ...
```
