# <GetProperties>d__27::MoveNext_0

- ea: `0xf5730`
- end: `0xf7a3c`
- name: `<GetProperties>d__27::MoveNext_0`
- size: `8972`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x2ce60`
- `0xf5730`
- `0xf7a60`
- `0xf7ac0`

## string_xrefs

- `0xf5880`: `AccessRequestMode`
- `0xf58f2`: `AccessRequestMode`
- `0xf5a3c`: `CanCurrentUserManageOrganizationReadonlyLink`
- `0xf5aae`: `CanCurrentUserManageOrganizationReadonlyLink`
- `0xf5b1a`: `CanCurrentUserManageOrganizationReadWriteLink`
- `0xf5b8c`: `CanCurrentUserManageOrganizationReadWriteLink`
- `0xf5bf8`: `CanCurrentUserManageReadonlyLink`
- `0xf5c6a`: `CanCurrentUserManageReadonlyLink`
- `0xf5cd6`: `CanCurrentUserManageReadWriteLink`
- `0xf5d48`: `CanCurrentUserManageReadWriteLink`
- `0xf5db4`: `CanCurrentUserRetrieveOrganizationReadonlyLink`
- `0xf5e26`: `CanCurrentUserRetrieveOrganizationReadonlyLink`
- `0xf5e93`: `CanCurrentUserRetrieveOrganizationReadWriteLink`
- `0xf5f05`: `CanCurrentUserRetrieveOrganizationReadWriteLink`
- `0xf5f72`: `CanCurrentUserRetrieveReadonlyLink`
- `0xf5fe4`: `CanCurrentUserRetrieveReadonlyLink`
- `0xf6051`: `CanCurrentUserRetrieveReadWriteLink`
- `0xf60c3`: `CanCurrentUserRetrieveReadWriteLink`
- `0xf63cd`: `CanSendLink`
- `0xf643f`: `CanSendLink`
- `0xf658b`: `DefaultShareLinkPermission`
- `0xf65fd`: `DefaultShareLinkPermission`
- `0xf666a`: `DefaultShareLinkType`
- `0xf66dc`: `DefaultShareLinkType`
- `0xf6902`: `HasReadRole`
- `0xf6974`: `HasReadRole`
- `0xf69e1`: `InheritingWebLink`
- `0xf6a4e`: `InheritingWebLink`
- `0xf7286`: `RequiredAnonymousLinkExpirationInDays`
- `0xf72f8`: `RequiredAnonymousLinkExpirationInDays`
- `0xf788b`: `SupportsAclPropagation`
- `0xf78fd`: `SupportsAclPropagation`

## pseudocode

```c

