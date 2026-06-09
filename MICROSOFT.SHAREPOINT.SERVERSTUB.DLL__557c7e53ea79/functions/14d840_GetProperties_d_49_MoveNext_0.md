# <GetProperties>d__49::MoveNext_0

- ea: `0x14d840`
- end: `0x14e6fe`
- name: `<GetProperties>d__49::MoveNext_0`
- size: `3774`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x6ebd0`
- `0x14d840`
- `0x14e720`
- `0x14e780`

## string_xrefs

- `0x14d934`: `AnonymousEditLink`
- `0x14d9a1`: `AnonymousEditLink`
- `0x14da0d`: `AnonymousViewLink`
- `0x14da7a`: `AnonymousViewLink`
- `0x14dd80`: `HasPendingAccessRequests`
- `0x14ddf2`: `HasPendingAccessRequests`
- `0x14e2b9`: `IsSharedWithSecurityGroup`
- `0x14e32b`: `IsSharedWithSecurityGroup`
- `0x14e398`: `PendingAccessRequestsLink`
- `0x14e405`: `PendingAccessRequestsLink`
- `0x14e54c`: `SharingLinks`
- `0x14e5b9`: `SharingLinks`

## pseudocode

```c

```

## disassembly

```asm
0x14d840  ldarg.0
0x14d841  ldfld    int32 <GetProperties>d__49::<>1__state
0x14d846  stloc.1
0x14d847  ldloc.1
0x14d848  switch   loc_14D89E, loc_14E6F1, loc_14D908, loc_14D9F4, loc_14DACD, loc_14DBAB, loc_14DC89, loc_14DD67, loc_14DE45, loc_14DF24, loc_14E003, loc_14E0E2, loc_14E1C1, loc_14E2A0, loc_14E37F, loc_14E459, loc_14E533, loc_14E60D, loc_14E6EA
0x14d899  br       loc_14E6F1
0x14d89e  ldarg.0
0x14d89f  ldc.i4.m1
0x14d8a0  stfld    int32 <GetProperties>d__49::<>1__state
0x14d8a5  ldarg.0
0x14d8a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__49::proxyContext
0x14d8ab  brtrue.s loc_14D8B8
0x14d8ad  ldstr    aProxycontext// "proxyContext"
0x14d8b2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x14d8b7  throw
0x14d8b8  ldarg.0
0x14d8b9  ldarg.0
0x14d8ba  ldfld    class Microsoft.SharePoint.ServerStub.SPObjectSharingInformationServerStub <GetProperties>d__49::<>4__this
0x14d8bf  ldarg.0
0x14d8c0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__49::proxyContext
0x14d8c5  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPObjectSharingInformationServerStub::<>n__FabricatedMethod4d(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext name)
0x14d8ca  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x14d8cf  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__49::<>7__wrap4b
0x14d8d4  ldarg.0
0x14d8d5  ldc.i4.1
0x14d8d6  stfld    int32 <GetProperties>d__49::<>1__state
0x14d8db  br.s     loc_14D90F
0x14d8dd  ldarg.0
0x14d8de  ldarg.0
0x14d8df  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__49::<>7__wrap4b
0x14d8e4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x14d8e9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<item>5__4a
0x14d8ee  ldarg.0
0x14d8ef  ldarg.0
0x14d8f0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<item>5__4a
0x14d8f5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>2__current
0x14d8fa  ldarg.0
0x14d8fb  ldc.i4.2
0x14d8fc  stfld    int32 <GetProperties>d__49::<>1__state
0x14d901  ldc.i4.1
0x14d902  stloc.0
0x14d903  leave    loc_14E6FC
0x14d908  ldarg.0
0x14d909  ldc.i4.1
0x14d90a  stfld    int32 <GetProperties>d__49::<>1__state
0x14d90f  ldarg.0
0x14d910  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__49::<>7__wrap4b
0x14d915  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x14d91a  brtrue.s loc_14D8DD
0x14d91c  ldarg.0
0x14d91d  call     instance void <GetProperties>d__49::<>m__Finally4c()
0x14d922  ldarg.0
0x14d923  ldarg.0
0x14d924  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x14d929  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal39
0x14d92e  ldarg.0
0x14d92f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal39
0x14d934  ldstr    aAnonymouseditl// "AnonymousEditLink"
0x14d939  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x14d93e  ldarg.0
0x14d93f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal39
0x14d944  ldc.i4.0
0x14d945  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x14d94a  ldarg.0
0x14d94b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal39
0x14d950  ldc.i4.1
0x14d951  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14d956  ldarg.0
0x14d957  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal39
0x14d95c  ldc.i4.0
0x14d95d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x14d962  ldarg.0
0x14d963  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal39
0x14d968  ldtoken  [mscorlib]System.String
0x14d96d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14d972  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x14d977  ldarg.0
0x14d978  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal39
0x14d97d  ldc.i4.1
0x14d97e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x14d983  ldarg.0
0x14d984  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal39
0x14d989  ldc.i4.1
0x14d98a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x14d98f  ldarg.0
0x14d990  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal39
0x14d995  ldnull
0x14d996  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x14d99b  ldarg.0
0x14d99c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal39
0x14d9a1  ldstr    aAnonymouseditl// "AnonymousEditLink"
0x14d9a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x14d9ab  ldarg.0
0x14d9ac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal39
0x14d9b1  ldnull
0x14d9b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x14d9b7  ldarg.0
0x14d9b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal39
0x14d9bd  ldc.i4.0
0x14d9be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x14d9c3  ldarg.0
0x14d9c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal39
0x14d9c9  ldc.i4.0
0x14d9ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x14d9cf  ldarg.0
0x14d9d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal39
0x14d9d5  ldc.i4.0
0x14d9d6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x14d9db  ldarg.0
0x14d9dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal39
0x14d9e1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>2__current
0x14d9e6  ldarg.0
0x14d9e7  ldc.i4.3
0x14d9e8  stfld    int32 <GetProperties>d__49::<>1__state
0x14d9ed  ldc.i4.1
0x14d9ee  stloc.0
0x14d9ef  leave    loc_14E6FC
0x14d9f4  ldarg.0
0x14d9f5  ldc.i4.m1
0x14d9f6  stfld    int32 <GetProperties>d__49::<>1__state
0x14d9fb  ldarg.0
0x14d9fc  ldarg.0
0x14d9fd  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x14da02  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3a
0x14da07  ldarg.0
0x14da08  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3a
0x14da0d  ldstr    aAnonymousviewl// "AnonymousViewLink"
0x14da12  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x14da17  ldarg.0
0x14da18  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3a
0x14da1d  ldc.i4.0
0x14da1e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x14da23  ldarg.0
0x14da24  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3a
0x14da29  ldc.i4.1
0x14da2a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14da2f  ldarg.0
0x14da30  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3a
0x14da35  ldc.i4.0
0x14da36  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x14da3b  ldarg.0
0x14da3c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3a
0x14da41  ldtoken  [mscorlib]System.String
0x14da46  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14da4b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x14da50  ldarg.0
0x14da51  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3a
0x14da56  ldc.i4.1
0x14da57  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x14da5c  ldarg.0
0x14da5d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3a
0x14da62  ldc.i4.1
0x14da63  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x14da68  ldarg.0
0x14da69  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3a
0x14da6e  ldnull
0x14da6f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x14da74  ldarg.0
0x14da75  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3a
0x14da7a  ldstr    aAnonymousviewl// "AnonymousViewLink"
0x14da7f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x14da84  ldarg.0
0x14da85  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3a
0x14da8a  ldnull
0x14da8b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x14da90  ldarg.0
0x14da91  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3a
0x14da96  ldc.i4.0
0x14da97  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x14da9c  ldarg.0
0x14da9d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3a
0x14daa2  ldc.i4.0
0x14daa3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x14daa8  ldarg.0
0x14daa9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3a
0x14daae  ldc.i4.0
0x14daaf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x14dab4  ldarg.0
0x14dab5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3a
0x14daba  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>2__current
0x14dabf  ldarg.0
0x14dac0  ldc.i4.4
0x14dac1  stfld    int32 <GetProperties>d__49::<>1__state
0x14dac6  ldc.i4.1
0x14dac7  stloc.0
0x14dac8  leave    loc_14E6FC
0x14dacd  ldarg.0
0x14dace  ldc.i4.m1
0x14dacf  stfld    int32 <GetProperties>d__49::<>1__state
0x14dad4  ldarg.0
0x14dad5  ldarg.0
0x14dad6  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x14dadb  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3b
0x14dae0  ldarg.0
0x14dae1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3b
0x14dae6  ldstr    aCanbeshared// "CanBeShared"
0x14daeb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x14daf0  ldarg.0
0x14daf1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3b
0x14daf6  ldc.i4.0
0x14daf7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x14dafc  ldarg.0
0x14dafd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3b
0x14db02  ldc.i4.1
0x14db03  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14db08  ldarg.0
0x14db09  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3b
0x14db0e  ldc.i4.0
0x14db0f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x14db14  ldarg.0
0x14db15  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3b
0x14db1a  ldtoken  [mscorlib]System.Boolean
0x14db1f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14db24  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x14db29  ldarg.0
0x14db2a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3b
0x14db2f  ldc.i4.1
0x14db30  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x14db35  ldarg.0
0x14db36  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3b
0x14db3b  ldc.i4.1
0x14db3c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x14db41  ldarg.0
0x14db42  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3b
0x14db47  ldc.i4.0
0x14db48  box      [mscorlib]System.Boolean
0x14db4d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x14db52  ldarg.0
0x14db53  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3b
0x14db58  ldstr    aCanbeshared// "CanBeShared"
0x14db5d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x14db62  ldarg.0
0x14db63  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3b
0x14db68  ldnull
0x14db69  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x14db6e  ldarg.0
0x14db6f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3b
0x14db74  ldc.i4.0
0x14db75  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x14db7a  ldarg.0
0x14db7b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3b
0x14db80  ldc.i4.0
0x14db81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x14db86  ldarg.0
0x14db87  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3b
0x14db8c  ldc.i4.0
0x14db8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x14db92  ldarg.0
0x14db93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3b
0x14db98  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>2__current
0x14db9d  ldarg.0
0x14db9e  ldc.i4.5
0x14db9f  stfld    int32 <GetProperties>d__49::<>1__state
0x14dba4  ldc.i4.1
0x14dba5  stloc.0
0x14dba6  leave    loc_14E6FC
0x14dbab  ldarg.0
0x14dbac  ldc.i4.m1
0x14dbad  stfld    int32 <GetProperties>d__49::<>1__state
0x14dbb2  ldarg.0
0x14dbb3  ldarg.0
0x14dbb4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x14dbb9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3c
0x14dbbe  ldarg.0
0x14dbbf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3c
0x14dbc4  ldstr    aCanbeunshared// "CanBeUnshared"
0x14dbc9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x14dbce  ldarg.0
0x14dbcf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3c
0x14dbd4  ldc.i4.0
0x14dbd5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x14dbda  ldarg.0
0x14dbdb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3c
0x14dbe0  ldc.i4.1
0x14dbe1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14dbe6  ldarg.0
0x14dbe7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3c
0x14dbec  ldc.i4.0
0x14dbed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x14dbf2  ldarg.0
0x14dbf3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3c
0x14dbf8  ldtoken  [mscorlib]System.Boolean
0x14dbfd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14dc02  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x14dc07  ldarg.0
0x14dc08  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3c
0x14dc0d  ldc.i4.1
0x14dc0e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x14dc13  ldarg.0
0x14dc14  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3c
0x14dc19  ldc.i4.1
0x14dc1a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x14dc1f  ldarg.0
0x14dc20  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3c
0x14dc25  ldc.i4.0
0x14dc26  box      [mscorlib]System.Boolean
0x14dc2b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x14dc30  ldarg.0
0x14dc31  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__49::<>g__initLocal3c
0x14dc36  ldstr    aCanbeunshared// "CanBeUnshared"
  ... truncated ...
```
