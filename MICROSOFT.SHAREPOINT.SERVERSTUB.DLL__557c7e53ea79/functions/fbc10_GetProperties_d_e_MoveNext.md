# <GetProperties>d__e::MoveNext

- ea: `0xfbc10`
- end: `0xfc92b`
- name: `<GetProperties>d__e::MoveNext`
- size: `3355`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x306a0`
- `0xfbc10`
- `0xfc950`
- `0xfc9b0`

## string_xrefs

- `0xfbf91`: `IsFormsLink`
- `0xfc003`: `IsFormsLink`
- `0xfc14d`: `IsReviewLink`
- `0xfc1bf`: `IsReviewLink`
- `0xfc22b`: `IsSharingLink`
- `0xfc29d`: `IsSharingLink`
- `0xfc3e9`: `LinkKind`
- `0xfc45b`: `LinkKind`

## pseudocode

```c

```

## disassembly

```asm
0xfbc10  ldarg.0
0xfbc11  ldfld    int32 <GetProperties>d__e::<>1__state
0xfbc16  stloc.1
0xfbc17  ldloc.1
0xfbc18  switch   loc_FBC66, loc_FC91E, loc_FBCD0, loc_FBDBC, loc_FBE9A, loc_FBF78, loc_FC056, loc_FC134, loc_FC212, loc_FC2F1, loc_FC3D0, loc_FC4AF, loc_FC58E, loc_FC675, loc_FC754, loc_FC833, loc_FC917
0xfbc61  br       loc_FC91E
0xfbc66  ldarg.0
0xfbc67  ldc.i4.m1
0xfbc68  stfld    int32 <GetProperties>d__e::<>1__state
0xfbc6d  ldarg.0
0xfbc6e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__e::proxyContext
0xfbc73  brtrue.s loc_FBC80
0xfbc75  ldstr    aProxycontext// "proxyContext"
0xfbc7a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfbc7f  throw
0xfbc80  ldarg.0
0xfbc81  ldarg.0
0xfbc82  ldfld    class Microsoft.SharePoint.ServerStub.SharingLinkDataValueTypeConverter <GetProperties>d__e::<>4__this
0xfbc87  ldarg.0
0xfbc88  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__e::proxyContext
0xfbc8d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SharingLinkDataValueTypeConverter::<>n__FabricatedMethod12(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0xfbc92  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0xfbc97  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__e::<>7__wrap10
0xfbc9c  ldarg.0
0xfbc9d  ldc.i4.1
0xfbc9e  stfld    int32 <GetProperties>d__e::<>1__state
0xfbca3  br.s     loc_FBCD7
0xfbca5  ldarg.0
0xfbca6  ldarg.0
0xfbca7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__e::<>7__wrap10
0xfbcac  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0xfbcb1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<item>5__f
0xfbcb6  ldarg.0
0xfbcb7  ldarg.0
0xfbcb8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<item>5__f
0xfbcbd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>2__current
0xfbcc2  ldarg.0
0xfbcc3  ldc.i4.2
0xfbcc4  stfld    int32 <GetProperties>d__e::<>1__state
0xfbcc9  ldc.i4.1
0xfbcca  stloc.0
0xfbccb  leave    loc_FC929
0xfbcd0  ldarg.0
0xfbcd1  ldc.i4.1
0xfbcd2  stfld    int32 <GetProperties>d__e::<>1__state
0xfbcd7  ldarg.0
0xfbcd8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__e::<>7__wrap10
0xfbcdd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xfbce2  brtrue.s loc_FBCA5
0xfbce4  ldarg.0
0xfbce5  call     instance void <GetProperties>d__e::<>m__Finally11()
0xfbcea  ldarg.0
0xfbceb  ldarg.0
0xfbcec  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xfbcf1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal0
0xfbcf6  ldarg.0
0xfbcf7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal0
0xfbcfc  ldstr    aExpiration// "Expiration"
0xfbd01  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xfbd06  ldarg.0
0xfbd07  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal0
0xfbd0c  ldc.i4.0
0xfbd0d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xfbd12  ldarg.0
0xfbd13  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal0
0xfbd18  ldc.i4.1
0xfbd19  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xfbd1e  ldarg.0
0xfbd1f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal0
0xfbd24  ldc.i4.0
0xfbd25  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xfbd2a  ldarg.0
0xfbd2b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal0
0xfbd30  ldtoken  [mscorlib]System.String
0xfbd35  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfbd3a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xfbd3f  ldarg.0
0xfbd40  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal0
0xfbd45  ldc.i4.0
0xfbd46  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xfbd4b  ldarg.0
0xfbd4c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal0
0xfbd51  ldc.i4.1
0xfbd52  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xfbd57  ldarg.0
0xfbd58  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal0
0xfbd5d  ldnull
0xfbd5e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xfbd63  ldarg.0
0xfbd64  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal0
0xfbd69  ldstr    aExpiration// "Expiration"
0xfbd6e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xfbd73  ldarg.0
0xfbd74  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal0
0xfbd79  ldnull
0xfbd7a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xfbd7f  ldarg.0
0xfbd80  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal0
0xfbd85  ldc.i4.0
0xfbd86  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xfbd8b  ldarg.0
0xfbd8c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal0
0xfbd91  ldc.i4.0
0xfbd92  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xfbd97  ldarg.0
0xfbd98  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal0
0xfbd9d  ldc.i4.0
0xfbd9e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xfbda3  ldarg.0
0xfbda4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal0
0xfbda9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>2__current
0xfbdae  ldarg.0
0xfbdaf  ldc.i4.3
0xfbdb0  stfld    int32 <GetProperties>d__e::<>1__state
0xfbdb5  ldc.i4.1
0xfbdb6  stloc.0
0xfbdb7  leave    loc_FC929
0xfbdbc  ldarg.0
0xfbdbd  ldc.i4.m1
0xfbdbe  stfld    int32 <GetProperties>d__e::<>1__state
0xfbdc3  ldarg.0
0xfbdc4  ldarg.0
0xfbdc5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xfbdca  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal1
0xfbdcf  ldarg.0
0xfbdd0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal1
0xfbdd5  ldstr    aHasexternalgue// "HasExternalGuestInvitees"
0xfbdda  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xfbddf  ldarg.0
0xfbde0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal1
0xfbde5  ldc.i4.0
0xfbde6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xfbdeb  ldarg.0
0xfbdec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal1
0xfbdf1  ldc.i4.1
0xfbdf2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xfbdf7  ldarg.0
0xfbdf8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal1
0xfbdfd  ldc.i4.0
0xfbdfe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xfbe03  ldarg.0
0xfbe04  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal1
0xfbe09  ldtoken  [mscorlib]System.Boolean
0xfbe0e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfbe13  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xfbe18  ldarg.0
0xfbe19  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal1
0xfbe1e  ldc.i4.0
0xfbe1f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xfbe24  ldarg.0
0xfbe25  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal1
0xfbe2a  ldc.i4.1
0xfbe2b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xfbe30  ldarg.0
0xfbe31  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal1
0xfbe36  ldc.i4.0
0xfbe37  box      [mscorlib]System.Boolean
0xfbe3c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xfbe41  ldarg.0
0xfbe42  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal1
0xfbe47  ldstr    aHasexternalgue// "HasExternalGuestInvitees"
0xfbe4c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xfbe51  ldarg.0
0xfbe52  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal1
0xfbe57  ldnull
0xfbe58  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xfbe5d  ldarg.0
0xfbe5e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal1
0xfbe63  ldc.i4.0
0xfbe64  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xfbe69  ldarg.0
0xfbe6a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal1
0xfbe6f  ldc.i4.1
0xfbe70  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xfbe75  ldarg.0
0xfbe76  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal1
0xfbe7b  ldc.i4.0
0xfbe7c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xfbe81  ldarg.0
0xfbe82  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal1
0xfbe87  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>2__current
0xfbe8c  ldarg.0
0xfbe8d  ldc.i4.4
0xfbe8e  stfld    int32 <GetProperties>d__e::<>1__state
0xfbe93  ldc.i4.1
0xfbe94  stloc.0
0xfbe95  leave    loc_FC929
0xfbe9a  ldarg.0
0xfbe9b  ldc.i4.m1
0xfbe9c  stfld    int32 <GetProperties>d__e::<>1__state
0xfbea1  ldarg.0
0xfbea2  ldarg.0
0xfbea3  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xfbea8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal2
0xfbead  ldarg.0
0xfbeae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal2
0xfbeb3  ldstr    aIsanonymous// "IsAnonymous"
0xfbeb8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xfbebd  ldarg.0
0xfbebe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal2
0xfbec3  ldc.i4.0
0xfbec4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xfbec9  ldarg.0
0xfbeca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal2
0xfbecf  ldc.i4.1
0xfbed0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xfbed5  ldarg.0
0xfbed6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal2
0xfbedb  ldc.i4.0
0xfbedc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xfbee1  ldarg.0
0xfbee2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal2
0xfbee7  ldtoken  [mscorlib]System.Boolean
0xfbeec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfbef1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xfbef6  ldarg.0
0xfbef7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal2
0xfbefc  ldc.i4.0
0xfbefd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xfbf02  ldarg.0
0xfbf03  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal2
0xfbf08  ldc.i4.1
0xfbf09  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xfbf0e  ldarg.0
0xfbf0f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal2
0xfbf14  ldc.i4.0
0xfbf15  box      [mscorlib]System.Boolean
0xfbf1a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xfbf1f  ldarg.0
0xfbf20  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal2
0xfbf25  ldstr    aIsanonymous// "IsAnonymous"
0xfbf2a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xfbf2f  ldarg.0
0xfbf30  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal2
0xfbf35  ldnull
0xfbf36  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xfbf3b  ldarg.0
0xfbf3c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal2
0xfbf41  ldc.i4.0
0xfbf42  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xfbf47  ldarg.0
0xfbf48  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal2
0xfbf4d  ldc.i4.0
0xfbf4e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xfbf53  ldarg.0
0xfbf54  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal2
0xfbf59  ldc.i4.0
0xfbf5a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xfbf5f  ldarg.0
0xfbf60  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal2
0xfbf65  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>2__current
0xfbf6a  ldarg.0
0xfbf6b  ldc.i4.5
0xfbf6c  stfld    int32 <GetProperties>d__e::<>1__state
0xfbf71  ldc.i4.1
0xfbf72  stloc.0
0xfbf73  leave    loc_FC929
0xfbf78  ldarg.0
0xfbf79  ldc.i4.m1
0xfbf7a  stfld    int32 <GetProperties>d__e::<>1__state
0xfbf7f  ldarg.0
0xfbf80  ldarg.0
0xfbf81  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xfbf86  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal3
0xfbf8b  ldarg.0
0xfbf8c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal3
0xfbf91  ldstr    aIsformslink// "IsFormsLink"
0xfbf96  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xfbf9b  ldarg.0
0xfbf9c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal3
0xfbfa1  ldc.i4.0
0xfbfa2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xfbfa7  ldarg.0
0xfbfa8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal3
0xfbfad  ldc.i4.1
0xfbfae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xfbfb3  ldarg.0
0xfbfb4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal3
0xfbfb9  ldc.i4.0
0xfbfba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xfbfbf  ldarg.0
0xfbfc0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal3
0xfbfc5  ldtoken  [mscorlib]System.Boolean
0xfbfca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfbfcf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xfbfd4  ldarg.0
0xfbfd5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal3
0xfbfda  ldc.i4.0
0xfbfdb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xfbfe0  ldarg.0
0xfbfe1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal3
0xfbfe6  ldc.i4.1
0xfbfe7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xfbfec  ldarg.0
0xfbfed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal3
0xfbff2  ldc.i4.0
0xfbff3  box      [mscorlib]System.Boolean
0xfbff8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xfbffd  ldarg.0
0xfbffe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__e::<>g__initLocal3
  ... truncated ...
```
