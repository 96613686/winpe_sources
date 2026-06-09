# <GetProperties>d__11::MoveNext

- ea: `0x202c0`
- end: `0x206ea`
- name: `<GetProperties>d__11::MoveNext`
- size: `1066`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xa7c0`
- `0x202c0`
- `0x20710`
- `0x20770`

## string_xrefs

- `0x20462`: `CreateFriendlyUrlsForNewPages`
- `0x204d4`: `CreateFriendlyUrlsForNewPages`

## pseudocode

```c

```

## disassembly

```asm
0x202c0  ldarg.0
0x202c1  ldfld    int32 <GetProperties>d__11::<>1__state
0x202c6  stloc.1
0x202c7  ldloc.1
0x202c8  switch   loc_202EE, loc_206DD, loc_20358, loc_20449, loc_20527, loc_20600, loc_206D6
0x202e9  br       loc_206DD
0x202ee  ldarg.0
0x202ef  ldc.i4.m1
0x202f0  stfld    int32 <GetProperties>d__11::<>1__state
0x202f5  ldarg.0
0x202f6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__11::proxyContext
0x202fb  brtrue.s loc_20308
0x202fd  ldstr    aProxycontext// "proxyContext"
0x20302  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x20307  throw
0x20308  ldarg.0
0x20309  ldarg.0
0x2030a  ldfld    class Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub <GetProperties>d__11::<>4__this
0x2030f  ldarg.0
0x20310  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__11::proxyContext
0x20315  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::<>n__FabricatedMethod15(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x2031a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x2031f  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__11::<>7__wrap13
0x20324  ldarg.0
0x20325  ldc.i4.1
0x20326  stfld    int32 <GetProperties>d__11::<>1__state
0x2032b  br.s     loc_2035F
0x2032d  ldarg.0
0x2032e  ldarg.0
0x2032f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__11::<>7__wrap13
0x20334  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x20339  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<item>5__12
0x2033e  ldarg.0
0x2033f  ldarg.0
0x20340  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<item>5__12
0x20345  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>2__current
0x2034a  ldarg.0
0x2034b  ldc.i4.2
0x2034c  stfld    int32 <GetProperties>d__11::<>1__state
0x20351  ldc.i4.1
0x20352  stloc.0
0x20353  leave    loc_206E8
0x20358  ldarg.0
0x20359  ldc.i4.1
0x2035a  stfld    int32 <GetProperties>d__11::<>1__state
0x2035f  ldarg.0
0x20360  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__11::<>7__wrap13
0x20365  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2036a  brtrue.s loc_2032D
0x2036c  ldarg.0
0x2036d  call     instance void <GetProperties>d__11::<>m__Finally14()
0x20372  ldarg.0
0x20373  ldarg.0
0x20374  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x20379  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocald
0x2037e  ldarg.0
0x2037f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocald
0x20384  ldstr    aAddnewpageston// "AddNewPagesToNavigation"
0x20389  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2038e  ldarg.0
0x2038f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocald
0x20394  ldc.i4.0
0x20395  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2039a  ldarg.0
0x2039b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocald
0x203a0  ldc.i4.1
0x203a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x203a6  ldarg.0
0x203a7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocald
0x203ac  ldc.i4.0
0x203ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x203b2  ldarg.0
0x203b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocald
0x203b8  ldtoken  [mscorlib]System.Boolean
0x203bd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x203c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x203c7  ldarg.0
0x203c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocald
0x203cd  ldc.i4.0
0x203ce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x203d3  ldarg.0
0x203d4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocald
0x203d9  ldc.i4.1
0x203da  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x203df  ldarg.0
0x203e0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocald
0x203e5  ldc.i4.0
0x203e6  box      [mscorlib]System.Boolean
0x203eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x203f0  ldarg.0
0x203f1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocald
0x203f6  ldstr    aAddnewpageston// "AddNewPagesToNavigation"
0x203fb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x20400  ldarg.0
0x20401  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocald
0x20406  ldnull
0x20407  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2040c  ldarg.0
0x2040d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocald
0x20412  ldc.i4.0
0x20413  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x20418  ldarg.0
0x20419  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocald
0x2041e  ldc.i4.0
0x2041f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x20424  ldarg.0
0x20425  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocald
0x2042a  ldc.i4.0
0x2042b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x20430  ldarg.0
0x20431  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocald
0x20436  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>2__current
0x2043b  ldarg.0
0x2043c  ldc.i4.3
0x2043d  stfld    int32 <GetProperties>d__11::<>1__state
0x20442  ldc.i4.1
0x20443  stloc.0
0x20444  leave    loc_206E8
0x20449  ldarg.0
0x2044a  ldc.i4.m1
0x2044b  stfld    int32 <GetProperties>d__11::<>1__state
0x20450  ldarg.0
0x20451  ldarg.0
0x20452  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x20457  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocale
0x2045c  ldarg.0
0x2045d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocale
0x20462  ldstr    aCreatefriendly// "CreateFriendlyUrlsForNewPages"
0x20467  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2046c  ldarg.0
0x2046d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocale
0x20472  ldc.i4.0
0x20473  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x20478  ldarg.0
0x20479  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocale
0x2047e  ldc.i4.1
0x2047f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x20484  ldarg.0
0x20485  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocale
0x2048a  ldc.i4.0
0x2048b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x20490  ldarg.0
0x20491  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocale
0x20496  ldtoken  [mscorlib]System.Boolean
0x2049b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x204a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x204a5  ldarg.0
0x204a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocale
0x204ab  ldc.i4.0
0x204ac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x204b1  ldarg.0
0x204b2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocale
0x204b7  ldc.i4.1
0x204b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x204bd  ldarg.0
0x204be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocale
0x204c3  ldc.i4.0
0x204c4  box      [mscorlib]System.Boolean
0x204c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x204ce  ldarg.0
0x204cf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocale
0x204d4  ldstr    aCreatefriendly// "CreateFriendlyUrlsForNewPages"
0x204d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x204de  ldarg.0
0x204df  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocale
0x204e4  ldnull
0x204e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x204ea  ldarg.0
0x204eb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocale
0x204f0  ldc.i4.0
0x204f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x204f6  ldarg.0
0x204f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocale
0x204fc  ldc.i4.0
0x204fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x20502  ldarg.0
0x20503  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocale
0x20508  ldc.i4.0
0x20509  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x2050e  ldarg.0
0x2050f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocale
0x20514  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>2__current
0x20519  ldarg.0
0x2051a  ldc.i4.4
0x2051b  stfld    int32 <GetProperties>d__11::<>1__state
0x20520  ldc.i4.1
0x20521  stloc.0
0x20522  leave    loc_206E8
0x20527  ldarg.0
0x20528  ldc.i4.m1
0x20529  stfld    int32 <GetProperties>d__11::<>1__state
0x2052e  ldarg.0
0x2052f  ldarg.0
0x20530  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x20535  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocalf
0x2053a  ldarg.0
0x2053b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocalf
0x20540  ldstr    aCurrentnavigat// "CurrentNavigation"
0x20545  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2054a  ldarg.0
0x2054b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocalf
0x20550  ldc.i4.0
0x20551  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x20556  ldarg.0
0x20557  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocalf
0x2055c  ldc.i4.4
0x2055d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x20562  ldarg.0
0x20563  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocalf
0x20568  ldc.i4.0
0x20569  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2056e  ldarg.0
0x2056f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocalf
0x20574  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettings
0x20579  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2057e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x20583  ldarg.0
0x20584  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocalf
0x20589  ldc.i4.1
0x2058a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2058f  ldarg.0
0x20590  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocalf
0x20595  ldc.i4.1
0x20596  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2059b  ldarg.0
0x2059c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocalf
0x205a1  ldnull
0x205a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x205a7  ldarg.0
0x205a8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocalf
0x205ad  ldstr    aCurrentnavigat// "CurrentNavigation"
0x205b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x205b7  ldarg.0
0x205b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocalf
0x205bd  ldnull
0x205be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x205c3  ldarg.0
0x205c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocalf
0x205c9  ldc.i4.0
0x205ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x205cf  ldarg.0
0x205d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocalf
0x205d5  ldc.i4.0
0x205d6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x205db  ldarg.0
0x205dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocalf
0x205e1  ldc.i4.0
0x205e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x205e7  ldarg.0
0x205e8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocalf
0x205ed  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>2__current
0x205f2  ldarg.0
0x205f3  ldc.i4.5
0x205f4  stfld    int32 <GetProperties>d__11::<>1__state
0x205f9  ldc.i4.1
0x205fa  stloc.0
0x205fb  leave    loc_206E8
0x20600  ldarg.0
0x20601  ldc.i4.m1
0x20602  stfld    int32 <GetProperties>d__11::<>1__state
0x20607  ldarg.0
0x20608  ldarg.0
0x20609  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2060e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal10
0x20613  ldarg.0
0x20614  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal10
0x20619  ldstr    aGlobalnavigati// "GlobalNavigation"
0x2061e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x20623  ldarg.0
0x20624  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal10
0x20629  ldc.i4.0
0x2062a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2062f  ldarg.0
0x20630  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal10
0x20635  ldc.i4.4
0x20636  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2063b  ldarg.0
0x2063c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal10
0x20641  ldc.i4.0
0x20642  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x20647  ldarg.0
0x20648  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal10
0x2064d  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettings
0x20652  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20657  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2065c  ldarg.0
0x2065d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal10
0x20662  ldc.i4.1
0x20663  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x20668  ldarg.0
0x20669  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal10
0x2066e  ldc.i4.1
0x2066f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x20674  ldarg.0
0x20675  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal10
0x2067a  ldnull
0x2067b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x20680  ldarg.0
0x20681  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__11::<>g__initLocal10
0x20686  ldstr    aGlobalnavigati// "GlobalNavigation"
  ... truncated ...
```
