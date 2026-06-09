# <GetProperties>d__1d::MoveNext_0

- ea: `0x288f0`
- end: `0x28d10`
- name: `<GetProperties>d__1d::MoveNext_0`
- size: `1056`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x10c10`
- `0x288f0`
- `0x28d30`
- `0x28d90`

## string_xrefs

- `0x28b66`: `CanvasJson1`
- `0x28bd3`: `CanvasJson1`

## pseudocode

```c

```

## disassembly

```asm
0x288f0  ldarg.0
0x288f1  ldfld    int32 <GetProperties>d__1d::<>1__state
0x288f6  stloc.1
0x288f7  ldloc.1
0x288f8  switch   loc_2891E, loc_28D03, loc_28988, loc_28A74, loc_28B4D, loc_28C26, loc_28CFC
0x28919  br       loc_28D03
0x2891e  ldarg.0
0x2891f  ldc.i4.m1
0x28920  stfld    int32 <GetProperties>d__1d::<>1__state
0x28925  ldarg.0
0x28926  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__1d::proxyContext
0x2892b  brtrue.s loc_28938
0x2892d  ldstr    aProxycontext// "proxyContext"
0x28932  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x28937  throw
0x28938  ldarg.0
0x28939  ldarg.0
0x2893a  ldfld    class Microsoft.SharePoint.Publishing.SitePageServerStub <GetProperties>d__1d::<>4__this
0x2893f  ldarg.0
0x28940  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__1d::proxyContext
0x28945  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.SitePageServerStub::<>n__FabricatedMethod21(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x2894a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x2894f  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1d::<>7__wrap1f
0x28954  ldarg.0
0x28955  ldc.i4.1
0x28956  stfld    int32 <GetProperties>d__1d::<>1__state
0x2895b  br.s     loc_2898F
0x2895d  ldarg.0
0x2895e  ldarg.0
0x2895f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1d::<>7__wrap1f
0x28964  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x28969  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<item>5__1e
0x2896e  ldarg.0
0x2896f  ldarg.0
0x28970  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<item>5__1e
0x28975  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>2__current
0x2897a  ldarg.0
0x2897b  ldc.i4.2
0x2897c  stfld    int32 <GetProperties>d__1d::<>1__state
0x28981  ldc.i4.1
0x28982  stloc.0
0x28983  leave    loc_28D0E
0x28988  ldarg.0
0x28989  ldc.i4.1
0x2898a  stfld    int32 <GetProperties>d__1d::<>1__state
0x2898f  ldarg.0
0x28990  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1d::<>7__wrap1f
0x28995  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2899a  brtrue.s loc_2895D
0x2899c  ldarg.0
0x2899d  call     instance void <GetProperties>d__1d::<>m__Finally20()
0x289a2  ldarg.0
0x289a3  ldarg.0
0x289a4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x289a9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x289ae  ldarg.0
0x289af  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x289b4  ldstr    aAlternativeurl// "AlternativeUrlMap"
0x289b9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x289be  ldarg.0
0x289bf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x289c4  ldc.i4.0
0x289c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x289ca  ldarg.0
0x289cb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x289d0  ldc.i4.1
0x289d1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x289d6  ldarg.0
0x289d7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x289dc  ldc.i4.0
0x289dd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x289e2  ldarg.0
0x289e3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x289e8  ldtoken  [mscorlib]System.String
0x289ed  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x289f2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x289f7  ldarg.0
0x289f8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x289fd  ldc.i4.1
0x289fe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x28a03  ldarg.0
0x28a04  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x28a09  ldc.i4.1
0x28a0a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x28a0f  ldarg.0
0x28a10  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x28a15  ldnull
0x28a16  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x28a1b  ldarg.0
0x28a1c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x28a21  ldstr    aAlternativeurl// "AlternativeUrlMap"
0x28a26  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x28a2b  ldarg.0
0x28a2c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x28a31  ldnull
0x28a32  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x28a37  ldarg.0
0x28a38  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x28a3d  ldc.i4.0
0x28a3e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x28a43  ldarg.0
0x28a44  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x28a49  ldc.i4.1
0x28a4a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x28a4f  ldarg.0
0x28a50  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x28a55  ldc.i4.0
0x28a56  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x28a5b  ldarg.0
0x28a5c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal19
0x28a61  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>2__current
0x28a66  ldarg.0
0x28a67  ldc.i4.3
0x28a68  stfld    int32 <GetProperties>d__1d::<>1__state
0x28a6d  ldc.i4.1
0x28a6e  stloc.0
0x28a6f  leave    loc_28D0E
0x28a74  ldarg.0
0x28a75  ldc.i4.m1
0x28a76  stfld    int32 <GetProperties>d__1d::<>1__state
0x28a7b  ldarg.0
0x28a7c  ldarg.0
0x28a7d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x28a82  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x28a87  ldarg.0
0x28a88  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x28a8d  ldstr    aCanvascontent1// "CanvasContent1"
0x28a92  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x28a97  ldarg.0
0x28a98  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x28a9d  ldc.i4.0
0x28a9e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x28aa3  ldarg.0
0x28aa4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x28aa9  ldc.i4.1
0x28aaa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x28aaf  ldarg.0
0x28ab0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x28ab5  ldc.i4.0
0x28ab6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x28abb  ldarg.0
0x28abc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x28ac1  ldtoken  [mscorlib]System.String
0x28ac6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x28acb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x28ad0  ldarg.0
0x28ad1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x28ad6  ldc.i4.0
0x28ad7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x28adc  ldarg.0
0x28add  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x28ae2  ldc.i4.1
0x28ae3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x28ae8  ldarg.0
0x28ae9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x28aee  ldnull
0x28aef  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x28af4  ldarg.0
0x28af5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x28afa  ldstr    aCanvascontent1// "CanvasContent1"
0x28aff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x28b04  ldarg.0
0x28b05  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x28b0a  ldnull
0x28b0b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x28b10  ldarg.0
0x28b11  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x28b16  ldc.i4.0
0x28b17  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x28b1c  ldarg.0
0x28b1d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x28b22  ldc.i4.1
0x28b23  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x28b28  ldarg.0
0x28b29  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x28b2e  ldc.i4.0
0x28b2f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x28b34  ldarg.0
0x28b35  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1a
0x28b3a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>2__current
0x28b3f  ldarg.0
0x28b40  ldc.i4.4
0x28b41  stfld    int32 <GetProperties>d__1d::<>1__state
0x28b46  ldc.i4.1
0x28b47  stloc.0
0x28b48  leave    loc_28D0E
0x28b4d  ldarg.0
0x28b4e  ldc.i4.m1
0x28b4f  stfld    int32 <GetProperties>d__1d::<>1__state
0x28b54  ldarg.0
0x28b55  ldarg.0
0x28b56  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x28b5b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1b
0x28b60  ldarg.0
0x28b61  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1b
0x28b66  ldstr    aCanvasjson1// "CanvasJson1"
0x28b6b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x28b70  ldarg.0
0x28b71  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1b
0x28b76  ldc.i4.0
0x28b77  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x28b7c  ldarg.0
0x28b7d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1b
0x28b82  ldc.i4.1
0x28b83  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x28b88  ldarg.0
0x28b89  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1b
0x28b8e  ldc.i4.1
0x28b8f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x28b94  ldarg.0
0x28b95  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1b
0x28b9a  ldtoken  [mscorlib]System.String
0x28b9f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x28ba4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x28ba9  ldarg.0
0x28baa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1b
0x28baf  ldc.i4.0
0x28bb0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x28bb5  ldarg.0
0x28bb6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1b
0x28bbb  ldc.i4.1
0x28bbc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x28bc1  ldarg.0
0x28bc2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1b
0x28bc7  ldnull
0x28bc8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x28bcd  ldarg.0
0x28bce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1b
0x28bd3  ldstr    aCanvasjson1// "CanvasJson1"
0x28bd8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x28bdd  ldarg.0
0x28bde  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1b
0x28be3  ldnull
0x28be4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x28be9  ldarg.0
0x28bea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1b
0x28bef  ldc.i4.0
0x28bf0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x28bf5  ldarg.0
0x28bf6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1b
0x28bfb  ldc.i4.1
0x28bfc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x28c01  ldarg.0
0x28c02  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1b
0x28c07  ldc.i4.0
0x28c08  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x28c0d  ldarg.0
0x28c0e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1b
0x28c13  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>2__current
0x28c18  ldarg.0
0x28c19  ldc.i4.5
0x28c1a  stfld    int32 <GetProperties>d__1d::<>1__state
0x28c1f  ldc.i4.1
0x28c20  stloc.0
0x28c21  leave    loc_28D0E
0x28c26  ldarg.0
0x28c27  ldc.i4.m1
0x28c28  stfld    int32 <GetProperties>d__1d::<>1__state
0x28c2d  ldarg.0
0x28c2e  ldarg.0
0x28c2f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x28c34  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1c
0x28c39  ldarg.0
0x28c3a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1c
0x28c3f  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x28c44  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x28c49  ldarg.0
0x28c4a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1c
0x28c4f  ldc.i4.0
0x28c50  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x28c55  ldarg.0
0x28c56  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1c
0x28c5b  ldc.i4.1
0x28c5c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x28c61  ldarg.0
0x28c62  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1c
0x28c67  ldc.i4.0
0x28c68  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x28c6d  ldarg.0
0x28c6e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1c
0x28c73  ldtoken  [mscorlib]System.String
0x28c78  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x28c7d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x28c82  ldarg.0
0x28c83  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1c
0x28c88  ldc.i4.0
0x28c89  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x28c8e  ldarg.0
0x28c8f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1c
0x28c94  ldc.i4.1
0x28c95  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x28c9a  ldarg.0
0x28c9b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1c
0x28ca0  ldnull
0x28ca1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x28ca6  ldarg.0
0x28ca7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1d::<>g__initLocal1c
0x28cac  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x28cb1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x28cb6  ldarg.0
  ... truncated ...
```
