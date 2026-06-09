# <GetProperties>d__19::MoveNext_0

- ea: `0x140550`
- end: `0x14132f`
- name: `<GetProperties>d__19::MoveNext_0`
- size: `3551`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x655b0`
- `0x140550`
- `0x141350`
- `0x1413b0`

## string_xrefs

- `0x1407fc`: `AllowWriteCopy`
- `0x14086e`: `AllowWriteCopy`
- `0x1409b8`: `DocumentAccessExpireDays`
- `0x140a2a`: `DocumentAccessExpireDays`
- `0x140a96`: `EnableDocumentAccessExpire`
- `0x140b08`: `EnableDocumentAccessExpire`
- `0x140d32`: `EnableLicenseCacheExpire`
- `0x140da4`: `EnableLicenseCacheExpire`
- `0x140fca`: `LicenseCacheExpireDays`
- `0x14103c`: `LicenseCacheExpireDays`
- `0x14125d`: `TemplateId`
- `0x1412ca`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x140550  ldarg.0
0x140551  ldfld    int32 <GetProperties>d__19::<>1__state
0x140556  stloc.1
0x140557  ldloc.1
0x140558  switch   loc_1405AA, loc_141322, loc_140614, loc_140705, loc_1407E3, loc_1408C1, loc_14099F, loc_140A7D, loc_140B5B, loc_140C3A, loc_140D19, loc_140DF8, loc_140ED2, loc_140FB1, loc_141090, loc_14116A, loc_141244, loc_14131B
0x1405a5  br       loc_141322
0x1405aa  ldarg.0
0x1405ab  ldc.i4.m1
0x1405ac  stfld    int32 <GetProperties>d__19::<>1__state
0x1405b1  ldarg.0
0x1405b2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__19::proxyContext
0x1405b7  brtrue.s loc_1405C4
0x1405b9  ldstr    aProxycontext// "proxyContext"
0x1405be  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1405c3  throw
0x1405c4  ldarg.0
0x1405c5  ldarg.0
0x1405c6  ldfld    class Microsoft.SharePoint.ServerStub.SPInformationRightsManagementFileSettingsServerStub <GetProperties>d__19::<>4__this
0x1405cb  ldarg.0
0x1405cc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__19::proxyContext
0x1405d1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPInformationRightsManagementFileSettingsServerStub::<>n__FabricatedMethod1d(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x1405d6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x1405db  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__19::<>7__wrap1b
0x1405e0  ldarg.0
0x1405e1  ldc.i4.1
0x1405e2  stfld    int32 <GetProperties>d__19::<>1__state
0x1405e7  br.s     loc_14061B
0x1405e9  ldarg.0
0x1405ea  ldarg.0
0x1405eb  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__19::<>7__wrap1b
0x1405f0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x1405f5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<item>5__1a
0x1405fa  ldarg.0
0x1405fb  ldarg.0
0x1405fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<item>5__1a
0x140601  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>2__current
0x140606  ldarg.0
0x140607  ldc.i4.2
0x140608  stfld    int32 <GetProperties>d__19::<>1__state
0x14060d  ldc.i4.1
0x14060e  stloc.0
0x14060f  leave    loc_14132D
0x140614  ldarg.0
0x140615  ldc.i4.1
0x140616  stfld    int32 <GetProperties>d__19::<>1__state
0x14061b  ldarg.0
0x14061c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__19::<>7__wrap1b
0x140621  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x140626  brtrue.s loc_1405E9
0x140628  ldarg.0
0x140629  call     instance void <GetProperties>d__19::<>m__Finally1c()
0x14062e  ldarg.0
0x14062f  ldarg.0
0x140630  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x140635  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x14063a  ldarg.0
0x14063b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x140640  ldstr    aAllowprint// "AllowPrint"
0x140645  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x14064a  ldarg.0
0x14064b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x140650  ldc.i4.0
0x140651  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x140656  ldarg.0
0x140657  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x14065c  ldc.i4.1
0x14065d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x140662  ldarg.0
0x140663  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x140668  ldc.i4.0
0x140669  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x14066e  ldarg.0
0x14066f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x140674  ldtoken  [mscorlib]System.Boolean
0x140679  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14067e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x140683  ldarg.0
0x140684  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x140689  ldc.i4.0
0x14068a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x14068f  ldarg.0
0x140690  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x140695  ldc.i4.1
0x140696  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x14069b  ldarg.0
0x14069c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x1406a1  ldc.i4.0
0x1406a2  box      [mscorlib]System.Boolean
0x1406a7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1406ac  ldarg.0
0x1406ad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x1406b2  ldstr    aAllowprint// "AllowPrint"
0x1406b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1406bc  ldarg.0
0x1406bd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x1406c2  ldnull
0x1406c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1406c8  ldarg.0
0x1406c9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x1406ce  ldc.i4.0
0x1406cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1406d4  ldarg.0
0x1406d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x1406da  ldc.i4.1
0x1406db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1406e0  ldarg.0
0x1406e1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x1406e6  ldc.i4.0
0x1406e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1406ec  ldarg.0
0x1406ed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocala
0x1406f2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>2__current
0x1406f7  ldarg.0
0x1406f8  ldc.i4.3
0x1406f9  stfld    int32 <GetProperties>d__19::<>1__state
0x1406fe  ldc.i4.1
0x1406ff  stloc.0
0x140700  leave    loc_14132D
0x140705  ldarg.0
0x140706  ldc.i4.m1
0x140707  stfld    int32 <GetProperties>d__19::<>1__state
0x14070c  ldarg.0
0x14070d  ldarg.0
0x14070e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x140713  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x140718  ldarg.0
0x140719  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x14071e  ldstr    aAllowscript// "AllowScript"
0x140723  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x140728  ldarg.0
0x140729  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x14072e  ldc.i4.0
0x14072f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x140734  ldarg.0
0x140735  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x14073a  ldc.i4.1
0x14073b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x140740  ldarg.0
0x140741  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x140746  ldc.i4.0
0x140747  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x14074c  ldarg.0
0x14074d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x140752  ldtoken  [mscorlib]System.Boolean
0x140757  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14075c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x140761  ldarg.0
0x140762  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x140767  ldc.i4.0
0x140768  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x14076d  ldarg.0
0x14076e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x140773  ldc.i4.1
0x140774  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x140779  ldarg.0
0x14077a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x14077f  ldc.i4.0
0x140780  box      [mscorlib]System.Boolean
0x140785  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x14078a  ldarg.0
0x14078b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x140790  ldstr    aAllowscript// "AllowScript"
0x140795  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x14079a  ldarg.0
0x14079b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x1407a0  ldnull
0x1407a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1407a6  ldarg.0
0x1407a7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x1407ac  ldc.i4.0
0x1407ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1407b2  ldarg.0
0x1407b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x1407b8  ldc.i4.1
0x1407b9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1407be  ldarg.0
0x1407bf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x1407c4  ldc.i4.0
0x1407c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1407ca  ldarg.0
0x1407cb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalb
0x1407d0  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>2__current
0x1407d5  ldarg.0
0x1407d6  ldc.i4.4
0x1407d7  stfld    int32 <GetProperties>d__19::<>1__state
0x1407dc  ldc.i4.1
0x1407dd  stloc.0
0x1407de  leave    loc_14132D
0x1407e3  ldarg.0
0x1407e4  ldc.i4.m1
0x1407e5  stfld    int32 <GetProperties>d__19::<>1__state
0x1407ea  ldarg.0
0x1407eb  ldarg.0
0x1407ec  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1407f1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x1407f6  ldarg.0
0x1407f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x1407fc  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x140801  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x140806  ldarg.0
0x140807  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x14080c  ldc.i4.0
0x14080d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x140812  ldarg.0
0x140813  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x140818  ldc.i4.1
0x140819  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14081e  ldarg.0
0x14081f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x140824  ldc.i4.0
0x140825  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x14082a  ldarg.0
0x14082b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x140830  ldtoken  [mscorlib]System.Boolean
0x140835  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14083a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x14083f  ldarg.0
0x140840  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x140845  ldc.i4.0
0x140846  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x14084b  ldarg.0
0x14084c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x140851  ldc.i4.1
0x140852  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x140857  ldarg.0
0x140858  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x14085d  ldc.i4.0
0x14085e  box      [mscorlib]System.Boolean
0x140863  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x140868  ldarg.0
0x140869  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x14086e  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x140873  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x140878  ldarg.0
0x140879  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x14087e  ldnull
0x14087f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x140884  ldarg.0
0x140885  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x14088a  ldc.i4.0
0x14088b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x140890  ldarg.0
0x140891  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x140896  ldc.i4.1
0x140897  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x14089c  ldarg.0
0x14089d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x1408a2  ldc.i4.0
0x1408a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1408a8  ldarg.0
0x1408a9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocalc
0x1408ae  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>2__current
0x1408b3  ldarg.0
0x1408b4  ldc.i4.5
0x1408b5  stfld    int32 <GetProperties>d__19::<>1__state
0x1408ba  ldc.i4.1
0x1408bb  stloc.0
0x1408bc  leave    loc_14132D
0x1408c1  ldarg.0
0x1408c2  ldc.i4.m1
0x1408c3  stfld    int32 <GetProperties>d__19::<>1__state
0x1408c8  ldarg.0
0x1408c9  ldarg.0
0x1408ca  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1408cf  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x1408d4  ldarg.0
0x1408d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x1408da  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x1408df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1408e4  ldarg.0
0x1408e5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x1408ea  ldc.i4.0
0x1408eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1408f0  ldarg.0
0x1408f1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x1408f6  ldc.i4.1
0x1408f7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1408fc  ldarg.0
0x1408fd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x140902  ldc.i4.0
0x140903  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x140908  ldarg.0
0x140909  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x14090e  ldtoken  [mscorlib]System.Boolean
0x140913  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x140918  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x14091d  ldarg.0
0x14091e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x140923  ldc.i4.0
0x140924  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x140929  ldarg.0
0x14092a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x14092f  ldc.i4.1
0x140930  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x140935  ldarg.0
0x140936  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__19::<>g__initLocald
0x14093b  ldc.i4.0
0x14093c  box      [mscorlib]System.Boolean
0x140941  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x140946  ldarg.0
  ... truncated ...
```
