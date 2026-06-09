# <GetProperties>d__29::MoveNext

- ea: `0x117390`
- end: `0x118d78`
- name: `<GetProperties>d__29::MoveNext`
- size: `6632`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x44960`
- `0x117390`
- `0x118da0`
- `0x118e00`

## string_xrefs

- `0x1178f5`: `DocumentTemplateUrl`
- `0x117962`: `DocumentTemplateUrl`
- `0x11885f`: `SchemaXml`
- `0x1188cc`: `SchemaXml`
- `0x11781c`: `DocumentTemplate`
- `0x117889`: `DocumentTemplate`
- `0x11766a`: `DisplayFormTemplateName`
- `0x1176d7`: `DisplayFormTemplateName`
- `0x1179ce`: `EditFormTemplateName`
- `0x117a3b`: `EditFormTemplateName`
- `0x117b82`: `FieldLinks`
- `0x117bef`: `FieldLinks`
- `0x117fd6`: `JSLink`
- `0x118043`: `JSLink`
- `0x1184f2`: `NewFormTemplateName`
- `0x11855f`: `NewFormTemplateName`
- `0x118780`: `ReadOnly`
- `0x1187f2`: `ReadOnly`
- `0x118939`: `SchemaXmlWithResourceTokens`
- `0x1189a6`: `SchemaXmlWithResourceTokens`

## pseudocode

```c

