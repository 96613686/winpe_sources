# <GetProperties>d__46::MoveNext

- ea: `0xc7a60`
- end: `0xc90cd`
- name: `<GetProperties>d__46::MoveNext`
- size: `5741`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xb750`
- `0xc7a60`
- `0xc90f0`
- `0xc9150`

## string_xrefs

- `0xc7d2a`: `CommentsDisabled`
- `0xc7d9c`: `CommentsDisabled`
- `0xc7e08`: `CommentsDisabledScope`
- `0xc7e7a`: `CommentsDisabledScope`
- `0xc8d6d`: `ServerRedirectedEmbedUri`
- `0xc8dda`: `ServerRedirectedEmbedUri`

## pseudocode

```c

```

## disassembly

```asm
0xc7a60  ldarg.0
0xc7a61  ldfld    int32 <GetProperties>d__46::<>1__state
0xc7a66  stloc.1
0xc7a67  ldloc.1
0xc7a68  switch   loc_C7AE2, loc_C90C0, loc_C7B4C, loc_C7C38, loc_C7D11, loc_C7DEF, loc_C7ECD, loc_C7FA6, loc_C807F, loc_C8159, loc_C8233, loc_C830D, loc_C83E7, loc_C84C1, loc_C859B, loc_C8675, loc_C8754, loc_C882E, loc_C890D, loc_C89E7, loc_C8AC6, loc_C8BA0, loc_C8C7A, loc_C8D54, loc_C8E2E, loc_C8F08, loc_C8FE2, loc_C90B9
0xc7add  br       loc_C90C0
0xc7ae2  ldarg.0
0xc7ae3  ldc.i4.m1
0xc7ae4  stfld    int32 <GetProperties>d__46::<>1__state
0xc7ae9  ldarg.0
0xc7aea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__46::proxyContext
0xc7aef  brtrue.s loc_C7AFC
0xc7af1  ldstr    aProxycontext// "proxyContext"
0xc7af6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xc7afb  throw
0xc7afc  ldarg.0
0xc7afd  ldarg.0
0xc7afe  ldfld    class Microsoft.SharePoint.ServerStub.SPListItemServerStub <GetProperties>d__46::<>4__this
0xc7b03  ldarg.0
0xc7b04  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__46::proxyContext
0xc7b09  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPListItemServerStub::<>n__FabricatedMethod4a(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0xc7b0e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0xc7b13  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__46::<>7__wrap48
0xc7b18  ldarg.0
0xc7b19  ldc.i4.1
0xc7b1a  stfld    int32 <GetProperties>d__46::<>1__state
0xc7b1f  br.s     loc_C7B53
0xc7b21  ldarg.0
0xc7b22  ldarg.0
0xc7b23  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__46::<>7__wrap48
0xc7b28  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0xc7b2d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<item>5__47
0xc7b32  ldarg.0
0xc7b33  ldarg.0
0xc7b34  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<item>5__47
0xc7b39  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>2__current
0xc7b3e  ldarg.0
0xc7b3f  ldc.i4.2
0xc7b40  stfld    int32 <GetProperties>d__46::<>1__state
0xc7b45  ldc.i4.1
0xc7b46  stloc.0
0xc7b47  leave    loc_C90CB
0xc7b4c  ldarg.0
0xc7b4d  ldc.i4.1
0xc7b4e  stfld    int32 <GetProperties>d__46::<>1__state
0xc7b53  ldarg.0
0xc7b54  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__46::<>7__wrap48
0xc7b59  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc7b5e  brtrue.s loc_C7B21
0xc7b60  ldarg.0
0xc7b61  call     instance void <GetProperties>d__46::<>m__Finally49()
0xc7b66  ldarg.0
0xc7b67  ldarg.0
0xc7b68  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xc7b6d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2d
0xc7b72  ldarg.0
0xc7b73  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2d
0xc7b78  ldstr    aActivities// "Activities"
0xc7b7d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xc7b82  ldarg.0
0xc7b83  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2d
0xc7b88  ldc.i4.0
0xc7b89  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xc7b8e  ldarg.0
0xc7b8f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2d
0xc7b94  ldc.i4.5
0xc7b95  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xc7b9a  ldarg.0
0xc7b9b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2d
0xc7ba0  ldc.i4.1
0xc7ba1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xc7ba6  ldarg.0
0xc7ba7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2d
0xc7bac  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityEntitySet
0xc7bb1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc7bb6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xc7bbb  ldarg.0
0xc7bbc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2d
0xc7bc1  ldc.i4.1
0xc7bc2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xc7bc7  ldarg.0
0xc7bc8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2d
0xc7bcd  ldc.i4.1
0xc7bce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xc7bd3  ldarg.0
0xc7bd4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2d
0xc7bd9  ldnull
0xc7bda  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xc7bdf  ldarg.0
0xc7be0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2d
0xc7be5  ldstr    aActivities// "Activities"
0xc7bea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xc7bef  ldarg.0
0xc7bf0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2d
0xc7bf5  ldnull
0xc7bf6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xc7bfb  ldarg.0
0xc7bfc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2d
0xc7c01  ldc.i4.0
0xc7c02  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xc7c07  ldarg.0
0xc7c08  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2d
0xc7c0d  ldc.i4.1
0xc7c0e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xc7c13  ldarg.0
0xc7c14  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2d
0xc7c19  ldc.i4.0
0xc7c1a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xc7c1f  ldarg.0
0xc7c20  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2d
0xc7c25  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>2__current
0xc7c2a  ldarg.0
0xc7c2b  ldc.i4.3
0xc7c2c  stfld    int32 <GetProperties>d__46::<>1__state
0xc7c31  ldc.i4.1
0xc7c32  stloc.0
0xc7c33  leave    loc_C90CB
0xc7c38  ldarg.0
0xc7c39  ldc.i4.m1
0xc7c3a  stfld    int32 <GetProperties>d__46::<>1__state
0xc7c3f  ldarg.0
0xc7c40  ldarg.0
0xc7c41  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xc7c46  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2e
0xc7c4b  ldarg.0
0xc7c4c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2e
0xc7c51  ldstr    aAttachmentfile// "AttachmentFiles"
0xc7c56  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xc7c5b  ldarg.0
0xc7c5c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2e
0xc7c61  ldc.i4.0
0xc7c62  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xc7c67  ldarg.0
0xc7c68  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2e
0xc7c6d  ldc.i4.5
0xc7c6e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xc7c73  ldarg.0
0xc7c74  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2e
0xc7c79  ldc.i4.0
0xc7c7a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xc7c7f  ldarg.0
0xc7c80  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2e
0xc7c85  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPAttachmentCollection_Client
0xc7c8a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc7c8f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xc7c94  ldarg.0
0xc7c95  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2e
0xc7c9a  ldc.i4.1
0xc7c9b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xc7ca0  ldarg.0
0xc7ca1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2e
0xc7ca6  ldc.i4.1
0xc7ca7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xc7cac  ldarg.0
0xc7cad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2e
0xc7cb2  ldnull
0xc7cb3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xc7cb8  ldarg.0
0xc7cb9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2e
0xc7cbe  ldstr    aAttachmentsCli// "Attachments_Client"
0xc7cc3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xc7cc8  ldarg.0
0xc7cc9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2e
0xc7cce  ldnull
0xc7ccf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xc7cd4  ldarg.0
0xc7cd5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2e
0xc7cda  ldc.i4.0
0xc7cdb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xc7ce0  ldarg.0
0xc7ce1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2e
0xc7ce6  ldc.i4.0
0xc7ce7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xc7cec  ldarg.0
0xc7ced  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2e
0xc7cf2  ldc.i4.0
0xc7cf3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xc7cf8  ldarg.0
0xc7cf9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2e
0xc7cfe  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>2__current
0xc7d03  ldarg.0
0xc7d04  ldc.i4.4
0xc7d05  stfld    int32 <GetProperties>d__46::<>1__state
0xc7d0a  ldc.i4.1
0xc7d0b  stloc.0
0xc7d0c  leave    loc_C90CB
0xc7d11  ldarg.0
0xc7d12  ldc.i4.m1
0xc7d13  stfld    int32 <GetProperties>d__46::<>1__state
0xc7d18  ldarg.0
0xc7d19  ldarg.0
0xc7d1a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xc7d1f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2f
0xc7d24  ldarg.0
0xc7d25  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2f
0xc7d2a  ldstr    aCommentsdisabl// "CommentsDisabled"
0xc7d2f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xc7d34  ldarg.0
0xc7d35  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2f
0xc7d3a  ldc.i4.0
0xc7d3b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xc7d40  ldarg.0
0xc7d41  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2f
0xc7d46  ldc.i4.1
0xc7d47  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xc7d4c  ldarg.0
0xc7d4d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2f
0xc7d52  ldc.i4.1
0xc7d53  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xc7d58  ldarg.0
0xc7d59  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2f
0xc7d5e  ldtoken  [mscorlib]System.Boolean
0xc7d63  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc7d68  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xc7d6d  ldarg.0
0xc7d6e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2f
0xc7d73  ldc.i4.1
0xc7d74  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xc7d79  ldarg.0
0xc7d7a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2f
0xc7d7f  ldc.i4.1
0xc7d80  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xc7d85  ldarg.0
0xc7d86  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2f
0xc7d8b  ldc.i4.0
0xc7d8c  box      [mscorlib]System.Boolean
0xc7d91  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xc7d96  ldarg.0
0xc7d97  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2f
0xc7d9c  ldstr    aCommentsdisabl// "CommentsDisabled"
0xc7da1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xc7da6  ldarg.0
0xc7da7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2f
0xc7dac  ldnull
0xc7dad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xc7db2  ldarg.0
0xc7db3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2f
0xc7db8  ldc.i4.0
0xc7db9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xc7dbe  ldarg.0
0xc7dbf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2f
0xc7dc4  ldc.i4.1
0xc7dc5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xc7dca  ldarg.0
0xc7dcb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2f
0xc7dd0  ldc.i4.0
0xc7dd1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xc7dd6  ldarg.0
0xc7dd7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal2f
0xc7ddc  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>2__current
0xc7de1  ldarg.0
0xc7de2  ldc.i4.5
0xc7de3  stfld    int32 <GetProperties>d__46::<>1__state
0xc7de8  ldc.i4.1
0xc7de9  stloc.0
0xc7dea  leave    loc_C90CB
0xc7def  ldarg.0
0xc7df0  ldc.i4.m1
0xc7df1  stfld    int32 <GetProperties>d__46::<>1__state
0xc7df6  ldarg.0
0xc7df7  ldarg.0
0xc7df8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xc7dfd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal30
0xc7e02  ldarg.0
0xc7e03  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal30
0xc7e08  ldstr    aCommentsdisabl_0// "CommentsDisabledScope"
0xc7e0d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xc7e12  ldarg.0
0xc7e13  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal30
0xc7e18  ldc.i4.0
0xc7e19  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xc7e1e  ldarg.0
0xc7e1f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal30
0xc7e24  ldc.i4.1
0xc7e25  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xc7e2a  ldarg.0
0xc7e2b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal30
0xc7e30  ldc.i4.1
0xc7e31  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xc7e36  ldarg.0
0xc7e37  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal30
0xc7e3c  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Comments.SPCommentsDisabledScope
0xc7e41  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc7e46  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xc7e4b  ldarg.0
0xc7e4c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal30
0xc7e51  ldc.i4.1
0xc7e52  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xc7e57  ldarg.0
0xc7e58  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal30
0xc7e5d  ldc.i4.1
0xc7e5e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xc7e63  ldarg.0
0xc7e64  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal30
0xc7e69  ldc.i4.0
0xc7e6a  box      [Microsoft.SharePoint]Microsoft.SharePoint.Comments.SPCommentsDisabledScope
0xc7e6f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xc7e74  ldarg.0
0xc7e75  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__46::<>g__initLocal30
0xc7e7a  ldstr    aCommentsdisabl_0// "CommentsDisabledScope"
  ... truncated ...
```
