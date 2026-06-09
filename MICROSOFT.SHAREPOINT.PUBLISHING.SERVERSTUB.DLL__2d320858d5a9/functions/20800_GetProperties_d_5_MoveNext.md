# <GetProperties>d__5::MoveNext

- ea: `0x20800`
- end: `0x20cfd`
- name: `<GetProperties>d__5::MoveNext`
- size: `1277`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0xac00`
- `0x20800`
- `0x20d20`
- `0x20d80`

## string_xrefs

- `0x20a7a`: `NewPageLayoutEditablePath`
- `0x20ae7`: `NewPageLayoutEditablePath`
- `0x20b53`: `NewPageLayoutNameWithoutExtension`
- `0x20bc0`: `NewPageLayoutNameWithoutExtension`

## pseudocode

```c

```

## disassembly

```asm
0x20800  ldarg.0
0x20801  ldfld    int32 <GetProperties>d__5::<>1__state
0x20806  stloc.1
0x20807  ldloc.1
0x20808  switch   loc_20832, loc_20CF0, loc_2089C, loc_20988, loc_20A61, loc_20B3A, loc_20C13, loc_20CE9
0x2082d  br       loc_20CF0
0x20832  ldarg.0
0x20833  ldc.i4.m1
0x20834  stfld    int32 <GetProperties>d__5::<>1__state
0x20839  ldarg.0
0x2083a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__5::proxyContext
0x2083f  brtrue.s loc_2084C
0x20841  ldstr    aProxycontext// "proxyContext"
0x20846  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2084b  throw
0x2084c  ldarg.0
0x2084d  ldarg.0
0x2084e  ldfld    class Microsoft.SharePoint.Publishing.PageLayoutCreationInformationValueTypeConverter <GetProperties>d__5::<>4__this
0x20853  ldarg.0
0x20854  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__5::proxyContext
0x20859  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.PageLayoutCreationInformationValueTypeConverter::<>n__FabricatedMethod9(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x2085e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x20863  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__5::<>7__wrap7
0x20868  ldarg.0
0x20869  ldc.i4.1
0x2086a  stfld    int32 <GetProperties>d__5::<>1__state
0x2086f  br.s     loc_208A3
0x20871  ldarg.0
0x20872  ldarg.0
0x20873  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__5::<>7__wrap7
0x20878  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x2087d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<item>5__6
0x20882  ldarg.0
0x20883  ldarg.0
0x20884  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<item>5__6
0x20889  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>2__current
0x2088e  ldarg.0
0x2088f  ldc.i4.2
0x20890  stfld    int32 <GetProperties>d__5::<>1__state
0x20895  ldc.i4.1
0x20896  stloc.0
0x20897  leave    loc_20CFB
0x2089c  ldarg.0
0x2089d  ldc.i4.1
0x2089e  stfld    int32 <GetProperties>d__5::<>1__state
0x208a3  ldarg.0
0x208a4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__5::<>7__wrap7
0x208a9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x208ae  brtrue.s loc_20871
0x208b0  ldarg.0
0x208b1  call     instance void <GetProperties>d__5::<>m__Finally8()
0x208b6  ldarg.0
0x208b7  ldarg.0
0x208b8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x208bd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x208c2  ldarg.0
0x208c3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x208c8  ldstr    aAssociatedcont// "AssociatedContentTypeId"
0x208cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x208d2  ldarg.0
0x208d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x208d8  ldc.i4.0
0x208d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x208de  ldarg.0
0x208df  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x208e4  ldc.i4.1
0x208e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x208ea  ldarg.0
0x208eb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x208f0  ldc.i4.0
0x208f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x208f6  ldarg.0
0x208f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x208fc  ldtoken  [mscorlib]System.String
0x20901  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20906  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2090b  ldarg.0
0x2090c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x20911  ldc.i4.0
0x20912  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x20917  ldarg.0
0x20918  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x2091d  ldc.i4.1
0x2091e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x20923  ldarg.0
0x20924  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x20929  ldnull
0x2092a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2092f  ldarg.0
0x20930  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x20935  ldstr    aAssociatedcont// "AssociatedContentTypeId"
0x2093a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2093f  ldarg.0
0x20940  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x20945  ldnull
0x20946  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2094b  ldarg.0
0x2094c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x20951  ldc.i4.0
0x20952  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x20957  ldarg.0
0x20958  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x2095d  ldc.i4.0
0x2095e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x20963  ldarg.0
0x20964  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x20969  ldc.i4.0
0x2096a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x2096f  ldarg.0
0x20970  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x20975  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>2__current
0x2097a  ldarg.0
0x2097b  ldc.i4.3
0x2097c  stfld    int32 <GetProperties>d__5::<>1__state
0x20981  ldc.i4.1
0x20982  stloc.0
0x20983  leave    loc_20CFB
0x20988  ldarg.0
0x20989  ldc.i4.m1
0x2098a  stfld    int32 <GetProperties>d__5::<>1__state
0x2098f  ldarg.0
0x20990  ldarg.0
0x20991  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x20996  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x2099b  ldarg.0
0x2099c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x209a1  ldstr    aMasterpageurl// "MasterPageUrl"
0x209a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x209ab  ldarg.0
0x209ac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x209b1  ldc.i4.0
0x209b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x209b7  ldarg.0
0x209b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x209bd  ldc.i4.1
0x209be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x209c3  ldarg.0
0x209c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x209c9  ldc.i4.0
0x209ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x209cf  ldarg.0
0x209d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x209d5  ldtoken  [mscorlib]System.String
0x209da  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x209df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x209e4  ldarg.0
0x209e5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x209ea  ldc.i4.0
0x209eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x209f0  ldarg.0
0x209f1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x209f6  ldc.i4.1
0x209f7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x209fc  ldarg.0
0x209fd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x20a02  ldnull
0x20a03  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x20a08  ldarg.0
0x20a09  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x20a0e  ldstr    aMasterpageurl// "MasterPageUrl"
0x20a13  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x20a18  ldarg.0
0x20a19  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x20a1e  ldnull
0x20a1f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x20a24  ldarg.0
0x20a25  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x20a2a  ldc.i4.0
0x20a2b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x20a30  ldarg.0
0x20a31  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x20a36  ldc.i4.0
0x20a37  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x20a3c  ldarg.0
0x20a3d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x20a42  ldc.i4.0
0x20a43  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x20a48  ldarg.0
0x20a49  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x20a4e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>2__current
0x20a53  ldarg.0
0x20a54  ldc.i4.4
0x20a55  stfld    int32 <GetProperties>d__5::<>1__state
0x20a5a  ldc.i4.1
0x20a5b  stloc.0
0x20a5c  leave    loc_20CFB
0x20a61  ldarg.0
0x20a62  ldc.i4.m1
0x20a63  stfld    int32 <GetProperties>d__5::<>1__state
0x20a68  ldarg.0
0x20a69  ldarg.0
0x20a6a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x20a6f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x20a74  ldarg.0
0x20a75  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x20a7a  ldstr    aNewpagelayoute// "NewPageLayoutEditablePath"
0x20a7f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x20a84  ldarg.0
0x20a85  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x20a8a  ldc.i4.0
0x20a8b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x20a90  ldarg.0
0x20a91  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x20a96  ldc.i4.1
0x20a97  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x20a9c  ldarg.0
0x20a9d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x20aa2  ldc.i4.0
0x20aa3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x20aa8  ldarg.0
0x20aa9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x20aae  ldtoken  [mscorlib]System.String
0x20ab3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20ab8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x20abd  ldarg.0
0x20abe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x20ac3  ldc.i4.0
0x20ac4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x20ac9  ldarg.0
0x20aca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x20acf  ldc.i4.1
0x20ad0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x20ad5  ldarg.0
0x20ad6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x20adb  ldnull
0x20adc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x20ae1  ldarg.0
0x20ae2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x20ae7  ldstr    aNewpagelayoute// "NewPageLayoutEditablePath"
0x20aec  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x20af1  ldarg.0
0x20af2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x20af7  ldnull
0x20af8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x20afd  ldarg.0
0x20afe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x20b03  ldc.i4.0
0x20b04  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x20b09  ldarg.0
0x20b0a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x20b0f  ldc.i4.0
0x20b10  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x20b15  ldarg.0
0x20b16  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x20b1b  ldc.i4.0
0x20b1c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x20b21  ldarg.0
0x20b22  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x20b27  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>2__current
0x20b2c  ldarg.0
0x20b2d  ldc.i4.5
0x20b2e  stfld    int32 <GetProperties>d__5::<>1__state
0x20b33  ldc.i4.1
0x20b34  stloc.0
0x20b35  leave    loc_20CFB
0x20b3a  ldarg.0
0x20b3b  ldc.i4.m1
0x20b3c  stfld    int32 <GetProperties>d__5::<>1__state
0x20b41  ldarg.0
0x20b42  ldarg.0
0x20b43  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x20b48  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x20b4d  ldarg.0
0x20b4e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x20b53  ldstr    aNewpagelayoutn// "NewPageLayoutNameWithoutExtension"
0x20b58  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x20b5d  ldarg.0
0x20b5e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x20b63  ldc.i4.0
0x20b64  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x20b69  ldarg.0
0x20b6a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x20b6f  ldc.i4.1
0x20b70  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x20b75  ldarg.0
0x20b76  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x20b7b  ldc.i4.0
0x20b7c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x20b81  ldarg.0
0x20b82  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x20b87  ldtoken  [mscorlib]System.String
0x20b8c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20b91  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x20b96  ldarg.0
0x20b97  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x20b9c  ldc.i4.0
0x20b9d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x20ba2  ldarg.0
0x20ba3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x20ba8  ldc.i4.1
0x20ba9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x20bae  ldarg.0
0x20baf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x20bb4  ldnull
0x20bb5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x20bba  ldarg.0
0x20bbb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x20bc0  ldstr    aNewpagelayoutn// "NewPageLayoutNameWithoutExtension"
0x20bc5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x20bca  ldarg.0
  ... truncated ...
```