```

## disassembly

```asm
0x117390  ldarg.0
0x117391  ldfld    int32 <GetProperties>d__29::<>1__state
0x117396  stloc.1
0x117397  ldloc.1
0x117398  switch   loc_117422, loc_118D6B, loc_11748C, loc_117578, loc_117651, loc_11772A, loc_117803, loc_1178DC, loc_1179B5, loc_117A8F, loc_117B69, loc_117C43, loc_117D1D, loc_117DF7, loc_117ED6, loc_117FBD, loc_118097, loc_118171, loc_11824B, loc_118325, loc_1183FF, loc_1184D9, loc_1185B3, loc_11868D, loc_118767, loc_118846, loc_118920, loc_1189FA, loc_118AD4, loc_118BB3, loc_118C8D, loc_118D64
0x11741d  br       loc_118D6B
0x117422  ldarg.0
0x117423  ldc.i4.m1
0x117424  stfld    int32 <GetProperties>d__29::<>1__state
0x117429  ldarg.0
0x11742a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__29::proxyContext
0x11742f  brtrue.s loc_11743C
0x117431  ldstr    aProxycontext// "proxyContext"
0x117436  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11743b  throw
0x11743c  ldarg.0
0x11743d  ldarg.0
0x11743e  ldfld    class Microsoft.SharePoint.ServerStub.SPContentTypeServerStub <GetProperties>d__29::<>4__this
0x117443  ldarg.0
0x117444  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__29::proxyContext
0x117449  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::<>n__FabricatedMethod2d(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x11744e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x117453  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__29::<>7__wrap2b
0x117458  ldarg.0
0x117459  ldc.i4.1
0x11745a  stfld    int32 <GetProperties>d__29::<>1__state
0x11745f  br.s     loc_117493
0x117461  ldarg.0
0x117462  ldarg.0
0x117463  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__29::<>7__wrap2b
0x117468  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x11746d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<item>5__2a
0x117472  ldarg.0
0x117473  ldarg.0
0x117474  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<item>5__2a
0x117479  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>2__current
0x11747e  ldarg.0
0x11747f  ldc.i4.2
0x117480  stfld    int32 <GetProperties>d__29::<>1__state
0x117485  ldc.i4.1
0x117486  stloc.0
0x117487  leave    loc_118D76
0x11748c  ldarg.0
0x11748d  ldc.i4.1
0x11748e  stfld    int32 <GetProperties>d__29::<>1__state
0x117493  ldarg.0
0x117494  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__29::<>7__wrap2b
0x117499  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11749e  brtrue.s loc_117461
0x1174a0  ldarg.0
0x1174a1  call     instance void <GetProperties>d__29::<>m__Finally2c()
0x1174a6  ldarg.0
0x1174a7  ldarg.0
0x1174a8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1174ad  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalc
0x1174b2  ldarg.0
0x1174b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalc
0x1174b8  ldstr    aDescription// "Description"
0x1174bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1174c2  ldarg.0
0x1174c3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalc
0x1174c8  ldc.i4.0
0x1174c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1174ce  ldarg.0
0x1174cf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalc
0x1174d4  ldc.i4.1
0x1174d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1174da  ldarg.0
0x1174db  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalc
0x1174e0  ldc.i4.0
0x1174e1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1174e6  ldarg.0
0x1174e7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalc
0x1174ec  ldtoken  [mscorlib]System.String
0x1174f1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1174f6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1174fb  ldarg.0
0x1174fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalc
0x117501  ldc.i4.0
0x117502  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x117507  ldarg.0
0x117508  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalc
0x11750d  ldc.i4.1
0x11750e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x117513  ldarg.0
0x117514  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalc
0x117519  ldnull
0x11751a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x11751f  ldarg.0
0x117520  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalc
0x117525  ldstr    aDescription// "Description"
0x11752a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x11752f  ldarg.0
0x117530  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalc
0x117535  ldnull
0x117536  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x11753b  ldarg.0
0x11753c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalc
0x117541  ldc.i4.0
0x117542  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x117547  ldarg.0
0x117548  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalc
0x11754d  ldc.i4.0
0x11754e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x117553  ldarg.0
0x117554  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalc
0x117559  ldc.i4.0
0x11755a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x11755f  ldarg.0
0x117560  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalc
0x117565  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>2__current
0x11756a  ldarg.0
0x11756b  ldc.i4.3
0x11756c  stfld    int32 <GetProperties>d__29::<>1__state
0x117571  ldc.i4.1
0x117572  stloc.0
0x117573  leave    loc_118D76
0x117578  ldarg.0
0x117579  ldc.i4.m1
0x11757a  stfld    int32 <GetProperties>d__29::<>1__state
0x11757f  ldarg.0
0x117580  ldarg.0
0x117581  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x117586  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocald
0x11758b  ldarg.0
0x11758c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocald
0x117591  ldstr    aDescriptionres// "DescriptionResource"
0x117596  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x11759b  ldarg.0
0x11759c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocald
0x1175a1  ldc.i4.0
0x1175a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1175a7  ldarg.0
0x1175a8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocald
0x1175ad  ldc.i4.4
0x1175ae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1175b3  ldarg.0
0x1175b4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocald
0x1175b9  ldc.i4.0
0x1175ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1175bf  ldarg.0
0x1175c0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocald
0x1175c5  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPUserResource
0x1175ca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1175cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1175d4  ldarg.0
0x1175d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocald
0x1175da  ldc.i4.1
0x1175db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1175e0  ldarg.0
0x1175e1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocald
0x1175e6  ldc.i4.1
0x1175e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1175ec  ldarg.0
0x1175ed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocald
0x1175f2  ldnull
0x1175f3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1175f8  ldarg.0
0x1175f9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocald
0x1175fe  ldstr    aDescriptionres// "DescriptionResource"
0x117603  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x117608  ldarg.0
0x117609  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocald
0x11760e  ldnull
0x11760f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x117614  ldarg.0
0x117615  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocald
0x11761a  ldc.i4.0
0x11761b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x117620  ldarg.0
0x117621  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocald
0x117626  ldc.i4.0
0x117627  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x11762c  ldarg.0
0x11762d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocald
0x117632  ldc.i4.0
0x117633  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x117638  ldarg.0
0x117639  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocald
0x11763e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>2__current
0x117643  ldarg.0
0x117644  ldc.i4.4
0x117645  stfld    int32 <GetProperties>d__29::<>1__state
0x11764a  ldc.i4.1
0x11764b  stloc.0
0x11764c  leave    loc_118D76
0x117651  ldarg.0
0x117652  ldc.i4.m1
0x117653  stfld    int32 <GetProperties>d__29::<>1__state
0x117658  ldarg.0
0x117659  ldarg.0
0x11765a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x11765f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocale
0x117664  ldarg.0
0x117665  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocale
0x11766a  ldstr    aDisplayformtem// "DisplayFormTemplateName"
0x11766f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x117674  ldarg.0
0x117675  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocale
0x11767a  ldc.i4.0
0x11767b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x117680  ldarg.0
0x117681  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocale
0x117686  ldc.i4.1
0x117687  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x11768c  ldarg.0
0x11768d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocale
0x117692  ldc.i4.0
0x117693  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x117698  ldarg.0
0x117699  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocale
0x11769e  ldtoken  [mscorlib]System.String
0x1176a3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1176a8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1176ad  ldarg.0
0x1176ae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocale
0x1176b3  ldc.i4.0
0x1176b4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1176b9  ldarg.0
0x1176ba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocale
0x1176bf  ldc.i4.1
0x1176c0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1176c5  ldarg.0
0x1176c6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocale
0x1176cb  ldnull
0x1176cc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1176d1  ldarg.0
0x1176d2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocale
0x1176d7  ldstr    aDisplayformtem// "DisplayFormTemplateName"
0x1176dc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1176e1  ldarg.0
0x1176e2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocale
0x1176e7  ldnull
0x1176e8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1176ed  ldarg.0
0x1176ee  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocale
0x1176f3  ldc.i4.0
0x1176f4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1176f9  ldarg.0
0x1176fa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocale
0x1176ff  ldc.i4.0
0x117700  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x117705  ldarg.0
0x117706  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocale
0x11770b  ldc.i4.0
0x11770c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x117711  ldarg.0
0x117712  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocale
0x117717  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>2__current
0x11771c  ldarg.0
0x11771d  ldc.i4.5
0x11771e  stfld    int32 <GetProperties>d__29::<>1__state
0x117723  ldc.i4.1
0x117724  stloc.0
0x117725  leave    loc_118D76
0x11772a  ldarg.0
0x11772b  ldc.i4.m1
0x11772c  stfld    int32 <GetProperties>d__29::<>1__state
0x117731  ldarg.0
0x117732  ldarg.0
0x117733  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x117738  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalf
0x11773d  ldarg.0
0x11773e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalf
0x117743  ldstr    aDisplayformurl// "DisplayFormUrl"
0x117748  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x11774d  ldarg.0
0x11774e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalf
0x117753  ldc.i4.0
0x117754  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x117759  ldarg.0
0x11775a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalf
0x11775f  ldc.i4.1
0x117760  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x117765  ldarg.0
0x117766  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalf
0x11776b  ldc.i4.0
0x11776c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x117771  ldarg.0
0x117772  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalf
0x117777  ldtoken  [mscorlib]System.String
0x11777c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x117781  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x117786  ldarg.0
0x117787  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalf
0x11778c  ldc.i4.0
0x11778d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x117792  ldarg.0
0x117793  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalf
0x117798  ldc.i4.1
0x117799  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x11779e  ldarg.0
0x11779f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalf
0x1177a4  ldnull
0x1177a5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1177aa  ldarg.0
0x1177ab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__29::<>g__initLocalf
0x1177b0  ldstr    aDisplayformurl// "DisplayFormUrl"
0x1177b5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1177ba  ldarg.0
  ... truncated ...
```
