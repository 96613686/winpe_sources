# <GetProperties>d__17::MoveNext_0

- ea: `0x1a9df0`
- end: `0x1ab2ce`
- name: `<GetProperties>d__17::MoveNext_0`
- size: `5342`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xafcf0`
- `0x1a9df0`
- `0x1ab2f0`
- `0x1ab350`

## string_xrefs

- `0x1aa81d`: `DefaultShareLinkPermission`
- `0x1a9f00`: `accessRequestSettings`
- `0x1a9fd9`: `anonymousLinkExpirationRestrictionDays`
- `0x1aa351`: `canRequestAccessForGrantAccess`
- `0x1aa6cc`: `defaultLinkKind`
- `0x1aa7ab`: `defaultShareLinkPermission`
- `0x1aab1d`: `microserviceShareUiUrl`
- `0x1a9f6d`: `AccessRequestSettings`
- `0x1aa04b`: `AnonymousLinkExpirationRestrictionDays`
- `0x1aa3c3`: `CanRequestAccessForGrantAccess`
- `0x1aa73e`: `DefaultLinkKind`
- `0x1aab8a`: `MicroserviceShareUiUrl`

## pseudocode

```c

```

## disassembly

```asm
0x1a9df0  ldarg.0
0x1a9df1  ldfld    int32 <GetProperties>d__17::<>1__state
0x1a9df6  stloc.1
0x1a9df7  ldloc.1
0x1a9df8  switch   loc_1A9E6A, loc_1AB2C1, loc_1A9ED4, loc_1A9FC0, loc_1AA09E, loc_1AA17C, loc_1AA25A, loc_1AA338, loc_1AA416, loc_1AA4F5, loc_1AA5D4, loc_1AA6B3, loc_1AA792, loc_1AA871, loc_1AA94B, loc_1AAA25, loc_1AAB04, loc_1AABDE, loc_1AACB8, loc_1AAD92, loc_1AAE71, loc_1AAF4B, loc_1AB025, loc_1AB104, loc_1AB1E3, loc_1AB2BA
0x1a9e65  br       loc_1AB2C1
0x1a9e6a  ldarg.0
0x1a9e6b  ldc.i4.m1
0x1a9e6c  stfld    int32 <GetProperties>d__17::<>1__state
0x1a9e71  ldarg.0
0x1a9e72  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__17::proxyContext
0x1a9e77  brtrue.s loc_1A9E84
0x1a9e79  ldstr    aProxycontext// "proxyContext"
0x1a9e7e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1a9e83  throw
0x1a9e84  ldarg.0
0x1a9e85  ldarg.0
0x1a9e86  ldfld    class Microsoft.SharePoint.Sharing.SharingInformationServerStub <GetProperties>d__17::<>4__this
0x1a9e8b  ldarg.0
0x1a9e8c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__17::proxyContext
0x1a9e91  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Sharing.SharingInformationServerStub::<>n__FabricatedMethod1b(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x1a9e96  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x1a9e9b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__17::<>7__wrap19
0x1a9ea0  ldarg.0
0x1a9ea1  ldc.i4.1
0x1a9ea2  stfld    int32 <GetProperties>d__17::<>1__state
0x1a9ea7  br.s     loc_1A9EDB
0x1a9ea9  ldarg.0
0x1a9eaa  ldarg.0
0x1a9eab  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__17::<>7__wrap19
0x1a9eb0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x1a9eb5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<item>5__18
0x1a9eba  ldarg.0
0x1a9ebb  ldarg.0
0x1a9ebc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<item>5__18
0x1a9ec1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>2__current
0x1a9ec6  ldarg.0
0x1a9ec7  ldc.i4.2
0x1a9ec8  stfld    int32 <GetProperties>d__17::<>1__state
0x1a9ecd  ldc.i4.1
0x1a9ece  stloc.0
0x1a9ecf  leave    loc_1AB2CC
0x1a9ed4  ldarg.0
0x1a9ed5  ldc.i4.1
0x1a9ed6  stfld    int32 <GetProperties>d__17::<>1__state
0x1a9edb  ldarg.0
0x1a9edc  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__17::<>7__wrap19
0x1a9ee1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a9ee6  brtrue.s loc_1A9EA9
0x1a9ee8  ldarg.0
0x1a9ee9  call     instance void <GetProperties>d__17::<>m__Finally1a()
0x1a9eee  ldarg.0
0x1a9eef  ldarg.0
0x1a9ef0  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a9ef5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal0
0x1a9efa  ldarg.0
0x1a9efb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal0
0x1a9f00  ldstr    aAccessrequests// "accessRequestSettings"
0x1a9f05  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a9f0a  ldarg.0
0x1a9f0b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal0
0x1a9f10  ldc.i4.0
0x1a9f11  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a9f16  ldarg.0
0x1a9f17  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal0
0x1a9f1c  ldc.i4.2
0x1a9f1d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a9f22  ldarg.0
0x1a9f23  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal0
0x1a9f28  ldc.i4.1
0x1a9f29  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1a9f2e  ldarg.0
0x1a9f2f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal0
0x1a9f34  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.AccessRequestSettings
0x1a9f39  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a9f3e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1a9f43  ldarg.0
0x1a9f44  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal0
0x1a9f49  ldc.i4.1
0x1a9f4a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1a9f4f  ldarg.0
0x1a9f50  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal0
0x1a9f55  ldc.i4.1
0x1a9f56  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1a9f5b  ldarg.0
0x1a9f5c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal0
0x1a9f61  ldnull
0x1a9f62  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1a9f67  ldarg.0
0x1a9f68  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal0
0x1a9f6d  ldstr    aAccessrequests_0// "AccessRequestSettings"
0x1a9f72  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1a9f77  ldarg.0
0x1a9f78  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal0
0x1a9f7d  ldnull
0x1a9f7e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1a9f83  ldarg.0
0x1a9f84  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal0
0x1a9f89  ldc.i4.0
0x1a9f8a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1a9f8f  ldarg.0
0x1a9f90  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal0
0x1a9f95  ldc.i4.0
0x1a9f96  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1a9f9b  ldarg.0
0x1a9f9c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal0
0x1a9fa1  ldc.i4.0
0x1a9fa2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1a9fa7  ldarg.0
0x1a9fa8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal0
0x1a9fad  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>2__current
0x1a9fb2  ldarg.0
0x1a9fb3  ldc.i4.3
0x1a9fb4  stfld    int32 <GetProperties>d__17::<>1__state
0x1a9fb9  ldc.i4.1
0x1a9fba  stloc.0
0x1a9fbb  leave    loc_1AB2CC
0x1a9fc0  ldarg.0
0x1a9fc1  ldc.i4.m1
0x1a9fc2  stfld    int32 <GetProperties>d__17::<>1__state
0x1a9fc7  ldarg.0
0x1a9fc8  ldarg.0
0x1a9fc9  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a9fce  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal1
0x1a9fd3  ldarg.0
0x1a9fd4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal1
0x1a9fd9  ldstr    aAnonymouslinke// "anonymousLinkExpirationRestrictionDays"
0x1a9fde  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a9fe3  ldarg.0
0x1a9fe4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal1
0x1a9fe9  ldc.i4.0
0x1a9fea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a9fef  ldarg.0
0x1a9ff0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal1
0x1a9ff5  ldc.i4.1
0x1a9ff6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a9ffb  ldarg.0
0x1a9ffc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal1
0x1aa001  ldc.i4.0
0x1aa002  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1aa007  ldarg.0
0x1aa008  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal1
0x1aa00d  ldtoken  [mscorlib]System.Int32
0x1aa012  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1aa017  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1aa01c  ldarg.0
0x1aa01d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal1
0x1aa022  ldc.i4.0
0x1aa023  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1aa028  ldarg.0
0x1aa029  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal1
0x1aa02e  ldc.i4.1
0x1aa02f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1aa034  ldarg.0
0x1aa035  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal1
0x1aa03a  ldc.i4.0
0x1aa03b  box      [mscorlib]System.Int32
0x1aa040  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1aa045  ldarg.0
0x1aa046  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal1
0x1aa04b  ldstr    aAnonymouslinke_0// "AnonymousLinkExpirationRestrictionDays"
0x1aa050  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1aa055  ldarg.0
0x1aa056  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal1
0x1aa05b  ldnull
0x1aa05c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1aa061  ldarg.0
0x1aa062  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal1
0x1aa067  ldc.i4.0
0x1aa068  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1aa06d  ldarg.0
0x1aa06e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal1
0x1aa073  ldc.i4.0
0x1aa074  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1aa079  ldarg.0
0x1aa07a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal1
0x1aa07f  ldc.i4.0
0x1aa080  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1aa085  ldarg.0
0x1aa086  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal1
0x1aa08b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>2__current
0x1aa090  ldarg.0
0x1aa091  ldc.i4.4
0x1aa092  stfld    int32 <GetProperties>d__17::<>1__state
0x1aa097  ldc.i4.1
0x1aa098  stloc.0
0x1aa099  leave    loc_1AB2CC
0x1aa09e  ldarg.0
0x1aa09f  ldc.i4.m1
0x1aa0a0  stfld    int32 <GetProperties>d__17::<>1__state
0x1aa0a5  ldarg.0
0x1aa0a6  ldarg.0
0x1aa0a7  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1aa0ac  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal2
0x1aa0b1  ldarg.0
0x1aa0b2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal2
0x1aa0b7  ldstr    aBlockpeoplepic_0// "blockPeoplePickerAndSharing"
0x1aa0bc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1aa0c1  ldarg.0
0x1aa0c2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal2
0x1aa0c7  ldc.i4.0
0x1aa0c8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1aa0cd  ldarg.0
0x1aa0ce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal2
0x1aa0d3  ldc.i4.1
0x1aa0d4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1aa0d9  ldarg.0
0x1aa0da  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal2
0x1aa0df  ldc.i4.0
0x1aa0e0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1aa0e5  ldarg.0
0x1aa0e6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal2
0x1aa0eb  ldtoken  [mscorlib]System.Boolean
0x1aa0f0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1aa0f5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1aa0fa  ldarg.0
0x1aa0fb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal2
0x1aa100  ldc.i4.0
0x1aa101  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1aa106  ldarg.0
0x1aa107  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal2
0x1aa10c  ldc.i4.1
0x1aa10d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1aa112  ldarg.0
0x1aa113  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal2
0x1aa118  ldc.i4.0
0x1aa119  box      [mscorlib]System.Boolean
0x1aa11e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1aa123  ldarg.0
0x1aa124  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal2
0x1aa129  ldstr    aBlockpeoplepic// "BlockPeoplePickerAndSharing"
0x1aa12e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1aa133  ldarg.0
0x1aa134  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal2
0x1aa139  ldnull
0x1aa13a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1aa13f  ldarg.0
0x1aa140  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal2
0x1aa145  ldc.i4.0
0x1aa146  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1aa14b  ldarg.0
0x1aa14c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal2
0x1aa151  ldc.i4.0
0x1aa152  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1aa157  ldarg.0
0x1aa158  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal2
0x1aa15d  ldc.i4.0
0x1aa15e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1aa163  ldarg.0
0x1aa164  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal2
0x1aa169  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>2__current
0x1aa16e  ldarg.0
0x1aa16f  ldc.i4.5
0x1aa170  stfld    int32 <GetProperties>d__17::<>1__state
0x1aa175  ldc.i4.1
0x1aa176  stloc.0
0x1aa177  leave    loc_1AB2CC
0x1aa17c  ldarg.0
0x1aa17d  ldc.i4.m1
0x1aa17e  stfld    int32 <GetProperties>d__17::<>1__state
0x1aa183  ldarg.0
0x1aa184  ldarg.0
0x1aa185  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1aa18a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal3
0x1aa18f  ldarg.0
0x1aa190  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal3
0x1aa195  ldstr    aCanaddexternal// "canAddExternalPrincipal"
0x1aa19a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1aa19f  ldarg.0
0x1aa1a0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal3
0x1aa1a5  ldc.i4.0
0x1aa1a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1aa1ab  ldarg.0
0x1aa1ac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal3
0x1aa1b1  ldc.i4.1
0x1aa1b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1aa1b7  ldarg.0
0x1aa1b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal3
0x1aa1bd  ldc.i4.0
0x1aa1be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1aa1c3  ldarg.0
0x1aa1c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal3
0x1aa1c9  ldtoken  [mscorlib]System.Boolean
0x1aa1ce  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1aa1d3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1aa1d8  ldarg.0
0x1aa1d9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal3
0x1aa1de  ldc.i4.0
0x1aa1df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1aa1e4  ldarg.0
0x1aa1e5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal3
0x1aa1ea  ldc.i4.1
0x1aa1eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1aa1f0  ldarg.0
0x1aa1f1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal3
0x1aa1f6  ldc.i4.0
0x1aa1f7  box      [mscorlib]System.Boolean
0x1aa1fc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1aa201  ldarg.0
0x1aa202  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__17::<>g__initLocal3
  ... truncated ...
```
