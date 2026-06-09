# <GetProperties>d__7f::MoveNext

- ea: `0x133120`
- end: `0x13533f`
- name: `<GetProperties>d__7f::MoveNext`
- size: `8735`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x5b400`
- `0x133120`
- `0x135360`
- `0x1353c0`

## string_xrefs

- `0x1348c5`: `ServerRelativePath`
- `0x134932`: `ServerRelativePath`
- `0x1334f7`: `CheckInComment`
- `0x133564`: `CheckInComment`
- `0x134032`: `LinkingUri`
- `0x13409f`: `LinkingUri`
- `0x13410c`: `LinkingUrl`
- `0x134179`: `LinkingUrl`
- `0x134b60`: `TimeCreated`
- `0x134bdb`: `TimeCreated`

## pseudocode

```c

```

## disassembly

```asm
0x133120  ldarg.0
0x133121  ldfld    int32 <GetProperties>d__7f::<>1__state
0x133126  stloc.1
0x133127  ldloc.1
0x133128  switch   loc_1331D6, loc_135332, loc_133240, loc_13332C, loc_133405, loc_1334DE, loc_1335B7, loc_133695, loc_13376E, loc_133848, loc_133927, loc_133A0E, loc_133AE8, loc_133BC2, loc_133CA1, loc_133D7B, loc_133E5A, loc_133F3A, loc_134019, loc_1340F3, loc_1341CD, loc_1342A7, loc_134381, loc_134460, loc_13453F, loc_134619, loc_1346F3, loc_1347D2, loc_1348AC, loc_134986, loc_134A60, loc_134B47, loc_134C2F, loc_134D17, loc_134DF1, loc_134ED0, loc_134FAA, loc_135092, loc_13516C, loc_135246, loc_13532B
0x1331d1  br       loc_135332
0x1331d6  ldarg.0
0x1331d7  ldc.i4.m1
0x1331d8  stfld    int32 <GetProperties>d__7f::<>1__state
0x1331dd  ldarg.0
0x1331de  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__7f::proxyContext
0x1331e3  brtrue.s loc_1331F0
0x1331e5  ldstr    aProxycontext// "proxyContext"
0x1331ea  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1331ef  throw
0x1331f0  ldarg.0
0x1331f1  ldarg.0
0x1331f2  ldfld    class Microsoft.SharePoint.ServerStub.SPFileServerStub <GetProperties>d__7f::<>4__this
0x1331f7  ldarg.0
0x1331f8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__7f::proxyContext
0x1331fd  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPFileServerStub::<>n__FabricatedMethod83(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x133202  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x133207  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__7f::<>7__wrap81
0x13320c  ldarg.0
0x13320d  ldc.i4.1
0x13320e  stfld    int32 <GetProperties>d__7f::<>1__state
0x133213  br.s     loc_133247
0x133215  ldarg.0
0x133216  ldarg.0
0x133217  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__7f::<>7__wrap81
0x13321c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x133221  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<item>5__80
0x133226  ldarg.0
0x133227  ldarg.0
0x133228  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<item>5__80
0x13322d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>2__current
0x133232  ldarg.0
0x133233  ldc.i4.2
0x133234  stfld    int32 <GetProperties>d__7f::<>1__state
0x133239  ldc.i4.1
0x13323a  stloc.0
0x13323b  leave    loc_13533D
0x133240  ldarg.0
0x133241  ldc.i4.1
0x133242  stfld    int32 <GetProperties>d__7f::<>1__state
0x133247  ldarg.0
0x133248  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__7f::<>7__wrap81
0x13324d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x133252  brtrue.s loc_133215
0x133254  ldarg.0
0x133255  call     instance void <GetProperties>d__7f::<>m__Finally82()
0x13325a  ldarg.0
0x13325b  ldarg.0
0x13325c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x133261  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal59
0x133266  ldarg.0
0x133267  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal59
0x13326c  ldstr    aActivitycapabi// "ActivityCapabilities"
0x133271  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x133276  ldarg.0
0x133277  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal59
0x13327c  ldc.i4.0
0x13327d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x133282  ldarg.0
0x133283  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal59
0x133288  ldc.i4.2
0x133289  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13328e  ldarg.0
0x13328f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal59
0x133294  ldc.i4.1
0x133295  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x13329a  ldarg.0
0x13329b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal59
0x1332a0  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityCapabilities
0x1332a5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1332aa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1332af  ldarg.0
0x1332b0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal59
0x1332b5  ldc.i4.1
0x1332b6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1332bb  ldarg.0
0x1332bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal59
0x1332c1  ldc.i4.1
0x1332c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1332c7  ldarg.0
0x1332c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal59
0x1332cd  ldnull
0x1332ce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1332d3  ldarg.0
0x1332d4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal59
0x1332d9  ldstr    aActivitycapabi// "ActivityCapabilities"
0x1332de  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1332e3  ldarg.0
0x1332e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal59
0x1332e9  ldnull
0x1332ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1332ef  ldarg.0
0x1332f0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal59
0x1332f5  ldc.i4.0
0x1332f6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1332fb  ldarg.0
0x1332fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal59
0x133301  ldc.i4.1
0x133302  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x133307  ldarg.0
0x133308  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal59
0x13330d  ldc.i4.0
0x13330e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x133313  ldarg.0
0x133314  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal59
0x133319  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>2__current
0x13331e  ldarg.0
0x13331f  ldc.i4.3
0x133320  stfld    int32 <GetProperties>d__7f::<>1__state
0x133325  ldc.i4.1
0x133326  stloc.0
0x133327  leave    loc_13533D
0x13332c  ldarg.0
0x13332d  ldc.i4.m1
0x13332e  stfld    int32 <GetProperties>d__7f::<>1__state
0x133333  ldarg.0
0x133334  ldarg.0
0x133335  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x13333a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5a
0x13333f  ldarg.0
0x133340  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5a
0x133345  ldstr    aAuthor_0// "Author"
0x13334a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x13334f  ldarg.0
0x133350  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5a
0x133355  ldc.i4.0
0x133356  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x13335b  ldarg.0
0x13335c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5a
0x133361  ldc.i4.4
0x133362  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x133367  ldarg.0
0x133368  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5a
0x13336d  ldc.i4.0
0x13336e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x133373  ldarg.0
0x133374  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5a
0x133379  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPUser
0x13337e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x133383  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x133388  ldarg.0
0x133389  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5a
0x13338e  ldc.i4.1
0x13338f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x133394  ldarg.0
0x133395  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5a
0x13339a  ldc.i4.1
0x13339b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1333a0  ldarg.0
0x1333a1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5a
0x1333a6  ldnull
0x1333a7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1333ac  ldarg.0
0x1333ad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5a
0x1333b2  ldstr    aAuthor_0// "Author"
0x1333b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1333bc  ldarg.0
0x1333bd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5a
0x1333c2  ldnull
0x1333c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1333c8  ldarg.0
0x1333c9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5a
0x1333ce  ldc.i4.0
0x1333cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1333d4  ldarg.0
0x1333d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5a
0x1333da  ldc.i4.0
0x1333db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1333e0  ldarg.0
0x1333e1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5a
0x1333e6  ldc.i4.0
0x1333e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1333ec  ldarg.0
0x1333ed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5a
0x1333f2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>2__current
0x1333f7  ldarg.0
0x1333f8  ldc.i4.4
0x1333f9  stfld    int32 <GetProperties>d__7f::<>1__state
0x1333fe  ldc.i4.1
0x1333ff  stloc.0
0x133400  leave    loc_13533D
0x133405  ldarg.0
0x133406  ldc.i4.m1
0x133407  stfld    int32 <GetProperties>d__7f::<>1__state
0x13340c  ldarg.0
0x13340d  ldarg.0
0x13340e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x133413  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5b
0x133418  ldarg.0
0x133419  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5b
0x13341e  ldstr    aCheckedoutbyus// "CheckedOutByUser"
0x133423  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x133428  ldarg.0
0x133429  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5b
0x13342e  ldc.i4.0
0x13342f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x133434  ldarg.0
0x133435  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5b
0x13343a  ldc.i4.4
0x13343b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x133440  ldarg.0
0x133441  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5b
0x133446  ldc.i4.0
0x133447  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x13344c  ldarg.0
0x13344d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5b
0x133452  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPUser
0x133457  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13345c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x133461  ldarg.0
0x133462  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5b
0x133467  ldc.i4.1
0x133468  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x13346d  ldarg.0
0x13346e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5b
0x133473  ldc.i4.1
0x133474  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x133479  ldarg.0
0x13347a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5b
0x13347f  ldnull
0x133480  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x133485  ldarg.0
0x133486  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5b
0x13348b  ldstr    aCheckedoutbyus// "CheckedOutByUser"
0x133490  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x133495  ldarg.0
0x133496  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5b
0x13349b  ldnull
0x13349c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1334a1  ldarg.0
0x1334a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5b
0x1334a7  ldc.i4.0
0x1334a8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1334ad  ldarg.0
0x1334ae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5b
0x1334b3  ldc.i4.0
0x1334b4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1334b9  ldarg.0
0x1334ba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5b
0x1334bf  ldc.i4.0
0x1334c0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1334c5  ldarg.0
0x1334c6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5b
0x1334cb  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>2__current
0x1334d0  ldarg.0
0x1334d1  ldc.i4.5
0x1334d2  stfld    int32 <GetProperties>d__7f::<>1__state
0x1334d7  ldc.i4.1
0x1334d8  stloc.0
0x1334d9  leave    loc_13533D
0x1334de  ldarg.0
0x1334df  ldc.i4.m1
0x1334e0  stfld    int32 <GetProperties>d__7f::<>1__state
0x1334e5  ldarg.0
0x1334e6  ldarg.0
0x1334e7  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1334ec  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5c
0x1334f1  ldarg.0
0x1334f2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5c
0x1334f7  ldstr    aCheckincomment_0// "CheckInComment"
0x1334fc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x133501  ldarg.0
0x133502  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5c
0x133507  ldc.i4.0
0x133508  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x13350d  ldarg.0
0x13350e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5c
0x133513  ldc.i4.1
0x133514  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x133519  ldarg.0
0x13351a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5c
0x13351f  ldc.i4.0
0x133520  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x133525  ldarg.0
0x133526  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5c
0x13352b  ldtoken  [mscorlib]System.String
0x133530  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x133535  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x13353a  ldarg.0
0x13353b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5c
0x133540  ldc.i4.1
0x133541  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x133546  ldarg.0
0x133547  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5c
0x13354c  ldc.i4.1
0x13354d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x133552  ldarg.0
0x133553  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5c
0x133558  ldnull
0x133559  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x13355e  ldarg.0
0x13355f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__7f::<>g__initLocal5c
0x133564  ldstr    aCheckincomment_0// "CheckInComment"
0x133569  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x13356e  ldarg.0
  ... truncated ...
```
