# <GetProperties>d__d::MoveNext_0

- ea: `0x22b60`
- end: `0x22ce9`
- name: `<GetProperties>d__d::MoveNext_0`
- size: `393`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xc530`
- `0x22b60`
- `0x22d10`
- `0x22d70`

## pseudocode

```c

```

## disassembly

```asm
0x22b60  ldarg.0
0x22b61  ldfld    int32 <GetProperties>d__d::<>1__state
0x22b66  stloc.1
0x22b67  ldloc.1
0x22b68  switch   loc_22B82, loc_22CDC, loc_22BEC, loc_22CD5
0x22b7d  br       loc_22CDC
0x22b82  ldarg.0
0x22b83  ldc.i4.m1
0x22b84  stfld    int32 <GetProperties>d__d::<>1__state
0x22b89  ldarg.0
0x22b8a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__d::proxyContext
0x22b8f  brtrue.s loc_22B9C
0x22b91  ldstr    aProxycontext// "proxyContext"
0x22b96  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x22b9b  throw
0x22b9c  ldarg.0
0x22b9d  ldarg.0
0x22b9e  ldfld    class Microsoft.SharePoint.Publishing.PublishingWebServerStub <GetProperties>d__d::<>4__this
0x22ba3  ldarg.0
0x22ba4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__d::proxyContext
0x22ba9  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.PublishingWebServerStub::<>n__FabricatedMethod11(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x22bae  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x22bb3  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__d::<>7__wrapf
0x22bb8  ldarg.0
0x22bb9  ldc.i4.1
0x22bba  stfld    int32 <GetProperties>d__d::<>1__state
0x22bbf  br.s     loc_22BF3
0x22bc1  ldarg.0
0x22bc2  ldarg.0
0x22bc3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__d::<>7__wrapf
0x22bc8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x22bcd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<item>5__e
0x22bd2  ldarg.0
0x22bd3  ldarg.0
0x22bd4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<item>5__e
0x22bd9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>2__current
0x22bde  ldarg.0
0x22bdf  ldc.i4.2
0x22be0  stfld    int32 <GetProperties>d__d::<>1__state
0x22be5  ldc.i4.1
0x22be6  stloc.0
0x22be7  leave    loc_22CE7
0x22bec  ldarg.0
0x22bed  ldc.i4.1
0x22bee  stfld    int32 <GetProperties>d__d::<>1__state
0x22bf3  ldarg.0
0x22bf4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__d::<>7__wrapf
0x22bf9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x22bfe  brtrue.s loc_22BC1
0x22c00  ldarg.0
0x22c01  call     instance void <GetProperties>d__d::<>m__Finally10()
0x22c06  ldarg.0
0x22c07  ldarg.0
0x22c08  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x22c0d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x22c12  ldarg.0
0x22c13  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x22c18  ldstr    aWeb_0// "Web"
0x22c1d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x22c22  ldarg.0
0x22c23  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x22c28  ldc.i4.0
0x22c29  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x22c2e  ldarg.0
0x22c2f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x22c34  ldc.i4.4
0x22c35  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x22c3a  ldarg.0
0x22c3b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x22c40  ldc.i4.0
0x22c41  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x22c46  ldarg.0
0x22c47  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x22c4c  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb
0x22c51  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22c56  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x22c5b  ldarg.0
0x22c5c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x22c61  ldc.i4.1
0x22c62  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x22c67  ldarg.0
0x22c68  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x22c6d  ldc.i4.1
0x22c6e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x22c73  ldarg.0
0x22c74  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x22c79  ldnull
0x22c7a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x22c7f  ldarg.0
0x22c80  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x22c85  ldstr    aWeb_0// "Web"
0x22c8a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x22c8f  ldarg.0
0x22c90  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x22c95  ldnull
0x22c96  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x22c9b  ldarg.0
0x22c9c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x22ca1  ldc.i4.0
0x22ca2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x22ca7  ldarg.0
0x22ca8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x22cad  ldc.i4.0
0x22cae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x22cb3  ldarg.0
0x22cb4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x22cb9  ldc.i4.0
0x22cba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x22cbf  ldarg.0
0x22cc0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x22cc5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>2__current
0x22cca  ldarg.0
0x22ccb  ldc.i4.3
0x22ccc  stfld    int32 <GetProperties>d__d::<>1__state
0x22cd1  ldc.i4.1
0x22cd2  stloc.0
0x22cd3  leave.s  loc_22CE7
0x22cd5  ldarg.0
0x22cd6  ldc.i4.m1
0x22cd7  stfld    int32 <GetProperties>d__d::<>1__state
0x22cdc  ldc.i4.0
0x22cdd  stloc.0
0x22cde  leave.s  loc_22CE7
0x22ce0  ldarg.0
0x22ce1  call     instance void <GetProperties>d__d::System.IDisposable.Dispose()
0x22ce6  endfinally
0x22ce7  ldloc.0
0x22ce8  ret
```
