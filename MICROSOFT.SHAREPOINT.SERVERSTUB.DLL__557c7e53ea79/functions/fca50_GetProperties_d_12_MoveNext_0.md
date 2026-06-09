# <GetProperties>d__12::MoveNext_0

- ea: `0xfca50`
- end: `0xfdad1`
- name: `<GetProperties>d__12::MoveNext_0`
- size: `4225`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x30ba0`
- `0xfca50`
- `0xfdb00`
- `0xfdb60`

## string_xrefs

- `0xfcc2a`: `Created`
- `0xfcc97`: `Created`
- `0xfd22a`: `IsFormsLink`
- `0xfd29c`: `IsFormsLink`
- `0xfd309`: `IsReviewLink`
- `0xfd37b`: `IsReviewLink`
- `0xfd67b`: `LinkKind`
- `0xfd6ed`: `LinkKind`
- `0xfcb4c`: `AllowsAnonymousAccess`
- `0xfcbbe`: `AllowsAnonymousAccess`
- `0xfcd03`: `CreatedBy`
- `0xfcd70`: `CreatedBy`
- `0xfd14b`: `IsEditLink`
- `0xfd1bd`: `IsEditLink`

## pseudocode

```c

```

## disassembly

```asm
0xfca50  ldarg.0
0xfca51  ldfld    int32 <GetProperties>d__12::<>1__state
0xfca56  stloc.1
0xfca57  ldloc.1
0xfca58  switch   loc_FCAB6, loc_FDAC4, loc_FCB20, loc_FCC11, loc_FCCEA, loc_FCDC3, loc_FCE9C, loc_FCF7A, loc_FD053, loc_FD132, loc_FD211, loc_FD2F0, loc_FD3CF, loc_FD4AE, loc_FD588, loc_FD662, loc_FD741, loc_FD820, loc_FD8FF, loc_FD9E6, loc_FDABD
0xfcab1  br       loc_FDAC4
0xfcab6  ldarg.0
0xfcab7  ldc.i4.m1
0xfcab8  stfld    int32 <GetProperties>d__12::<>1__state
0xfcabd  ldarg.0
0xfcabe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__12::proxyContext
0xfcac3  brtrue.s loc_FCAD0
0xfcac5  ldstr    aProxycontext// "proxyContext"
0xfcaca  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfcacf  throw
0xfcad0  ldarg.0
0xfcad1  ldarg.0
0xfcad2  ldfld    class Microsoft.SharePoint.ServerStub.SharingLinkInfoValueTypeConverter <GetProperties>d__12::<>4__this
0xfcad7  ldarg.0
0xfcad8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__12::proxyContext
0xfcadd  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SharingLinkInfoValueTypeConverter::<>n__FabricatedMethod16(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0xfcae2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0xfcae7  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__12::<>7__wrap14
0xfcaec  ldarg.0
0xfcaed  ldc.i4.1
0xfcaee  stfld    int32 <GetProperties>d__12::<>1__state
0xfcaf3  br.s     loc_FCB27
0xfcaf5  ldarg.0
0xfcaf6  ldarg.0
0xfcaf7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__12::<>7__wrap14
0xfcafc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0xfcb01  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<item>5__13
0xfcb06  ldarg.0
0xfcb07  ldarg.0
0xfcb08  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<item>5__13
0xfcb0d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>2__current
0xfcb12  ldarg.0
0xfcb13  ldc.i4.2
0xfcb14  stfld    int32 <GetProperties>d__12::<>1__state
0xfcb19  ldc.i4.1
0xfcb1a  stloc.0
0xfcb1b  leave    loc_FDACF
0xfcb20  ldarg.0
0xfcb21  ldc.i4.1
0xfcb22  stfld    int32 <GetProperties>d__12::<>1__state
0xfcb27  ldarg.0
0xfcb28  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__12::<>7__wrap14
0xfcb2d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xfcb32  brtrue.s loc_FCAF5
0xfcb34  ldarg.0
0xfcb35  call     instance void <GetProperties>d__12::<>m__Finally15()
0xfcb3a  ldarg.0
0xfcb3b  ldarg.0
0xfcb3c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xfcb41  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0xfcb46  ldarg.0
0xfcb47  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0xfcb4c  ldstr    aAllowsanonymou// "AllowsAnonymousAccess"
0xfcb51  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xfcb56  ldarg.0
0xfcb57  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0xfcb5c  ldc.i4.0
0xfcb5d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xfcb62  ldarg.0
0xfcb63  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0xfcb68  ldc.i4.1
0xfcb69  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xfcb6e  ldarg.0
0xfcb6f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0xfcb74  ldc.i4.0
0xfcb75  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xfcb7a  ldarg.0
0xfcb7b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0xfcb80  ldtoken  [mscorlib]System.Boolean
0xfcb85  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfcb8a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xfcb8f  ldarg.0
0xfcb90  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0xfcb95  ldc.i4.1
0xfcb96  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xfcb9b  ldarg.0
0xfcb9c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0xfcba1  ldc.i4.1
0xfcba2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xfcba7  ldarg.0
0xfcba8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0xfcbad  ldc.i4.0
0xfcbae  box      [mscorlib]System.Boolean
0xfcbb3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xfcbb8  ldarg.0
0xfcbb9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0xfcbbe  ldstr    aAllowsanonymou// "AllowsAnonymousAccess"
0xfcbc3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xfcbc8  ldarg.0
0xfcbc9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0xfcbce  ldnull
0xfcbcf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xfcbd4  ldarg.0
0xfcbd5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0xfcbda  ldc.i4.0
0xfcbdb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xfcbe0  ldarg.0
0xfcbe1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0xfcbe6  ldc.i4.1
0xfcbe7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xfcbec  ldarg.0
0xfcbed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0xfcbf2  ldc.i4.0
0xfcbf3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xfcbf8  ldarg.0
0xfcbf9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal0
0xfcbfe  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>2__current
0xfcc03  ldarg.0
0xfcc04  ldc.i4.3
0xfcc05  stfld    int32 <GetProperties>d__12::<>1__state
0xfcc0a  ldc.i4.1
0xfcc0b  stloc.0
0xfcc0c  leave    loc_FDACF
0xfcc11  ldarg.0
0xfcc12  ldc.i4.m1
0xfcc13  stfld    int32 <GetProperties>d__12::<>1__state
0xfcc18  ldarg.0
0xfcc19  ldarg.0
0xfcc1a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xfcc1f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0xfcc24  ldarg.0
0xfcc25  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0xfcc2a  ldstr    aCreated// "Created"
0xfcc2f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xfcc34  ldarg.0
0xfcc35  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0xfcc3a  ldc.i4.0
0xfcc3b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xfcc40  ldarg.0
0xfcc41  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0xfcc46  ldc.i4.1
0xfcc47  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xfcc4c  ldarg.0
0xfcc4d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0xfcc52  ldc.i4.0
0xfcc53  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xfcc58  ldarg.0
0xfcc59  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0xfcc5e  ldtoken  [mscorlib]System.String
0xfcc63  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfcc68  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xfcc6d  ldarg.0
0xfcc6e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0xfcc73  ldc.i4.1
0xfcc74  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xfcc79  ldarg.0
0xfcc7a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0xfcc7f  ldc.i4.1
0xfcc80  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xfcc85  ldarg.0
0xfcc86  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0xfcc8b  ldnull
0xfcc8c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xfcc91  ldarg.0
0xfcc92  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0xfcc97  ldstr    aCreated// "Created"
0xfcc9c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xfcca1  ldarg.0
0xfcca2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0xfcca7  ldnull
0xfcca8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xfccad  ldarg.0
0xfccae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0xfccb3  ldc.i4.0
0xfccb4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xfccb9  ldarg.0
0xfccba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0xfccbf  ldc.i4.1
0xfccc0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xfccc5  ldarg.0
0xfccc6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0xfcccb  ldc.i4.0
0xfcccc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xfccd1  ldarg.0
0xfccd2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal1
0xfccd7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>2__current
0xfccdc  ldarg.0
0xfccdd  ldc.i4.4
0xfccde  stfld    int32 <GetProperties>d__12::<>1__state
0xfcce3  ldc.i4.1
0xfcce4  stloc.0
0xfcce5  leave    loc_FDACF
0xfccea  ldarg.0
0xfcceb  ldc.i4.m1
0xfccec  stfld    int32 <GetProperties>d__12::<>1__state
0xfccf1  ldarg.0
0xfccf2  ldarg.0
0xfccf3  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xfccf8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0xfccfd  ldarg.0
0xfccfe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0xfcd03  ldstr    aCreatedby// "CreatedBy"
0xfcd08  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xfcd0d  ldarg.0
0xfcd0e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0xfcd13  ldc.i4.0
0xfcd14  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xfcd19  ldarg.0
0xfcd1a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0xfcd1f  ldc.i4.2
0xfcd20  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xfcd25  ldarg.0
0xfcd26  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0xfcd2b  ldc.i4.0
0xfcd2c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xfcd31  ldarg.0
0xfcd32  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0xfcd37  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal
0xfcd3c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfcd41  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xfcd46  ldarg.0
0xfcd47  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0xfcd4c  ldc.i4.1
0xfcd4d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xfcd52  ldarg.0
0xfcd53  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0xfcd58  ldc.i4.1
0xfcd59  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xfcd5e  ldarg.0
0xfcd5f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0xfcd64  ldnull
0xfcd65  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xfcd6a  ldarg.0
0xfcd6b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0xfcd70  ldstr    aCreatedby// "CreatedBy"
0xfcd75  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xfcd7a  ldarg.0
0xfcd7b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0xfcd80  ldnull
0xfcd81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xfcd86  ldarg.0
0xfcd87  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0xfcd8c  ldc.i4.0
0xfcd8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xfcd92  ldarg.0
0xfcd93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0xfcd98  ldc.i4.1
0xfcd99  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xfcd9e  ldarg.0
0xfcd9f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0xfcda4  ldc.i4.0
0xfcda5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xfcdaa  ldarg.0
0xfcdab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal2
0xfcdb0  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>2__current
0xfcdb5  ldarg.0
0xfcdb6  ldc.i4.5
0xfcdb7  stfld    int32 <GetProperties>d__12::<>1__state
0xfcdbc  ldc.i4.1
0xfcdbd  stloc.0
0xfcdbe  leave    loc_FDACF
0xfcdc3  ldarg.0
0xfcdc4  ldc.i4.m1
0xfcdc5  stfld    int32 <GetProperties>d__12::<>1__state
0xfcdca  ldarg.0
0xfcdcb  ldarg.0
0xfcdcc  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xfcdd1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0xfcdd6  ldarg.0
0xfcdd7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0xfcddc  ldstr    aExpiration// "Expiration"
0xfcde1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xfcde6  ldarg.0
0xfcde7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0xfcdec  ldc.i4.0
0xfcded  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xfcdf2  ldarg.0
0xfcdf3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0xfcdf8  ldc.i4.1
0xfcdf9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xfcdfe  ldarg.0
0xfcdff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0xfce04  ldc.i4.0
0xfce05  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xfce0a  ldarg.0
0xfce0b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0xfce10  ldtoken  [mscorlib]System.String
0xfce15  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfce1a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xfce1f  ldarg.0
0xfce20  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0xfce25  ldc.i4.1
0xfce26  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xfce2b  ldarg.0
0xfce2c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0xfce31  ldc.i4.1
0xfce32  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xfce37  ldarg.0
0xfce38  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0xfce3d  ldnull
0xfce3e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xfce43  ldarg.0
0xfce44  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__12::<>g__initLocal3
0xfce49  ldstr    aExpiration// "Expiration"
0xfce4e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
  ... truncated ...
```
