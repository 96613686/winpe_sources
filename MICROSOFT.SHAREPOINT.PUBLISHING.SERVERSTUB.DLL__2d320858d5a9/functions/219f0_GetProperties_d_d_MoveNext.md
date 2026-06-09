# <GetProperties>d__d::MoveNext

- ea: `0x219f0`
- end: `0x21d4d`
- name: `<GetProperties>d__d::MoveNext`
- size: `861`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xbb20`
- `0x219f0`
- `0x21d70`
- `0x21dd0`

## pseudocode

```c

```

## disassembly

```asm
0x219f0  ldarg.0
0x219f1  ldfld    int32 <GetProperties>d__d::<>1__state
0x219f6  stloc.1
0x219f7  ldloc.1
0x219f8  switch   loc_21A1A, loc_21D40, loc_21A84, loc_21B7D, loc_21C56, loc_21D39
0x21a15  br       loc_21D40
0x21a1a  ldarg.0
0x21a1b  ldc.i4.m1
0x21a1c  stfld    int32 <GetProperties>d__d::<>1__state
0x21a21  ldarg.0
0x21a22  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__d::proxyContext
0x21a27  brtrue.s loc_21A34
0x21a29  ldstr    aProxycontext// "proxyContext"
0x21a2e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x21a33  throw
0x21a34  ldarg.0
0x21a35  ldarg.0
0x21a36  ldfld    class Microsoft.SharePoint.Publishing.ScheduledItemServerStub <GetProperties>d__d::<>4__this
0x21a3b  ldarg.0
0x21a3c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__d::proxyContext
0x21a41  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.ScheduledItemServerStub::<>n__FabricatedMethod11(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x21a46  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x21a4b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__d::<>7__wrapf
0x21a50  ldarg.0
0x21a51  ldc.i4.1
0x21a52  stfld    int32 <GetProperties>d__d::<>1__state
0x21a57  br.s     loc_21A8B
0x21a59  ldarg.0
0x21a5a  ldarg.0
0x21a5b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__d::<>7__wrapf
0x21a60  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x21a65  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<item>5__e
0x21a6a  ldarg.0
0x21a6b  ldarg.0
0x21a6c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<item>5__e
0x21a71  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>2__current
0x21a76  ldarg.0
0x21a77  ldc.i4.2
0x21a78  stfld    int32 <GetProperties>d__d::<>1__state
0x21a7d  ldc.i4.1
0x21a7e  stloc.0
0x21a7f  leave    loc_21D4B
0x21a84  ldarg.0
0x21a85  ldc.i4.1
0x21a86  stfld    int32 <GetProperties>d__d::<>1__state
0x21a8b  ldarg.0
0x21a8c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__d::<>7__wrapf
0x21a91  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x21a96  brtrue.s loc_21A59
0x21a98  ldarg.0
0x21a99  call     instance void <GetProperties>d__d::<>m__Finally10()
0x21a9e  ldarg.0
0x21a9f  ldarg.0
0x21aa0  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x21aa5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocala
0x21aaa  ldarg.0
0x21aab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocala
0x21ab0  ldstr    aEnddate// "EndDate"
0x21ab5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x21aba  ldarg.0
0x21abb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocala
0x21ac0  ldc.i4.0
0x21ac1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x21ac6  ldarg.0
0x21ac7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocala
0x21acc  ldc.i4.1
0x21acd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x21ad2  ldarg.0
0x21ad3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocala
0x21ad8  ldc.i4.0
0x21ad9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x21ade  ldarg.0
0x21adf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocala
0x21ae4  ldtoken  [mscorlib]System.DateTime
0x21ae9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21aee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x21af3  ldarg.0
0x21af4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocala
0x21af9  ldc.i4.0
0x21afa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x21aff  ldarg.0
0x21b00  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocala
0x21b05  ldc.i4.1
0x21b06  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x21b0b  ldarg.0
0x21b0c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocala
0x21b11  ldloca.s 2
0x21b13  initobj  [mscorlib]System.DateTime
0x21b19  ldloc.2
0x21b1a  box      [mscorlib]System.DateTime
0x21b1f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x21b24  ldarg.0
0x21b25  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocala
0x21b2a  ldstr    aEnddate// "EndDate"
0x21b2f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x21b34  ldarg.0
0x21b35  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocala
0x21b3a  ldnull
0x21b3b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x21b40  ldarg.0
0x21b41  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocala
0x21b46  ldc.i4.0
0x21b47  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x21b4c  ldarg.0
0x21b4d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocala
0x21b52  ldc.i4.0
0x21b53  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x21b58  ldarg.0
0x21b59  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocala
0x21b5e  ldc.i4.0
0x21b5f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x21b64  ldarg.0
0x21b65  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocala
0x21b6a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>2__current
0x21b6f  ldarg.0
0x21b70  ldc.i4.3
0x21b71  stfld    int32 <GetProperties>d__d::<>1__state
0x21b76  ldc.i4.1
0x21b77  stloc.0
0x21b78  leave    loc_21D4B
0x21b7d  ldarg.0
0x21b7e  ldc.i4.m1
0x21b7f  stfld    int32 <GetProperties>d__d::<>1__state
0x21b84  ldarg.0
0x21b85  ldarg.0
0x21b86  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x21b8b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalb
0x21b90  ldarg.0
0x21b91  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalb
0x21b96  ldstr    aListitem// "ListItem"
0x21b9b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x21ba0  ldarg.0
0x21ba1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalb
0x21ba6  ldc.i4.0
0x21ba7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x21bac  ldarg.0
0x21bad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalb
0x21bb2  ldc.i4.4
0x21bb3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x21bb8  ldarg.0
0x21bb9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalb
0x21bbe  ldc.i4.0
0x21bbf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x21bc4  ldarg.0
0x21bc5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalb
0x21bca  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem
0x21bcf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21bd4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x21bd9  ldarg.0
0x21bda  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalb
0x21bdf  ldc.i4.1
0x21be0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x21be5  ldarg.0
0x21be6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalb
0x21beb  ldc.i4.1
0x21bec  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x21bf1  ldarg.0
0x21bf2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalb
0x21bf7  ldnull
0x21bf8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x21bfd  ldarg.0
0x21bfe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalb
0x21c03  ldstr    aListitem// "ListItem"
0x21c08  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x21c0d  ldarg.0
0x21c0e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalb
0x21c13  ldnull
0x21c14  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x21c19  ldarg.0
0x21c1a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalb
0x21c1f  ldc.i4.0
0x21c20  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x21c25  ldarg.0
0x21c26  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalb
0x21c2b  ldc.i4.0
0x21c2c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x21c31  ldarg.0
0x21c32  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalb
0x21c37  ldc.i4.0
0x21c38  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x21c3d  ldarg.0
0x21c3e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalb
0x21c43  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>2__current
0x21c48  ldarg.0
0x21c49  ldc.i4.4
0x21c4a  stfld    int32 <GetProperties>d__d::<>1__state
0x21c4f  ldc.i4.1
0x21c50  stloc.0
0x21c51  leave    loc_21D4B
0x21c56  ldarg.0
0x21c57  ldc.i4.m1
0x21c58  stfld    int32 <GetProperties>d__d::<>1__state
0x21c5d  ldarg.0
0x21c5e  ldarg.0
0x21c5f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x21c64  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x21c69  ldarg.0
0x21c6a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x21c6f  ldstr    aStartdate// "StartDate"
0x21c74  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x21c79  ldarg.0
0x21c7a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x21c7f  ldc.i4.0
0x21c80  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x21c85  ldarg.0
0x21c86  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x21c8b  ldc.i4.1
0x21c8c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x21c91  ldarg.0
0x21c92  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x21c97  ldc.i4.0
0x21c98  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x21c9d  ldarg.0
0x21c9e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x21ca3  ldtoken  [mscorlib]System.DateTime
0x21ca8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21cad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x21cb2  ldarg.0
0x21cb3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x21cb8  ldc.i4.0
0x21cb9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x21cbe  ldarg.0
0x21cbf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x21cc4  ldc.i4.1
0x21cc5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x21cca  ldarg.0
0x21ccb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x21cd0  ldloca.s 3
0x21cd2  initobj  [mscorlib]System.DateTime
0x21cd8  ldloc.3
0x21cd9  box      [mscorlib]System.DateTime
0x21cde  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x21ce3  ldarg.0
0x21ce4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x21ce9  ldstr    aStartdate// "StartDate"
0x21cee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x21cf3  ldarg.0
0x21cf4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x21cf9  ldnull
0x21cfa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x21cff  ldarg.0
0x21d00  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x21d05  ldc.i4.0
0x21d06  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x21d0b  ldarg.0
0x21d0c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x21d11  ldc.i4.0
0x21d12  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x21d17  ldarg.0
0x21d18  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x21d1d  ldc.i4.0
0x21d1e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x21d23  ldarg.0
0x21d24  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocalc
0x21d29  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>2__current
0x21d2e  ldarg.0
0x21d2f  ldc.i4.5
0x21d30  stfld    int32 <GetProperties>d__d::<>1__state
0x21d35  ldc.i4.1
0x21d36  stloc.0
0x21d37  leave.s  loc_21D4B
0x21d39  ldarg.0
0x21d3a  ldc.i4.m1
0x21d3b  stfld    int32 <GetProperties>d__d::<>1__state
0x21d40  ldc.i4.0
0x21d41  stloc.0
0x21d42  leave.s  loc_21D4B
0x21d44  ldarg.0
0x21d45  call     instance void <GetProperties>d__d::System.IDisposable.Dispose()
0x21d4a  endfinally
0x21d4b  ldloc.0
0x21d4c  ret
```
