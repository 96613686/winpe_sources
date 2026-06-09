# <GetProperties>d__13::MoveNext

- ea: `0x14660`
- end: `0x14ee6`
- name: `<GetProperties>d__13::MoveNext`
- size: `2182`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1760`
- `0x14660`
- `0x14f10`
- `0x14f70`

## pseudocode

```c

```

## disassembly

```asm
0x14660  ldarg.0
0x14661  ldfld    int32 <GetProperties>d__13::<>1__state
0x14666  stloc.1
0x14667  ldloc.1
0x14668  switch   loc_146A2, loc_14ED9, loc_1470C, loc_147F8, loc_148D6, loc_149AF, loc_14A88, loc_14B61, loc_14C47, loc_14D21, loc_14DFB, loc_14ED2
0x1469d  br       loc_14ED9
0x146a2  ldarg.0
0x146a3  ldc.i4.m1
0x146a4  stfld    int32 <GetProperties>d__13::<>1__state
0x146a9  ldarg.0
0x146aa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__13::proxyContext
0x146af  brtrue.s loc_146BC
0x146b1  ldstr    aProxycontext// "proxyContext"
0x146b6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x146bb  throw
0x146bc  ldarg.0
0x146bd  ldarg.0
0x146be  ldfld    class Microsoft.SharePoint.Publishing.AddinSettingsServerStub <GetProperties>d__13::<>4__this
0x146c3  ldarg.0
0x146c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__13::proxyContext
0x146c9  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.AddinSettingsServerStub::<>n__FabricatedMethod17(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x146ce  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x146d3  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__13::<>7__wrap15
0x146d8  ldarg.0
0x146d9  ldc.i4.1
0x146da  stfld    int32 <GetProperties>d__13::<>1__state
0x146df  br.s     loc_14713
0x146e1  ldarg.0
0x146e2  ldarg.0
0x146e3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__13::<>7__wrap15
0x146e8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x146ed  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<item>5__14
0x146f2  ldarg.0
0x146f3  ldarg.0
0x146f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<item>5__14
0x146f9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>2__current
0x146fe  ldarg.0
0x146ff  ldc.i4.2
0x14700  stfld    int32 <GetProperties>d__13::<>1__state
0x14705  ldc.i4.1
0x14706  stloc.0
0x14707  leave    loc_14EE4
0x1470c  ldarg.0
0x1470d  ldc.i4.1
0x1470e  stfld    int32 <GetProperties>d__13::<>1__state
0x14713  ldarg.0
0x14714  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__13::<>7__wrap15
0x14719  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1471e  brtrue.s loc_146E1
0x14720  ldarg.0
0x14721  call     instance void <GetProperties>d__13::<>m__Finally16()
0x14726  ldarg.0
0x14727  ldarg.0
0x14728  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1472d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x14732  ldarg.0
0x14733  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x14738  ldstr    aDescription// "Description"
0x1473d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x14742  ldarg.0
0x14743  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x14748  ldc.i4.0
0x14749  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1474e  ldarg.0
0x1474f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x14754  ldc.i4.1
0x14755  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1475a  ldarg.0
0x1475b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x14760  ldc.i4.0
0x14761  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x14766  ldarg.0
0x14767  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x1476c  ldtoken  [mscorlib]System.String
0x14771  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14776  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1477b  ldarg.0
0x1477c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x14781  ldc.i4.0
0x14782  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x14787  ldarg.0
0x14788  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x1478d  ldc.i4.1
0x1478e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x14793  ldarg.0
0x14794  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x14799  ldnull
0x1479a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1479f  ldarg.0
0x147a0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x147a5  ldstr    aDescription// "Description"
0x147aa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x147af  ldarg.0
0x147b0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x147b5  ldnull
0x147b6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x147bb  ldarg.0
0x147bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x147c1  ldc.i4.0
0x147c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x147c7  ldarg.0
0x147c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x147cd  ldc.i4.0
0x147ce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x147d3  ldarg.0
0x147d4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x147d9  ldc.i4.0
0x147da  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x147df  ldarg.0
0x147e0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocala
0x147e5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>2__current
0x147ea  ldarg.0
0x147eb  ldc.i4.3
0x147ec  stfld    int32 <GetProperties>d__13::<>1__state
0x147f1  ldc.i4.1
0x147f2  stloc.0
0x147f3  leave    loc_14EE4
0x147f8  ldarg.0
0x147f9  ldc.i4.m1
0x147fa  stfld    int32 <GetProperties>d__13::<>1__state
0x147ff  ldarg.0
0x14800  ldarg.0
0x14801  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x14806  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x1480b  ldarg.0
0x1480c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x14811  ldstr    aEnabled// "Enabled"
0x14816  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1481b  ldarg.0
0x1481c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x14821  ldc.i4.0
0x14822  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x14827  ldarg.0
0x14828  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x1482d  ldc.i4.1
0x1482e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14833  ldarg.0
0x14834  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x14839  ldc.i4.0
0x1483a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1483f  ldarg.0
0x14840  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x14845  ldtoken  [mscorlib]System.Boolean
0x1484a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1484f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x14854  ldarg.0
0x14855  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x1485a  ldc.i4.0
0x1485b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x14860  ldarg.0
0x14861  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x14866  ldc.i4.1
0x14867  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1486c  ldarg.0
0x1486d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x14872  ldc.i4.0
0x14873  box      [mscorlib]System.Boolean
0x14878  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1487d  ldarg.0
0x1487e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x14883  ldstr    aEnabled// "Enabled"
0x14888  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1488d  ldarg.0
0x1488e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x14893  ldnull
0x14894  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x14899  ldarg.0
0x1489a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x1489f  ldc.i4.0
0x148a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x148a5  ldarg.0
0x148a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x148ab  ldc.i4.0
0x148ac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x148b1  ldarg.0
0x148b2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x148b7  ldc.i4.0
0x148b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x148bd  ldarg.0
0x148be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalb
0x148c3  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>2__current
0x148c8  ldarg.0
0x148c9  ldc.i4.4
0x148ca  stfld    int32 <GetProperties>d__13::<>1__state
0x148cf  ldc.i4.1
0x148d0  stloc.0
0x148d1  leave    loc_14EE4
0x148d6  ldarg.0
0x148d7  ldc.i4.m1
0x148d8  stfld    int32 <GetProperties>d__13::<>1__state
0x148dd  ldarg.0
0x148de  ldarg.0
0x148df  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x148e4  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x148e9  ldarg.0
0x148ea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x148ef  ldstr    aHeadscript// "HeadScript"
0x148f4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x148f9  ldarg.0
0x148fa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x148ff  ldc.i4.0
0x14900  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x14905  ldarg.0
0x14906  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x1490b  ldc.i4.1
0x1490c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14911  ldarg.0
0x14912  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x14917  ldc.i4.0
0x14918  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1491d  ldarg.0
0x1491e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x14923  ldtoken  [mscorlib]System.String
0x14928  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1492d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x14932  ldarg.0
0x14933  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x14938  ldc.i4.0
0x14939  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1493e  ldarg.0
0x1493f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x14944  ldc.i4.1
0x14945  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1494a  ldarg.0
0x1494b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x14950  ldnull
0x14951  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x14956  ldarg.0
0x14957  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x1495c  ldstr    aHeadscript// "HeadScript"
0x14961  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x14966  ldarg.0
0x14967  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x1496c  ldnull
0x1496d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x14972  ldarg.0
0x14973  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x14978  ldc.i4.0
0x14979  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1497e  ldarg.0
0x1497f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x14984  ldc.i4.0
0x14985  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1498a  ldarg.0
0x1498b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x14990  ldc.i4.0
0x14991  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x14996  ldarg.0
0x14997  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocalc
0x1499c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>2__current
0x149a1  ldarg.0
0x149a2  ldc.i4.5
0x149a3  stfld    int32 <GetProperties>d__13::<>1__state
0x149a8  ldc.i4.1
0x149a9  stloc.0
0x149aa  leave    loc_14EE4
0x149af  ldarg.0
0x149b0  ldc.i4.m1
0x149b1  stfld    int32 <GetProperties>d__13::<>1__state
0x149b6  ldarg.0
0x149b7  ldarg.0
0x149b8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x149bd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x149c2  ldarg.0
0x149c3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x149c8  ldstr    aHtmlendbody// "HtmlEndBody"
0x149cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x149d2  ldarg.0
0x149d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x149d8  ldc.i4.0
0x149d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x149de  ldarg.0
0x149df  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x149e4  ldc.i4.1
0x149e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x149ea  ldarg.0
0x149eb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x149f0  ldc.i4.0
0x149f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x149f6  ldarg.0
0x149f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x149fc  ldtoken  [mscorlib]System.String
0x14a01  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14a06  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x14a0b  ldarg.0
0x14a0c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x14a11  ldc.i4.0
0x14a12  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x14a17  ldarg.0
0x14a18  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x14a1d  ldc.i4.1
0x14a1e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x14a23  ldarg.0
0x14a24  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x14a29  ldnull
0x14a2a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x14a2f  ldarg.0
0x14a30  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__13::<>g__initLocald
0x14a35  ldstr    aHtmlendbody// "HtmlEndBody"
0x14a3a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
  ... truncated ...
```