```

## disassembly

```asm
0xf5730  ldarg.0
0xf5731  ldfld    int32 <GetProperties>d__27::<>1__state
0xf5736  stloc.1
0xf5737  ldloc.1
0xf5738  switch   loc_F57EA, loc_F7A2F, loc_F5854, loc_F5945, loc_F5A23, loc_F5B01, loc_F5BDF, loc_F5CBD, loc_F5D9B, loc_F5E7A, loc_F5F59, loc_F6038, loc_F6117, loc_F61F6, loc_F62D5, loc_F63B4, loc_F6493, loc_F6572, loc_F6651, loc_F6730, loc_F680A, loc_F68E9, loc_F69C8, loc_F6AA2, loc_F6B81, loc_F6C60, loc_F6D3F, loc_F6E19, loc_F6EF3, loc_F6FCD, loc_F70B4, loc_F718E, loc_F726D, loc_F734C, loc_F7426, loc_F7505, loc_F75DF, loc_F76B9, loc_F7798, loc_F7872, loc_F7951, loc_F7A28
0xf57e5  br       loc_F7A2F
0xf57ea  ldarg.0
0xf57eb  ldc.i4.m1
0xf57ec  stfld    int32 <GetProperties>d__27::<>1__state
0xf57f1  ldarg.0
0xf57f2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__27::proxyContext
0xf57f7  brtrue.s loc_F5804
0xf57f9  ldstr    aProxycontext// "proxyContext"
0xf57fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf5803  throw
0xf5804  ldarg.0
0xf5805  ldarg.0
0xf5806  ldfld    class Microsoft.SharePoint.ServerStub.ObjectSharingSettingsServerStub <GetProperties>d__27::<>4__this
0xf580b  ldarg.0
0xf580c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__27::proxyContext
0xf5811  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.ObjectSharingSettingsServerStub::<>n__FabricatedMethod2b(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0xf5816  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0xf581b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__27::<>7__wrap29
0xf5820  ldarg.0
0xf5821  ldc.i4.1
0xf5822  stfld    int32 <GetProperties>d__27::<>1__state
0xf5827  br.s     loc_F585B
0xf5829  ldarg.0
0xf582a  ldarg.0
0xf582b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__27::<>7__wrap29
0xf5830  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0xf5835  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<item>5__28
0xf583a  ldarg.0
0xf583b  ldarg.0
0xf583c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<item>5__28
0xf5841  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>2__current
0xf5846  ldarg.0
0xf5847  ldc.i4.2
0xf5848  stfld    int32 <GetProperties>d__27::<>1__state
0xf584d  ldc.i4.1
0xf584e  stloc.0
0xf584f  leave    loc_F7A3A
0xf5854  ldarg.0
0xf5855  ldc.i4.1
0xf5856  stfld    int32 <GetProperties>d__27::<>1__state
0xf585b  ldarg.0
0xf585c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__27::<>7__wrap29
0xf5861  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xf5866  brtrue.s loc_F5829
0xf5868  ldarg.0
0xf5869  call     instance void <GetProperties>d__27::<>m__Finally2a()
0xf586e  ldarg.0
0xf586f  ldarg.0
0xf5870  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xf5875  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal0
0xf587a  ldarg.0
0xf587b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal0
0xf5880  ldstr    aAccessrequestm// "AccessRequestMode"
0xf5885  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xf588a  ldarg.0
0xf588b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal0
0xf5890  ldc.i4.0
0xf5891  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xf5896  ldarg.0
0xf5897  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal0
0xf589c  ldc.i4.1
0xf589d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xf58a2  ldarg.0
0xf58a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal0
0xf58a8  ldc.i4.0
0xf58a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xf58ae  ldarg.0
0xf58af  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal0
0xf58b4  ldtoken  [mscorlib]System.Boolean
0xf58b9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf58be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xf58c3  ldarg.0
0xf58c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal0
0xf58c9  ldc.i4.1
0xf58ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xf58cf  ldarg.0
0xf58d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal0
0xf58d5  ldc.i4.1
0xf58d6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xf58db  ldarg.0
0xf58dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal0
0xf58e1  ldc.i4.0
0xf58e2  box      [mscorlib]System.Boolean
0xf58e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xf58ec  ldarg.0
0xf58ed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal0
0xf58f2  ldstr    aAccessrequestm// "AccessRequestMode"
0xf58f7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xf58fc  ldarg.0
0xf58fd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal0
0xf5902  ldnull
0xf5903  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xf5908  ldarg.0
0xf5909  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal0
0xf590e  ldc.i4.0
0xf590f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xf5914  ldarg.0
0xf5915  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal0
0xf591a  ldc.i4.0
0xf591b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xf5920  ldarg.0
0xf5921  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal0
0xf5926  ldc.i4.0
0xf5927  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xf592c  ldarg.0
0xf592d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal0
0xf5932  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>2__current
0xf5937  ldarg.0
0xf5938  ldc.i4.3
0xf5939  stfld    int32 <GetProperties>d__27::<>1__state
0xf593e  ldc.i4.1
0xf593f  stloc.0
0xf5940  leave    loc_F7A3A
0xf5945  ldarg.0
0xf5946  ldc.i4.m1
0xf5947  stfld    int32 <GetProperties>d__27::<>1__state
0xf594c  ldarg.0
0xf594d  ldarg.0
0xf594e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xf5953  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal1
0xf5958  ldarg.0
0xf5959  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal1
0xf595e  ldstr    aBlockpeoplepic// "BlockPeoplePickerAndSharing"
0xf5963  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xf5968  ldarg.0
0xf5969  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal1
0xf596e  ldc.i4.0
0xf596f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xf5974  ldarg.0
0xf5975  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal1
0xf597a  ldc.i4.1
0xf597b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xf5980  ldarg.0
0xf5981  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal1
0xf5986  ldc.i4.0
0xf5987  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xf598c  ldarg.0
0xf598d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal1
0xf5992  ldtoken  [mscorlib]System.Boolean
0xf5997  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf599c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xf59a1  ldarg.0
0xf59a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal1
0xf59a7  ldc.i4.1
0xf59a8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xf59ad  ldarg.0
0xf59ae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal1
0xf59b3  ldc.i4.1
0xf59b4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xf59b9  ldarg.0
0xf59ba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal1
0xf59bf  ldc.i4.0
0xf59c0  box      [mscorlib]System.Boolean
0xf59c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xf59ca  ldarg.0
0xf59cb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal1
0xf59d0  ldstr    aBlockpeoplepic// "BlockPeoplePickerAndSharing"
0xf59d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xf59da  ldarg.0
0xf59db  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal1
0xf59e0  ldnull
0xf59e1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xf59e6  ldarg.0
0xf59e7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal1
0xf59ec  ldc.i4.0
0xf59ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xf59f2  ldarg.0
0xf59f3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal1
0xf59f8  ldc.i4.0
0xf59f9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xf59fe  ldarg.0
0xf59ff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal1
0xf5a04  ldc.i4.0
0xf5a05  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xf5a0a  ldarg.0
0xf5a0b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal1
0xf5a10  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>2__current
0xf5a15  ldarg.0
0xf5a16  ldc.i4.4
0xf5a17  stfld    int32 <GetProperties>d__27::<>1__state
0xf5a1c  ldc.i4.1
0xf5a1d  stloc.0
0xf5a1e  leave    loc_F7A3A
0xf5a23  ldarg.0
0xf5a24  ldc.i4.m1
0xf5a25  stfld    int32 <GetProperties>d__27::<>1__state
0xf5a2a  ldarg.0
0xf5a2b  ldarg.0
0xf5a2c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xf5a31  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal2
0xf5a36  ldarg.0
0xf5a37  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal2
0xf5a3c  ldstr    aCancurrentuser// "CanCurrentUserManageOrganizationReadonl"...
0xf5a41  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xf5a46  ldarg.0
0xf5a47  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal2
0xf5a4c  ldc.i4.0
0xf5a4d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xf5a52  ldarg.0
0xf5a53  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal2
0xf5a58  ldc.i4.1
0xf5a59  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xf5a5e  ldarg.0
0xf5a5f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal2
0xf5a64  ldc.i4.0
0xf5a65  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xf5a6a  ldarg.0
0xf5a6b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal2
0xf5a70  ldtoken  [mscorlib]System.Boolean
0xf5a75  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf5a7a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xf5a7f  ldarg.0
0xf5a80  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal2
0xf5a85  ldc.i4.1
0xf5a86  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xf5a8b  ldarg.0
0xf5a8c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal2
0xf5a91  ldc.i4.1
0xf5a92  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xf5a97  ldarg.0
0xf5a98  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal2
0xf5a9d  ldc.i4.0
0xf5a9e  box      [mscorlib]System.Boolean
0xf5aa3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xf5aa8  ldarg.0
0xf5aa9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal2
0xf5aae  ldstr    aCancurrentuser// "CanCurrentUserManageOrganizationReadonl"...
0xf5ab3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xf5ab8  ldarg.0
0xf5ab9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal2
0xf5abe  ldnull
0xf5abf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xf5ac4  ldarg.0
0xf5ac5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal2
0xf5aca  ldc.i4.0
0xf5acb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xf5ad0  ldarg.0
0xf5ad1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal2
0xf5ad6  ldc.i4.0
0xf5ad7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xf5adc  ldarg.0
0xf5add  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal2
0xf5ae2  ldc.i4.0
0xf5ae3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xf5ae8  ldarg.0
0xf5ae9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal2
0xf5aee  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>2__current
0xf5af3  ldarg.0
0xf5af4  ldc.i4.5
0xf5af5  stfld    int32 <GetProperties>d__27::<>1__state
0xf5afa  ldc.i4.1
0xf5afb  stloc.0
0xf5afc  leave    loc_F7A3A
0xf5b01  ldarg.0
0xf5b02  ldc.i4.m1
0xf5b03  stfld    int32 <GetProperties>d__27::<>1__state
0xf5b08  ldarg.0
0xf5b09  ldarg.0
0xf5b0a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xf5b0f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal3
0xf5b14  ldarg.0
0xf5b15  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal3
0xf5b1a  ldstr    aCancurrentuser_0// "CanCurrentUserManageOrganizationReadWri"...
0xf5b1f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xf5b24  ldarg.0
0xf5b25  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal3
0xf5b2a  ldc.i4.0
0xf5b2b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xf5b30  ldarg.0
0xf5b31  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal3
0xf5b36  ldc.i4.1
0xf5b37  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xf5b3c  ldarg.0
0xf5b3d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal3
0xf5b42  ldc.i4.0
0xf5b43  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xf5b48  ldarg.0
0xf5b49  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal3
0xf5b4e  ldtoken  [mscorlib]System.Boolean
0xf5b53  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf5b58  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xf5b5d  ldarg.0
0xf5b5e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal3
0xf5b63  ldc.i4.1
0xf5b64  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xf5b69  ldarg.0
0xf5b6a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal3
0xf5b6f  ldc.i4.1
0xf5b70  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xf5b75  ldarg.0
0xf5b76  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__27::<>g__initLocal3
0xf5b7b  ldc.i4.0
0xf5b7c  box      [mscorlib]System.Boolean
0xf5b81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xf5b86  ldarg.0
  ... truncated ...
```
