# <GetProperties>d__8::MoveNext

- ea: `0x15010`
- end: `0x157ca`
- name: `<GetProperties>d__8::MoveNext`
- size: `1978`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1e00`
- `0x15010`
- `0x157f0`
- `0x15850`

## string_xrefs

- `0x156eb`: `WebTemplateExtensionId`
- `0x15765`: `WebTemplateExtensionId`

## pseudocode

```c

```

## disassembly

```asm
0x15010  ldarg.0
0x15011  ldfld    int32 <GetProperties>d__8::<>1__state
0x15016  stloc.1
0x15017  ldloc.1
0x15018  switch   loc_1504E, loc_157BD, loc_150B8, loc_151A9, loc_15282, loc_1535B, loc_15439, loc_1551F, loc_155F8, loc_156D2, loc_157B6
0x15049  br       loc_157BD
0x1504e  ldarg.0
0x1504f  ldc.i4.m1
0x15050  stfld    int32 <GetProperties>d__8::<>1__state
0x15055  ldarg.0
0x15056  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__8::proxyContext
0x1505b  brtrue.s loc_15068
0x1505d  ldstr    aProxycontext// "proxyContext"
0x15062  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x15067  throw
0x15068  ldarg.0
0x15069  ldarg.0
0x1506a  ldfld    class Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequestValueTypeConverter <GetProperties>d__8::<>4__this
0x1506f  ldarg.0
0x15070  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__8::proxyContext
0x15075  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequestValueTypeConverter::<>n__FabricatedMethodc(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x1507a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x1507f  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__8::<>7__wrapa
0x15084  ldarg.0
0x15085  ldc.i4.1
0x15086  stfld    int32 <GetProperties>d__8::<>1__state
0x1508b  br.s     loc_150BF
0x1508d  ldarg.0
0x1508e  ldarg.0
0x1508f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__8::<>7__wrapa
0x15094  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x15099  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<item>5__9
0x1509e  ldarg.0
0x1509f  ldarg.0
0x150a0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<item>5__9
0x150a5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>2__current
0x150aa  ldarg.0
0x150ab  ldc.i4.2
0x150ac  stfld    int32 <GetProperties>d__8::<>1__state
0x150b1  ldc.i4.1
0x150b2  stloc.0
0x150b3  leave    loc_157C8
0x150b8  ldarg.0
0x150b9  ldc.i4.1
0x150ba  stfld    int32 <GetProperties>d__8::<>1__state
0x150bf  ldarg.0
0x150c0  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__8::<>7__wrapa
0x150c5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x150ca  brtrue.s loc_1508D
0x150cc  ldarg.0
0x150cd  call     instance void <GetProperties>d__8::<>m__Finallyb()
0x150d2  ldarg.0
0x150d3  ldarg.0
0x150d4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x150d9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal0
0x150de  ldarg.0
0x150df  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal0
0x150e4  ldstr    aAllowfileshari// "AllowFileSharingForGuestUsers"
0x150e9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x150ee  ldarg.0
0x150ef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal0
0x150f4  ldc.i4.0
0x150f5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x150fa  ldarg.0
0x150fb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal0
0x15100  ldc.i4.1
0x15101  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x15106  ldarg.0
0x15107  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal0
0x1510c  ldc.i4.0
0x1510d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x15112  ldarg.0
0x15113  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal0
0x15118  ldtoken  [mscorlib]System.Boolean
0x1511d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15122  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x15127  ldarg.0
0x15128  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal0
0x1512d  ldc.i4.0
0x1512e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x15133  ldarg.0
0x15134  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal0
0x15139  ldc.i4.1
0x1513a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1513f  ldarg.0
0x15140  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal0
0x15145  ldc.i4.0
0x15146  box      [mscorlib]System.Boolean
0x1514b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x15150  ldarg.0
0x15151  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal0
0x15156  ldstr    aAllowfileshari// "AllowFileSharingForGuestUsers"
0x1515b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x15160  ldarg.0
0x15161  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal0
0x15166  ldnull
0x15167  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1516c  ldarg.0
0x1516d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal0
0x15172  ldc.i4.0
0x15173  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x15178  ldarg.0
0x15179  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal0
0x1517e  ldc.i4.0
0x1517f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x15184  ldarg.0
0x15185  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal0
0x1518a  ldc.i4.0
0x1518b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x15190  ldarg.0
0x15191  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal0
0x15196  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>2__current
0x1519b  ldarg.0
0x1519c  ldc.i4.3
0x1519d  stfld    int32 <GetProperties>d__8::<>1__state
0x151a2  ldc.i4.1
0x151a3  stloc.0
0x151a4  leave    loc_157C8
0x151a9  ldarg.0
0x151aa  ldc.i4.m1
0x151ab  stfld    int32 <GetProperties>d__8::<>1__state
0x151b0  ldarg.0
0x151b1  ldarg.0
0x151b2  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x151b7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal1
0x151bc  ldarg.0
0x151bd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal1
0x151c2  ldstr    aClassification// "Classification"
0x151c7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x151cc  ldarg.0
0x151cd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal1
0x151d2  ldc.i4.0
0x151d3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x151d8  ldarg.0
0x151d9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal1
0x151de  ldc.i4.1
0x151df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x151e4  ldarg.0
0x151e5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal1
0x151ea  ldc.i4.0
0x151eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x151f0  ldarg.0
0x151f1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal1
0x151f6  ldtoken  [mscorlib]System.String
0x151fb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15200  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x15205  ldarg.0
0x15206  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal1
0x1520b  ldc.i4.0
0x1520c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x15211  ldarg.0
0x15212  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal1
0x15217  ldc.i4.1
0x15218  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1521d  ldarg.0
0x1521e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal1
0x15223  ldnull
0x15224  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x15229  ldarg.0
0x1522a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal1
0x1522f  ldstr    aClassification// "Classification"
0x15234  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x15239  ldarg.0
0x1523a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal1
0x1523f  ldnull
0x15240  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x15245  ldarg.0
0x15246  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal1
0x1524b  ldc.i4.0
0x1524c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x15251  ldarg.0
0x15252  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal1
0x15257  ldc.i4.0
0x15258  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1525d  ldarg.0
0x1525e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal1
0x15263  ldc.i4.0
0x15264  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x15269  ldarg.0
0x1526a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal1
0x1526f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>2__current
0x15274  ldarg.0
0x15275  ldc.i4.4
0x15276  stfld    int32 <GetProperties>d__8::<>1__state
0x1527b  ldc.i4.1
0x1527c  stloc.0
0x1527d  leave    loc_157C8
0x15282  ldarg.0
0x15283  ldc.i4.m1
0x15284  stfld    int32 <GetProperties>d__8::<>1__state
0x15289  ldarg.0
0x1528a  ldarg.0
0x1528b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x15290  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal2
0x15295  ldarg.0
0x15296  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal2
0x1529b  ldstr    aDescription// "Description"
0x152a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x152a5  ldarg.0
0x152a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal2
0x152ab  ldc.i4.0
0x152ac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x152b1  ldarg.0
0x152b2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal2
0x152b7  ldc.i4.1
0x152b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x152bd  ldarg.0
0x152be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal2
0x152c3  ldc.i4.0
0x152c4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x152c9  ldarg.0
0x152ca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal2
0x152cf  ldtoken  [mscorlib]System.String
0x152d4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x152d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x152de  ldarg.0
0x152df  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal2
0x152e4  ldc.i4.0
0x152e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x152ea  ldarg.0
0x152eb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal2
0x152f0  ldc.i4.1
0x152f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x152f6  ldarg.0
0x152f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal2
0x152fc  ldnull
0x152fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x15302  ldarg.0
0x15303  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal2
0x15308  ldstr    aDescription// "Description"
0x1530d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x15312  ldarg.0
0x15313  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal2
0x15318  ldnull
0x15319  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1531e  ldarg.0
0x1531f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal2
0x15324  ldc.i4.0
0x15325  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1532a  ldarg.0
0x1532b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal2
0x15330  ldc.i4.0
0x15331  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x15336  ldarg.0
0x15337  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal2
0x1533c  ldc.i4.0
0x1533d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x15342  ldarg.0
0x15343  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal2
0x15348  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>2__current
0x1534d  ldarg.0
0x1534e  ldc.i4.5
0x1534f  stfld    int32 <GetProperties>d__8::<>1__state
0x15354  ldc.i4.1
0x15355  stloc.0
0x15356  leave    loc_157C8
0x1535b  ldarg.0
0x1535c  ldc.i4.m1
0x1535d  stfld    int32 <GetProperties>d__8::<>1__state
0x15362  ldarg.0
0x15363  ldarg.0
0x15364  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x15369  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal3
0x1536e  ldarg.0
0x1536f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal3
0x15374  ldstr    aLcid_0// "lcid"
0x15379  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1537e  ldarg.0
0x1537f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal3
0x15384  ldc.i4.0
0x15385  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1538a  ldarg.0
0x1538b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal3
0x15390  ldc.i4.1
0x15391  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x15396  ldarg.0
0x15397  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal3
0x1539c  ldc.i4.0
0x1539d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x153a2  ldarg.0
0x153a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal3
0x153a8  ldtoken  [mscorlib]System.Int32
0x153ad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x153b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x153b7  ldarg.0
0x153b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal3
0x153bd  ldc.i4.0
0x153be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x153c3  ldarg.0
0x153c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal3
0x153c9  ldc.i4.1
0x153ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x153cf  ldarg.0
0x153d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal3
0x153d5  ldc.i4.0
0x153d6  box      [mscorlib]System.Int32
0x153db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x153e0  ldarg.0
0x153e1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__8::<>g__initLocal3
0x153e6  ldstr    aLcid_0// "lcid"
  ... truncated ...
```
