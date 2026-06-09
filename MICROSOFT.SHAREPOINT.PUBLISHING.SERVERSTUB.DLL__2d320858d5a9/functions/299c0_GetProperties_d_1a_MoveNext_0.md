# <GetProperties>d__1a::MoveNext_0

- ea: `0x299c0`
- end: `0x29d08`
- name: `<GetProperties>d__1a::MoveNext_0`
- size: `840`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x11640`
- `0x299c0`
- `0x29d30`
- `0x29d90`

## string_xrefs

- `0x29a80`: `CommunicationSite`
- `0x29aed`: `CommunicationSite`

## pseudocode

```c

```

## disassembly

```asm
0x299c0  ldarg.0
0x299c1  ldfld    int32 <GetProperties>d__1a::<>1__state
0x299c6  stloc.1
0x299c7  ldloc.1
0x299c8  switch   loc_299EA, loc_29CFB, loc_29A54, loc_29B40, loc_29C1E, loc_29CF4
0x299e5  br       loc_29CFB
0x299ea  ldarg.0
0x299eb  ldc.i4.m1
0x299ec  stfld    int32 <GetProperties>d__1a::<>1__state
0x299f1  ldarg.0
0x299f2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__1a::proxyContext
0x299f7  brtrue.s loc_29A04
0x299f9  ldstr    aProxycontext// "proxyContext"
0x299fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x29a03  throw
0x29a04  ldarg.0
0x29a05  ldarg.0
0x29a06  ldfld    class Microsoft.SharePoint.Publishing.SitePageServiceServerStub <GetProperties>d__1a::<>4__this
0x29a0b  ldarg.0
0x29a0c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__1a::proxyContext
0x29a11  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.SitePageServiceServerStub::<>n__FabricatedMethod1e(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x29a16  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x29a1b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1a::<>7__wrap1c
0x29a20  ldarg.0
0x29a21  ldc.i4.1
0x29a22  stfld    int32 <GetProperties>d__1a::<>1__state
0x29a27  br.s     loc_29A5B
0x29a29  ldarg.0
0x29a2a  ldarg.0
0x29a2b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1a::<>7__wrap1c
0x29a30  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x29a35  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<item>5__1b
0x29a3a  ldarg.0
0x29a3b  ldarg.0
0x29a3c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<item>5__1b
0x29a41  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>2__current
0x29a46  ldarg.0
0x29a47  ldc.i4.2
0x29a48  stfld    int32 <GetProperties>d__1a::<>1__state
0x29a4d  ldc.i4.1
0x29a4e  stloc.0
0x29a4f  leave    loc_29D06
0x29a54  ldarg.0
0x29a55  ldc.i4.1
0x29a56  stfld    int32 <GetProperties>d__1a::<>1__state
0x29a5b  ldarg.0
0x29a5c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1a::<>7__wrap1c
0x29a61  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x29a66  brtrue.s loc_29A29
0x29a68  ldarg.0
0x29a69  call     instance void <GetProperties>d__1a::<>m__Finally1d()
0x29a6e  ldarg.0
0x29a6f  ldarg.0
0x29a70  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x29a75  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal17
0x29a7a  ldarg.0
0x29a7b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal17
0x29a80  ldstr    aCommunications// "CommunicationSite"
0x29a85  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x29a8a  ldarg.0
0x29a8b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal17
0x29a90  ldc.i4.0
0x29a91  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x29a96  ldarg.0
0x29a97  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal17
0x29a9c  ldc.i4.4
0x29a9d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x29aa2  ldarg.0
0x29aa3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal17
0x29aa8  ldc.i4.0
0x29aa9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x29aae  ldarg.0
0x29aaf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal17
0x29ab4  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSite
0x29ab9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29abe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x29ac3  ldarg.0
0x29ac4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal17
0x29ac9  ldc.i4.1
0x29aca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x29acf  ldarg.0
0x29ad0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal17
0x29ad5  ldc.i4.1
0x29ad6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x29adb  ldarg.0
0x29adc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal17
0x29ae1  ldnull
0x29ae2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x29ae7  ldarg.0
0x29ae8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal17
0x29aed  ldstr    aCommunications// "CommunicationSite"
0x29af2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x29af7  ldarg.0
0x29af8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal17
0x29afd  ldnull
0x29afe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x29b03  ldarg.0
0x29b04  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal17
0x29b09  ldc.i4.0
0x29b0a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x29b0f  ldarg.0
0x29b10  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal17
0x29b15  ldc.i4.1
0x29b16  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x29b1b  ldarg.0
0x29b1c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal17
0x29b21  ldc.i4.0
0x29b22  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x29b27  ldarg.0
0x29b28  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal17
0x29b2d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>2__current
0x29b32  ldarg.0
0x29b33  ldc.i4.3
0x29b34  stfld    int32 <GetProperties>d__1a::<>1__state
0x29b39  ldc.i4.1
0x29b3a  stloc.0
0x29b3b  leave    loc_29D06
0x29b40  ldarg.0
0x29b41  ldc.i4.m1
0x29b42  stfld    int32 <GetProperties>d__1a::<>1__state
0x29b47  ldarg.0
0x29b48  ldarg.0
0x29b49  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x29b4e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal18
0x29b53  ldarg.0
0x29b54  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal18
0x29b59  ldstr    aCustomcontenta// "CustomContentApprovalEnabled"
0x29b5e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x29b63  ldarg.0
0x29b64  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal18
0x29b69  ldc.i4.0
0x29b6a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x29b6f  ldarg.0
0x29b70  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal18
0x29b75  ldc.i4.1
0x29b76  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x29b7b  ldarg.0
0x29b7c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal18
0x29b81  ldc.i4.1
0x29b82  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x29b87  ldarg.0
0x29b88  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal18
0x29b8d  ldtoken  [mscorlib]System.Boolean
0x29b92  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29b97  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x29b9c  ldarg.0
0x29b9d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal18
0x29ba2  ldc.i4.0
0x29ba3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x29ba8  ldarg.0
0x29ba9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal18
0x29bae  ldc.i4.1
0x29baf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x29bb4  ldarg.0
0x29bb5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal18
0x29bba  ldc.i4.0
0x29bbb  box      [mscorlib]System.Boolean
0x29bc0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x29bc5  ldarg.0
0x29bc6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal18
0x29bcb  ldstr    aCustomcontenta// "CustomContentApprovalEnabled"
0x29bd0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x29bd5  ldarg.0
0x29bd6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal18
0x29bdb  ldnull
0x29bdc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x29be1  ldarg.0
0x29be2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal18
0x29be7  ldc.i4.0
0x29be8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x29bed  ldarg.0
0x29bee  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal18
0x29bf3  ldc.i4.1
0x29bf4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x29bf9  ldarg.0
0x29bfa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal18
0x29bff  ldc.i4.0
0x29c00  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x29c05  ldarg.0
0x29c06  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal18
0x29c0b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>2__current
0x29c10  ldarg.0
0x29c11  ldc.i4.4
0x29c12  stfld    int32 <GetProperties>d__1a::<>1__state
0x29c17  ldc.i4.1
0x29c18  stloc.0
0x29c19  leave    loc_29D06
0x29c1e  ldarg.0
0x29c1f  ldc.i4.m1
0x29c20  stfld    int32 <GetProperties>d__1a::<>1__state
0x29c25  ldarg.0
0x29c26  ldarg.0
0x29c27  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x29c2c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal19
0x29c31  ldarg.0
0x29c32  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal19
0x29c37  ldstr    aPages// "Pages"
0x29c3c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x29c41  ldarg.0
0x29c42  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal19
0x29c47  ldc.i4.0
0x29c48  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x29c4d  ldarg.0
0x29c4e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal19
0x29c53  ldc.i4.5
0x29c54  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x29c59  ldarg.0
0x29c5a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal19
0x29c5f  ldc.i4.0
0x29c60  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x29c65  ldarg.0
0x29c66  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal19
0x29c6b  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection
0x29c70  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29c75  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x29c7a  ldarg.0
0x29c7b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal19
0x29c80  ldc.i4.1
0x29c81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x29c86  ldarg.0
0x29c87  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal19
0x29c8c  ldc.i4.1
0x29c8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x29c92  ldarg.0
0x29c93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal19
0x29c98  ldnull
0x29c99  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x29c9e  ldarg.0
0x29c9f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal19
0x29ca4  ldstr    aPages// "Pages"
0x29ca9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x29cae  ldarg.0
0x29caf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal19
0x29cb4  ldnull
0x29cb5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x29cba  ldarg.0
0x29cbb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal19
0x29cc0  ldc.i4.0
0x29cc1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x29cc6  ldarg.0
0x29cc7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal19
0x29ccc  ldc.i4.1
0x29ccd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x29cd2  ldarg.0
0x29cd3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal19
0x29cd8  ldc.i4.0
0x29cd9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x29cde  ldarg.0
0x29cdf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>g__initLocal19
0x29ce4  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1a::<>2__current
0x29ce9  ldarg.0
0x29cea  ldc.i4.5
0x29ceb  stfld    int32 <GetProperties>d__1a::<>1__state
0x29cf0  ldc.i4.1
0x29cf1  stloc.0
0x29cf2  leave.s  loc_29D06
0x29cf4  ldarg.0
0x29cf5  ldc.i4.m1
0x29cf6  stfld    int32 <GetProperties>d__1a::<>1__state
0x29cfb  ldc.i4.0
0x29cfc  stloc.0
0x29cfd  leave.s  loc_29D06
0x29cff  ldarg.0
0x29d00  call     instance void <GetProperties>d__1a::System.IDisposable.Dispose()
0x29d05  endfinally
0x29d06  ldloc.0
0x29d07  ret
```
