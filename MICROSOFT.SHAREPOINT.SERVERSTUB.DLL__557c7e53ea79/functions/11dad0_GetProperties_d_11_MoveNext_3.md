# <GetProperties>d__11::MoveNext_3

- ea: `0x11dad0`
- end: `0x11ea7d`
- name: `<GetProperties>d__11::MoveNext_3`
- size: `4013`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x48a70`
- `0x11dad0`
- `0x11eaa0`
- `0x11eb00`

## string_xrefs

- `0x11dd84`: `AllowWriteCopy`
- `0x11ddf6`: `AllowWriteCopy`
- `0x11df40`: `DocumentAccessExpireDays`
- `0x11dfb2`: `DocumentAccessExpireDays`
- `0x11e104`: `EnableDocumentAccessExpire`
- `0x11e176`: `EnableDocumentAccessExpire`
- `0x11e3a1`: `EnableLicenseCacheExpire`
- `0x11e413`: `EnableLicenseCacheExpire`
- `0x11e639`: `LicenseCacheExpireDays`
- `0x11e6ab`: `LicenseCacheExpireDays`
- `0x11e9ab`: `TemplateId`
- `0x11ea18`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x11dad0  ldarg.0
0x11dad1  ldfld    int32 <GetProperties>d__11::<>1__state
0x11dad6  stloc.1
0x11dad7  ldloc.1
0x11dad8  switch   loc_11DB32, loc_11EA70, loc_11DB9C, loc_11DC8D, loc_11DD6B, loc_11DE49, loc_11DF27, loc_11E005, loc_11E0EB, loc_11E1CA, loc_11E2A9, loc_11E388, loc_11E467, loc_11E541, loc_11E620, loc_11E6FF, loc_11E7D9, loc_11E8B3, loc_11E992, loc_11EA69
0x11db2d  br       loc_11EA70
0x11db32  ldarg.0
0x11db33  ldc.i4.m1
0x11db34  stfld    int32 <GetProperties>d__11::<>1__state
0x11db39  ldarg.0
0x11db3a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__11::proxyContext
0x11db3f  brtrue.s loc_11DB4C
0x11db41  ldstr    aProxycontext// "proxyContext"
0x11db46  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11db4b  throw
0x11db4c  ldarg.0
0x11db4d  ldarg.0
0x11db4e  ldfld    class Microsoft.SharePoint.ServerStub.SPEffectiveInformationRightsManagementSettingsServerStub <GetProperties>d__11::<>4__this
0x11db53  ldarg.0
0x11db54  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__11::proxyContext
0x11db59  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPEffectiveInformationRightsManagementSettingsServerStub::<>n__FabricatedMethod15(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x11db5e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x11db63  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__11::<>7__wrap13
0x11db68  ldarg.0
0x11db69  ldc.i4.1
0x11db6a  stfld    int32 <GetProperties>d__11::<>1__state
0x11db6f  br.s     loc_11DBA3
0x11db71  ldarg.0
0x11db72  ldarg.0
0x11db73  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__11::<>7__wrap13
0x11db78  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x11db7d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<item>5__12
0x11db82  ldarg.0
0x11db83  ldarg.0
0x11db84  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<item>5__12
0x11db89  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>2__current
0x11db8e  ldarg.0
0x11db8f  ldc.i4.2
0x11db90  stfld    int32 <GetProperties>d__11::<>1__state
0x11db95  ldc.i4.1
0x11db96  stloc.0
0x11db97  leave    loc_11EA7B
0x11db9c  ldarg.0
0x11db9d  ldc.i4.1
0x11db9e  stfld    int32 <GetProperties>d__11::<>1__state
0x11dba3  ldarg.0
0x11dba4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__11::<>7__wrap13
0x11dba9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11dbae  brtrue.s loc_11DB71
0x11dbb0  ldarg.0
0x11dbb1  call     instance void <GetProperties>d__11::<>m__Finally14()
0x11dbb6  ldarg.0
0x11dbb7  ldarg.0
0x11dbb8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x11dbbd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal0
0x11dbc2  ldarg.0
0x11dbc3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal0
0x11dbc8  ldstr    aAllowprint// "AllowPrint"
0x11dbcd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x11dbd2  ldarg.0
0x11dbd3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal0
0x11dbd8  ldc.i4.0
0x11dbd9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x11dbde  ldarg.0
0x11dbdf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal0
0x11dbe4  ldc.i4.1
0x11dbe5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x11dbea  ldarg.0
0x11dbeb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal0
0x11dbf0  ldc.i4.0
0x11dbf1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x11dbf6  ldarg.0
0x11dbf7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal0
0x11dbfc  ldtoken  [mscorlib]System.Boolean
0x11dc01  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11dc06  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x11dc0b  ldarg.0
0x11dc0c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal0
0x11dc11  ldc.i4.1
0x11dc12  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x11dc17  ldarg.0
0x11dc18  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal0
0x11dc1d  ldc.i4.1
0x11dc1e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x11dc23  ldarg.0
0x11dc24  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal0
0x11dc29  ldc.i4.0
0x11dc2a  box      [mscorlib]System.Boolean
0x11dc2f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x11dc34  ldarg.0
0x11dc35  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal0
0x11dc3a  ldstr    aAllowprint// "AllowPrint"
0x11dc3f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x11dc44  ldarg.0
0x11dc45  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal0
0x11dc4a  ldnull
0x11dc4b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x11dc50  ldarg.0
0x11dc51  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal0
0x11dc56  ldc.i4.0
0x11dc57  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x11dc5c  ldarg.0
0x11dc5d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal0
0x11dc62  ldc.i4.1
0x11dc63  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x11dc68  ldarg.0
0x11dc69  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal0
0x11dc6e  ldc.i4.0
0x11dc6f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x11dc74  ldarg.0
0x11dc75  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal0
0x11dc7a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>2__current
0x11dc7f  ldarg.0
0x11dc80  ldc.i4.3
0x11dc81  stfld    int32 <GetProperties>d__11::<>1__state
0x11dc86  ldc.i4.1
0x11dc87  stloc.0
0x11dc88  leave    loc_11EA7B
0x11dc8d  ldarg.0
0x11dc8e  ldc.i4.m1
0x11dc8f  stfld    int32 <GetProperties>d__11::<>1__state
0x11dc94  ldarg.0
0x11dc95  ldarg.0
0x11dc96  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x11dc9b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal1
0x11dca0  ldarg.0
0x11dca1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal1
0x11dca6  ldstr    aAllowscript// "AllowScript"
0x11dcab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x11dcb0  ldarg.0
0x11dcb1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal1
0x11dcb6  ldc.i4.0
0x11dcb7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x11dcbc  ldarg.0
0x11dcbd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal1
0x11dcc2  ldc.i4.1
0x11dcc3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x11dcc8  ldarg.0
0x11dcc9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal1
0x11dcce  ldc.i4.0
0x11dccf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x11dcd4  ldarg.0
0x11dcd5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal1
0x11dcda  ldtoken  [mscorlib]System.Boolean
0x11dcdf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11dce4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x11dce9  ldarg.0
0x11dcea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal1
0x11dcef  ldc.i4.1
0x11dcf0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x11dcf5  ldarg.0
0x11dcf6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal1
0x11dcfb  ldc.i4.1
0x11dcfc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x11dd01  ldarg.0
0x11dd02  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal1
0x11dd07  ldc.i4.0
0x11dd08  box      [mscorlib]System.Boolean
0x11dd0d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x11dd12  ldarg.0
0x11dd13  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal1
0x11dd18  ldstr    aAllowscript// "AllowScript"
0x11dd1d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x11dd22  ldarg.0
0x11dd23  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal1
0x11dd28  ldnull
0x11dd29  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x11dd2e  ldarg.0
0x11dd2f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal1
0x11dd34  ldc.i4.0
0x11dd35  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x11dd3a  ldarg.0
0x11dd3b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal1
0x11dd40  ldc.i4.1
0x11dd41  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x11dd46  ldarg.0
0x11dd47  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal1
0x11dd4c  ldc.i4.0
0x11dd4d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x11dd52  ldarg.0
0x11dd53  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal1
0x11dd58  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>2__current
0x11dd5d  ldarg.0
0x11dd5e  ldc.i4.4
0x11dd5f  stfld    int32 <GetProperties>d__11::<>1__state
0x11dd64  ldc.i4.1
0x11dd65  stloc.0
0x11dd66  leave    loc_11EA7B
0x11dd6b  ldarg.0
0x11dd6c  ldc.i4.m1
0x11dd6d  stfld    int32 <GetProperties>d__11::<>1__state
0x11dd72  ldarg.0
0x11dd73  ldarg.0
0x11dd74  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x11dd79  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal2
0x11dd7e  ldarg.0
0x11dd7f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal2
0x11dd84  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x11dd89  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x11dd8e  ldarg.0
0x11dd8f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal2
0x11dd94  ldc.i4.0
0x11dd95  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x11dd9a  ldarg.0
0x11dd9b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal2
0x11dda0  ldc.i4.1
0x11dda1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x11dda6  ldarg.0
0x11dda7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal2
0x11ddac  ldc.i4.0
0x11ddad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x11ddb2  ldarg.0
0x11ddb3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal2
0x11ddb8  ldtoken  [mscorlib]System.Boolean
0x11ddbd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11ddc2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x11ddc7  ldarg.0
0x11ddc8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal2
0x11ddcd  ldc.i4.1
0x11ddce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x11ddd3  ldarg.0
0x11ddd4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal2
0x11ddd9  ldc.i4.1
0x11ddda  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x11dddf  ldarg.0
0x11dde0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal2
0x11dde5  ldc.i4.0
0x11dde6  box      [mscorlib]System.Boolean
0x11ddeb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x11ddf0  ldarg.0
0x11ddf1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal2
0x11ddf6  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x11ddfb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x11de00  ldarg.0
0x11de01  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal2
0x11de06  ldnull
0x11de07  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x11de0c  ldarg.0
0x11de0d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal2
0x11de12  ldc.i4.0
0x11de13  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x11de18  ldarg.0
0x11de19  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal2
0x11de1e  ldc.i4.1
0x11de1f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x11de24  ldarg.0
0x11de25  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal2
0x11de2a  ldc.i4.0
0x11de2b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x11de30  ldarg.0
0x11de31  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal2
0x11de36  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>2__current
0x11de3b  ldarg.0
0x11de3c  ldc.i4.5
0x11de3d  stfld    int32 <GetProperties>d__11::<>1__state
0x11de42  ldc.i4.1
0x11de43  stloc.0
0x11de44  leave    loc_11EA7B
0x11de49  ldarg.0
0x11de4a  ldc.i4.m1
0x11de4b  stfld    int32 <GetProperties>d__11::<>1__state
0x11de50  ldarg.0
0x11de51  ldarg.0
0x11de52  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x11de57  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal3
0x11de5c  ldarg.0
0x11de5d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal3
0x11de62  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x11de67  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x11de6c  ldarg.0
0x11de6d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal3
0x11de72  ldc.i4.0
0x11de73  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x11de78  ldarg.0
0x11de79  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal3
0x11de7e  ldc.i4.1
0x11de7f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x11de84  ldarg.0
0x11de85  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal3
0x11de8a  ldc.i4.0
0x11de8b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x11de90  ldarg.0
0x11de91  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal3
0x11de96  ldtoken  [mscorlib]System.Boolean
0x11de9b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11dea0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x11dea5  ldarg.0
0x11dea6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal3
0x11deab  ldc.i4.1
0x11deac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x11deb1  ldarg.0
0x11deb2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal3
0x11deb7  ldc.i4.1
0x11deb8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x11debd  ldarg.0
0x11debe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal3
0x11dec3  ldc.i4.0
0x11dec4  box      [mscorlib]System.Boolean
0x11dec9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x11dece  ldarg.0
  ... truncated ...
```
