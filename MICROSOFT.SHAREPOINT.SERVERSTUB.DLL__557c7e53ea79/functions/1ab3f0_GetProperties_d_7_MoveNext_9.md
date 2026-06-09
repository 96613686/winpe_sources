# <GetProperties>d__7::MoveNext_9

- ea: `0x1ab3f0`
- end: `0x1abaa8`
- name: `<GetProperties>d__7::MoveNext_9`
- size: `1720`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xb00c0`
- `0x1ab3f0`
- `0x1abad0`
- `0x1abb30`

## string_xrefs

- `0x1ab4c0`: `canGetEditLink`
- `0x1ab599`: `canGetReadLink`
- `0x1ab74b`: `canManageEditLink`
- `0x1ab824`: `canManageReadLink`
- `0x1ab8fd`: `linkExpiration`
- `0x1ab52d`: `CanGetEditLink`
- `0x1ab606`: `CanGetReadLink`
- `0x1ab7b8`: `CanManageEditLink`
- `0x1ab891`: `CanManageReadLink`
- `0x1ab96a`: `LinkExpiration`

## pseudocode

```c

```

## disassembly

```asm
0x1ab3f0  ldarg.0
0x1ab3f1  ldfld    int32 <GetProperties>d__7::<>1__state
0x1ab3f6  stloc.1
0x1ab3f7  ldloc.1
0x1ab3f8  switch   loc_1AB42A, loc_1ABA9B, loc_1AB494, loc_1AB580, loc_1AB659, loc_1AB732, loc_1AB80B, loc_1AB8E4, loc_1AB9BD, loc_1ABA94
0x1ab425  br       loc_1ABA9B
0x1ab42a  ldarg.0
0x1ab42b  ldc.i4.m1
0x1ab42c  stfld    int32 <GetProperties>d__7::<>1__state
0x1ab431  ldarg.0
0x1ab432  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__7::proxyContext
0x1ab437  brtrue.s loc_1AB444
0x1ab439  ldstr    aProxycontext// "proxyContext"
0x1ab43e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1ab443  throw
0x1ab444  ldarg.0
0x1ab445  ldarg.0
0x1ab446  ldfld    class Microsoft.SharePoint.Sharing.SharingLinkAbilitiesValueTypeConverter <GetProperties>d__7::<>4__this
0x1ab44b  ldarg.0
0x1ab44c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__7::proxyContext
0x1ab451  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Sharing.SharingLinkAbilitiesValueTypeConverter::<>n__FabricatedMethodb(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x1ab456  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x1ab45b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__7::<>7__wrap9
0x1ab460  ldarg.0
0x1ab461  ldc.i4.1
0x1ab462  stfld    int32 <GetProperties>d__7::<>1__state
0x1ab467  br.s     loc_1AB49B
0x1ab469  ldarg.0
0x1ab46a  ldarg.0
0x1ab46b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__7::<>7__wrap9
0x1ab470  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x1ab475  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<item>5__8
0x1ab47a  ldarg.0
0x1ab47b  ldarg.0
0x1ab47c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<item>5__8
0x1ab481  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>2__current
0x1ab486  ldarg.0
0x1ab487  ldc.i4.2
0x1ab488  stfld    int32 <GetProperties>d__7::<>1__state
0x1ab48d  ldc.i4.1
0x1ab48e  stloc.0
0x1ab48f  leave    loc_1ABAA6
0x1ab494  ldarg.0
0x1ab495  ldc.i4.1
0x1ab496  stfld    int32 <GetProperties>d__7::<>1__state
0x1ab49b  ldarg.0
0x1ab49c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__7::<>7__wrap9
0x1ab4a1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1ab4a6  brtrue.s loc_1AB469
0x1ab4a8  ldarg.0
0x1ab4a9  call     instance void <GetProperties>d__7::<>m__Finallya()
0x1ab4ae  ldarg.0
0x1ab4af  ldarg.0
0x1ab4b0  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1ab4b5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x1ab4ba  ldarg.0
0x1ab4bb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x1ab4c0  ldstr    aCangeteditlink// "canGetEditLink"
0x1ab4c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1ab4ca  ldarg.0
0x1ab4cb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x1ab4d0  ldc.i4.0
0x1ab4d1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1ab4d6  ldarg.0
0x1ab4d7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x1ab4dc  ldc.i4.2
0x1ab4dd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ab4e2  ldarg.0
0x1ab4e3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x1ab4e8  ldc.i4.0
0x1ab4e9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1ab4ee  ldarg.0
0x1ab4ef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x1ab4f4  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingAbilityStatus
0x1ab4f9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ab4fe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1ab503  ldarg.0
0x1ab504  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x1ab509  ldc.i4.1
0x1ab50a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1ab50f  ldarg.0
0x1ab510  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x1ab515  ldc.i4.1
0x1ab516  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1ab51b  ldarg.0
0x1ab51c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x1ab521  ldnull
0x1ab522  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1ab527  ldarg.0
0x1ab528  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x1ab52d  ldstr    aCangeteditlink_0// "CanGetEditLink"
0x1ab532  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1ab537  ldarg.0
0x1ab538  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x1ab53d  ldnull
0x1ab53e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1ab543  ldarg.0
0x1ab544  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x1ab549  ldc.i4.0
0x1ab54a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1ab54f  ldarg.0
0x1ab550  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x1ab555  ldc.i4.0
0x1ab556  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1ab55b  ldarg.0
0x1ab55c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x1ab561  ldc.i4.0
0x1ab562  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1ab567  ldarg.0
0x1ab568  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal0
0x1ab56d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>2__current
0x1ab572  ldarg.0
0x1ab573  ldc.i4.3
0x1ab574  stfld    int32 <GetProperties>d__7::<>1__state
0x1ab579  ldc.i4.1
0x1ab57a  stloc.0
0x1ab57b  leave    loc_1ABAA6
0x1ab580  ldarg.0
0x1ab581  ldc.i4.m1
0x1ab582  stfld    int32 <GetProperties>d__7::<>1__state
0x1ab587  ldarg.0
0x1ab588  ldarg.0
0x1ab589  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1ab58e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x1ab593  ldarg.0
0x1ab594  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x1ab599  ldstr    aCangetreadlink// "canGetReadLink"
0x1ab59e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1ab5a3  ldarg.0
0x1ab5a4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x1ab5a9  ldc.i4.0
0x1ab5aa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1ab5af  ldarg.0
0x1ab5b0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x1ab5b5  ldc.i4.2
0x1ab5b6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ab5bb  ldarg.0
0x1ab5bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x1ab5c1  ldc.i4.0
0x1ab5c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1ab5c7  ldarg.0
0x1ab5c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x1ab5cd  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingAbilityStatus
0x1ab5d2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ab5d7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1ab5dc  ldarg.0
0x1ab5dd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x1ab5e2  ldc.i4.1
0x1ab5e3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1ab5e8  ldarg.0
0x1ab5e9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x1ab5ee  ldc.i4.1
0x1ab5ef  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1ab5f4  ldarg.0
0x1ab5f5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x1ab5fa  ldnull
0x1ab5fb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1ab600  ldarg.0
0x1ab601  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x1ab606  ldstr    aCangetreadlink_0// "CanGetReadLink"
0x1ab60b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1ab610  ldarg.0
0x1ab611  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x1ab616  ldnull
0x1ab617  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1ab61c  ldarg.0
0x1ab61d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x1ab622  ldc.i4.0
0x1ab623  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1ab628  ldarg.0
0x1ab629  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x1ab62e  ldc.i4.0
0x1ab62f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1ab634  ldarg.0
0x1ab635  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x1ab63a  ldc.i4.0
0x1ab63b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1ab640  ldarg.0
0x1ab641  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal1
0x1ab646  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>2__current
0x1ab64b  ldarg.0
0x1ab64c  ldc.i4.4
0x1ab64d  stfld    int32 <GetProperties>d__7::<>1__state
0x1ab652  ldc.i4.1
0x1ab653  stloc.0
0x1ab654  leave    loc_1ABAA6
0x1ab659  ldarg.0
0x1ab65a  ldc.i4.m1
0x1ab65b  stfld    int32 <GetProperties>d__7::<>1__state
0x1ab660  ldarg.0
0x1ab661  ldarg.0
0x1ab662  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1ab667  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x1ab66c  ldarg.0
0x1ab66d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x1ab672  ldstr    aCanhaveexterna// "canHaveExternalUsers"
0x1ab677  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1ab67c  ldarg.0
0x1ab67d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x1ab682  ldc.i4.0
0x1ab683  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1ab688  ldarg.0
0x1ab689  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x1ab68e  ldc.i4.2
0x1ab68f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ab694  ldarg.0
0x1ab695  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x1ab69a  ldc.i4.0
0x1ab69b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1ab6a0  ldarg.0
0x1ab6a1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x1ab6a6  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingAbilityStatus
0x1ab6ab  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ab6b0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1ab6b5  ldarg.0
0x1ab6b6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x1ab6bb  ldc.i4.1
0x1ab6bc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1ab6c1  ldarg.0
0x1ab6c2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x1ab6c7  ldc.i4.1
0x1ab6c8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1ab6cd  ldarg.0
0x1ab6ce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x1ab6d3  ldnull
0x1ab6d4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1ab6d9  ldarg.0
0x1ab6da  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x1ab6df  ldstr    aCanhaveexterna_0// "CanHaveExternalUsers"
0x1ab6e4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1ab6e9  ldarg.0
0x1ab6ea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x1ab6ef  ldnull
0x1ab6f0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1ab6f5  ldarg.0
0x1ab6f6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x1ab6fb  ldc.i4.0
0x1ab6fc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1ab701  ldarg.0
0x1ab702  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x1ab707  ldc.i4.0
0x1ab708  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1ab70d  ldarg.0
0x1ab70e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x1ab713  ldc.i4.0
0x1ab714  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1ab719  ldarg.0
0x1ab71a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal2
0x1ab71f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>2__current
0x1ab724  ldarg.0
0x1ab725  ldc.i4.5
0x1ab726  stfld    int32 <GetProperties>d__7::<>1__state
0x1ab72b  ldc.i4.1
0x1ab72c  stloc.0
0x1ab72d  leave    loc_1ABAA6
0x1ab732  ldarg.0
0x1ab733  ldc.i4.m1
0x1ab734  stfld    int32 <GetProperties>d__7::<>1__state
0x1ab739  ldarg.0
0x1ab73a  ldarg.0
0x1ab73b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1ab740  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x1ab745  ldarg.0
0x1ab746  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x1ab74b  ldstr    aCanmanageeditl// "canManageEditLink"
0x1ab750  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1ab755  ldarg.0
0x1ab756  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x1ab75b  ldc.i4.0
0x1ab75c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1ab761  ldarg.0
0x1ab762  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x1ab767  ldc.i4.2
0x1ab768  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ab76d  ldarg.0
0x1ab76e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x1ab773  ldc.i4.0
0x1ab774  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1ab779  ldarg.0
0x1ab77a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x1ab77f  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingAbilityStatus
0x1ab784  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ab789  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1ab78e  ldarg.0
0x1ab78f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x1ab794  ldc.i4.1
0x1ab795  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1ab79a  ldarg.0
0x1ab79b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x1ab7a0  ldc.i4.1
0x1ab7a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1ab7a6  ldarg.0
0x1ab7a7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x1ab7ac  ldnull
0x1ab7ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1ab7b2  ldarg.0
0x1ab7b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7::<>g__initLocal3
0x1ab7b8  ldstr    aCanmanageeditl_0// "CanManageEditLink"
0x1ab7bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1ab7c2  ldarg.0
  ... truncated ...
```
