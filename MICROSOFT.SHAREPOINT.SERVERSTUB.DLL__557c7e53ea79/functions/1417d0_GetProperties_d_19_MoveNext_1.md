# <GetProperties>d__19::MoveNext_1

- ea: `0x1417d0`
- end: `0x1425b7`
- name: `<GetProperties>d__19::MoveNext_1`
- size: `3559`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x66b80`
- `0x1417d0`
- `0x1425e0`
- `0x142640`

## string_xrefs

- `0x141a7c`: `AllowWriteCopy`
- `0x141aee`: `AllowWriteCopy`
- `0x141c38`: `DocumentAccessExpireDays`
- `0x141caa`: `DocumentAccessExpireDays`
- `0x141dfc`: `EnableDocumentAccessExpire`
- `0x141e6e`: `EnableDocumentAccessExpire`
- `0x142099`: `EnableLicenseCacheExpire`
- `0x14210b`: `EnableLicenseCacheExpire`
- `0x142252`: `LicenseCacheExpireDays`
- `0x1422c4`: `LicenseCacheExpireDays`
- `0x1424e5`: `TemplateId`
- `0x142552`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x1417d0  ldarg.0
0x1417d1  ldfld    int32 <GetProperties>d__19::<>1__state
0x1417d6  stloc.1
0x1417d7  ldloc.1
0x1417d8  switch   loc_14182A, loc_1425AA, loc_141894, loc_141985, loc_141A63, loc_141B41, loc_141C1F, loc_141CFD, loc_141DE3, loc_141EC2, loc_141FA1, loc_142080, loc_14215F, loc_142239, loc_142318, loc_1423F2, loc_1424CC, loc_1425A3
0x141825  br       loc_1425AA
0x14182a  ldarg.0
0x14182b  ldc.i4.m1
0x14182c  stfld    int32 <GetProperties>d__19::<>1__state
0x141831  ldarg.0
0x141832  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__19::proxyContext
0x141837  brtrue.s loc_141844
0x141839  ldstr    aProxycontext// "proxyContext"
0x14183e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x141843  throw
0x141844  ldarg.0
0x141845  ldarg.0
0x141846  ldfld    class Microsoft.SharePoint.ServerStub.SPInformationRightsManagementSettingsServerStub <GetProperties>d__19::<>4__this
0x14184b  ldarg.0
0x14184c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__19::proxyContext
0x141851  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPInformationRightsManagementSettingsServerStub::<>n__FabricatedMethod1d(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x141856  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x14185b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__19::<>7__wrap1b
0x141860  ldarg.0
0x141861  ldc.i4.1
0x141862  stfld    int32 <GetProperties>d__19::<>1__state
0x141867  br.s     loc_14189B
0x141869  ldarg.0
0x14186a  ldarg.0
0x14186b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__19::<>7__wrap1b
0x141870  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x141875  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<item>5__1a
0x14187a  ldarg.0
0x14187b  ldarg.0
0x14187c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<item>5__1a
0x141881  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>2__current
0x141886  ldarg.0
0x141887  ldc.i4.2
0x141888  stfld    int32 <GetProperties>d__19::<>1__state
0x14188d  ldc.i4.1
0x14188e  stloc.0
0x14188f  leave    loc_1425B5
0x141894  ldarg.0
0x141895  ldc.i4.1
0x141896  stfld    int32 <GetProperties>d__19::<>1__state
0x14189b  ldarg.0
0x14189c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__19::<>7__wrap1b
0x1418a1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1418a6  brtrue.s loc_141869
0x1418a8  ldarg.0
0x1418a9  call     instance void <GetProperties>d__19::<>m__Finally1c()
0x1418ae  ldarg.0
0x1418af  ldarg.0
0x1418b0  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1418b5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x1418ba  ldarg.0
0x1418bb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x1418c0  ldstr    aAllowprint// "AllowPrint"
0x1418c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1418ca  ldarg.0
0x1418cb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x1418d0  ldc.i4.0
0x1418d1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1418d6  ldarg.0
0x1418d7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x1418dc  ldc.i4.1
0x1418dd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1418e2  ldarg.0
0x1418e3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x1418e8  ldc.i4.0
0x1418e9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1418ee  ldarg.0
0x1418ef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x1418f4  ldtoken  [mscorlib]System.Boolean
0x1418f9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1418fe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x141903  ldarg.0
0x141904  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x141909  ldc.i4.0
0x14190a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x14190f  ldarg.0
0x141910  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x141915  ldc.i4.1
0x141916  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x14191b  ldarg.0
0x14191c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x141921  ldc.i4.0
0x141922  box      [mscorlib]System.Boolean
0x141927  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x14192c  ldarg.0
0x14192d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x141932  ldstr    aAllowprint// "AllowPrint"
0x141937  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x14193c  ldarg.0
0x14193d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x141942  ldnull
0x141943  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x141948  ldarg.0
0x141949  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x14194e  ldc.i4.0
0x14194f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x141954  ldarg.0
0x141955  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x14195a  ldc.i4.0
0x14195b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x141960  ldarg.0
0x141961  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x141966  ldc.i4.0
0x141967  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x14196c  ldarg.0
0x14196d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x141972  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>2__current
0x141977  ldarg.0
0x141978  ldc.i4.3
0x141979  stfld    int32 <GetProperties>d__19::<>1__state
0x14197e  ldc.i4.1
0x14197f  stloc.0
0x141980  leave    loc_1425B5
0x141985  ldarg.0
0x141986  ldc.i4.m1
0x141987  stfld    int32 <GetProperties>d__19::<>1__state
0x14198c  ldarg.0
0x14198d  ldarg.0
0x14198e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x141993  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x141998  ldarg.0
0x141999  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x14199e  ldstr    aAllowscript// "AllowScript"
0x1419a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1419a8  ldarg.0
0x1419a9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x1419ae  ldc.i4.0
0x1419af  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1419b4  ldarg.0
0x1419b5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x1419ba  ldc.i4.1
0x1419bb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1419c0  ldarg.0
0x1419c1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x1419c6  ldc.i4.0
0x1419c7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1419cc  ldarg.0
0x1419cd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x1419d2  ldtoken  [mscorlib]System.Boolean
0x1419d7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1419dc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1419e1  ldarg.0
0x1419e2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x1419e7  ldc.i4.0
0x1419e8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1419ed  ldarg.0
0x1419ee  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x1419f3  ldc.i4.1
0x1419f4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1419f9  ldarg.0
0x1419fa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x1419ff  ldc.i4.0
0x141a00  box      [mscorlib]System.Boolean
0x141a05  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x141a0a  ldarg.0
0x141a0b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x141a10  ldstr    aAllowscript// "AllowScript"
0x141a15  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x141a1a  ldarg.0
0x141a1b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x141a20  ldnull
0x141a21  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x141a26  ldarg.0
0x141a27  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x141a2c  ldc.i4.0
0x141a2d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x141a32  ldarg.0
0x141a33  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x141a38  ldc.i4.0
0x141a39  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x141a3e  ldarg.0
0x141a3f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x141a44  ldc.i4.0
0x141a45  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x141a4a  ldarg.0
0x141a4b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x141a50  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>2__current
0x141a55  ldarg.0
0x141a56  ldc.i4.4
0x141a57  stfld    int32 <GetProperties>d__19::<>1__state
0x141a5c  ldc.i4.1
0x141a5d  stloc.0
0x141a5e  leave    loc_1425B5
0x141a63  ldarg.0
0x141a64  ldc.i4.m1
0x141a65  stfld    int32 <GetProperties>d__19::<>1__state
0x141a6a  ldarg.0
0x141a6b  ldarg.0
0x141a6c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x141a71  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x141a76  ldarg.0
0x141a77  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x141a7c  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x141a81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x141a86  ldarg.0
0x141a87  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x141a8c  ldc.i4.0
0x141a8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x141a92  ldarg.0
0x141a93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x141a98  ldc.i4.1
0x141a99  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x141a9e  ldarg.0
0x141a9f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x141aa4  ldc.i4.0
0x141aa5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x141aaa  ldarg.0
0x141aab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x141ab0  ldtoken  [mscorlib]System.Boolean
0x141ab5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141aba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x141abf  ldarg.0
0x141ac0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x141ac5  ldc.i4.0
0x141ac6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x141acb  ldarg.0
0x141acc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x141ad1  ldc.i4.1
0x141ad2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x141ad7  ldarg.0
0x141ad8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x141add  ldc.i4.0
0x141ade  box      [mscorlib]System.Boolean
0x141ae3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x141ae8  ldarg.0
0x141ae9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x141aee  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x141af3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x141af8  ldarg.0
0x141af9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x141afe  ldnull
0x141aff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x141b04  ldarg.0
0x141b05  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x141b0a  ldc.i4.0
0x141b0b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x141b10  ldarg.0
0x141b11  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x141b16  ldc.i4.0
0x141b17  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x141b1c  ldarg.0
0x141b1d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x141b22  ldc.i4.0
0x141b23  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x141b28  ldarg.0
0x141b29  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x141b2e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>2__current
0x141b33  ldarg.0
0x141b34  ldc.i4.5
0x141b35  stfld    int32 <GetProperties>d__19::<>1__state
0x141b3a  ldc.i4.1
0x141b3b  stloc.0
0x141b3c  leave    loc_1425B5
0x141b41  ldarg.0
0x141b42  ldc.i4.m1
0x141b43  stfld    int32 <GetProperties>d__19::<>1__state
0x141b48  ldarg.0
0x141b49  ldarg.0
0x141b4a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x141b4f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x141b54  ldarg.0
0x141b55  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x141b5a  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x141b5f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x141b64  ldarg.0
0x141b65  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x141b6a  ldc.i4.0
0x141b6b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x141b70  ldarg.0
0x141b71  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x141b76  ldc.i4.1
0x141b77  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x141b7c  ldarg.0
0x141b7d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x141b82  ldc.i4.0
0x141b83  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x141b88  ldarg.0
0x141b89  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x141b8e  ldtoken  [mscorlib]System.Boolean
0x141b93  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141b98  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x141b9d  ldarg.0
0x141b9e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x141ba3  ldc.i4.0
0x141ba4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x141ba9  ldarg.0
0x141baa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x141baf  ldc.i4.1
0x141bb0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x141bb5  ldarg.0
0x141bb6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x141bbb  ldc.i4.0
0x141bbc  box      [mscorlib]System.Boolean
0x141bc1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x141bc6  ldarg.0
  ... truncated ...
```
