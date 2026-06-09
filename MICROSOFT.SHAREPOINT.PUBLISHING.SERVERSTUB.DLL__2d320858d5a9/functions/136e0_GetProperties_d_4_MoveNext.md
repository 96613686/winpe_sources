# <GetProperties>d__4::MoveNext

- ea: `0x136e0`
- end: `0x13b05`
- name: `<GetProperties>d__4::MoveNext`
- size: `1061`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x3b0`
- `0x136e0`
- `0x13b30`
- `0x13b90`

## pseudocode

```c

```

## disassembly

```asm
0x136e0  ldarg.0
0x136e1  ldfld    int32 <GetProperties>d__4::<>1__state
0x136e6  stloc.1
0x136e7  ldloc.1
0x136e8  switch   loc_1370E, loc_13AF8, loc_13778, loc_13864, loc_1393D, loc_13A1B, loc_13AF1
0x13709  br       loc_13AF8
0x1370e  ldarg.0
0x1370f  ldc.i4.m1
0x13710  stfld    int32 <GetProperties>d__4::<>1__state
0x13715  ldarg.0
0x13716  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__4::proxyContext
0x1371b  brtrue.s loc_13728
0x1371d  ldstr    aProxycontext// "proxyContext"
0x13722  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13727  throw
0x13728  ldarg.0
0x13729  ldarg.0
0x1372a  ldfld    class Microsoft.SharePoint.Publishing.AcronymInformationValueTypeConverter <GetProperties>d__4::<>4__this
0x1372f  ldarg.0
0x13730  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__4::proxyContext
0x13735  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.AcronymInformationValueTypeConverter::<>n__FabricatedMethod8(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x1373a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x1373f  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__4::<>7__wrap6
0x13744  ldarg.0
0x13745  ldc.i4.1
0x13746  stfld    int32 <GetProperties>d__4::<>1__state
0x1374b  br.s     loc_1377F
0x1374d  ldarg.0
0x1374e  ldarg.0
0x1374f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__4::<>7__wrap6
0x13754  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x13759  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<item>5__5
0x1375e  ldarg.0
0x1375f  ldarg.0
0x13760  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<item>5__5
0x13765  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>2__current
0x1376a  ldarg.0
0x1376b  ldc.i4.2
0x1376c  stfld    int32 <GetProperties>d__4::<>1__state
0x13771  ldc.i4.1
0x13772  stloc.0
0x13773  leave    loc_13B03
0x13778  ldarg.0
0x13779  ldc.i4.1
0x1377a  stfld    int32 <GetProperties>d__4::<>1__state
0x1377f  ldarg.0
0x13780  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__4::<>7__wrap6
0x13785  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1378a  brtrue.s loc_1374D
0x1378c  ldarg.0
0x1378d  call     instance void <GetProperties>d__4::<>m__Finally7()
0x13792  ldarg.0
0x13793  ldarg.0
0x13794  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x13799  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x1379e  ldarg.0
0x1379f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x137a4  ldstr    aAcronym// "Acronym"
0x137a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x137ae  ldarg.0
0x137af  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x137b4  ldc.i4.0
0x137b5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x137ba  ldarg.0
0x137bb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x137c0  ldc.i4.1
0x137c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x137c6  ldarg.0
0x137c7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x137cc  ldc.i4.0
0x137cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x137d2  ldarg.0
0x137d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x137d8  ldtoken  [mscorlib]System.String
0x137dd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x137e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x137e7  ldarg.0
0x137e8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x137ed  ldc.i4.0
0x137ee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x137f3  ldarg.0
0x137f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x137f9  ldc.i4.1
0x137fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x137ff  ldarg.0
0x13800  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x13805  ldnull
0x13806  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1380b  ldarg.0
0x1380c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x13811  ldstr    aAcronym// "Acronym"
0x13816  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1381b  ldarg.0
0x1381c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x13821  ldnull
0x13822  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x13827  ldarg.0
0x13828  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x1382d  ldc.i4.0
0x1382e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x13833  ldarg.0
0x13834  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x13839  ldc.i4.0
0x1383a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1383f  ldarg.0
0x13840  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x13845  ldc.i4.0
0x13846  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1384b  ldarg.0
0x1384c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x13851  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>2__current
0x13856  ldarg.0
0x13857  ldc.i4.3
0x13858  stfld    int32 <GetProperties>d__4::<>1__state
0x1385d  ldc.i4.1
0x1385e  stloc.0
0x1385f  leave    loc_13B03
0x13864  ldarg.0
0x13865  ldc.i4.m1
0x13866  stfld    int32 <GetProperties>d__4::<>1__state
0x1386b  ldarg.0
0x1386c  ldarg.0
0x1386d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x13872  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x13877  ldarg.0
0x13878  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x1387d  ldstr    aColor// "Color"
0x13882  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x13887  ldarg.0
0x13888  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x1388d  ldc.i4.0
0x1388e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x13893  ldarg.0
0x13894  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x13899  ldc.i4.1
0x1389a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1389f  ldarg.0
0x138a0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x138a5  ldc.i4.0
0x138a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x138ab  ldarg.0
0x138ac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x138b1  ldtoken  [mscorlib]System.String
0x138b6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x138bb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x138c0  ldarg.0
0x138c1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x138c6  ldc.i4.0
0x138c7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x138cc  ldarg.0
0x138cd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x138d2  ldc.i4.1
0x138d3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x138d8  ldarg.0
0x138d9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x138de  ldnull
0x138df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x138e4  ldarg.0
0x138e5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x138ea  ldstr    aColor// "Color"
0x138ef  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x138f4  ldarg.0
0x138f5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x138fa  ldnull
0x138fb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x13900  ldarg.0
0x13901  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x13906  ldc.i4.0
0x13907  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1390c  ldarg.0
0x1390d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x13912  ldc.i4.0
0x13913  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x13918  ldarg.0
0x13919  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x1391e  ldc.i4.0
0x1391f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x13924  ldarg.0
0x13925  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x1392a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>2__current
0x1392f  ldarg.0
0x13930  ldc.i4.4
0x13931  stfld    int32 <GetProperties>d__4::<>1__state
0x13936  ldc.i4.1
0x13937  stloc.0
0x13938  leave    loc_13B03
0x1393d  ldarg.0
0x1393e  ldc.i4.m1
0x1393f  stfld    int32 <GetProperties>d__4::<>1__state
0x13944  ldarg.0
0x13945  ldarg.0
0x13946  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1394b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x13950  ldarg.0
0x13951  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x13956  ldstr    aLcid// "Lcid"
0x1395b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x13960  ldarg.0
0x13961  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x13966  ldc.i4.0
0x13967  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1396c  ldarg.0
0x1396d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x13972  ldc.i4.1
0x13973  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13978  ldarg.0
0x13979  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x1397e  ldc.i4.0
0x1397f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x13984  ldarg.0
0x13985  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x1398a  ldtoken  [mscorlib]System.Int32
0x1398f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13994  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x13999  ldarg.0
0x1399a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x1399f  ldc.i4.0
0x139a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x139a5  ldarg.0
0x139a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x139ab  ldc.i4.1
0x139ac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x139b1  ldarg.0
0x139b2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x139b7  ldc.i4.0
0x139b8  box      [mscorlib]System.Int32
0x139bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x139c2  ldarg.0
0x139c3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x139c8  ldstr    aLcid// "Lcid"
0x139cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x139d2  ldarg.0
0x139d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x139d8  ldnull
0x139d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x139de  ldarg.0
0x139df  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x139e4  ldc.i4.0
0x139e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x139ea  ldarg.0
0x139eb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x139f0  ldc.i4.0
0x139f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x139f6  ldarg.0
0x139f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x139fc  ldc.i4.0
0x139fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x13a02  ldarg.0
0x13a03  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x13a08  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>2__current
0x13a0d  ldarg.0
0x13a0e  ldc.i4.5
0x13a0f  stfld    int32 <GetProperties>d__4::<>1__state
0x13a14  ldc.i4.1
0x13a15  stloc.0
0x13a16  leave    loc_13B03
0x13a1b  ldarg.0
0x13a1c  ldc.i4.m1
0x13a1d  stfld    int32 <GetProperties>d__4::<>1__state
0x13a22  ldarg.0
0x13a23  ldarg.0
0x13a24  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x13a29  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x13a2e  ldarg.0
0x13a2f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x13a34  ldstr    aText// "Text"
0x13a39  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x13a3e  ldarg.0
0x13a3f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x13a44  ldc.i4.0
0x13a45  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x13a4a  ldarg.0
0x13a4b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x13a50  ldc.i4.1
0x13a51  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13a56  ldarg.0
0x13a57  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x13a5c  ldc.i4.0
0x13a5d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x13a62  ldarg.0
0x13a63  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x13a68  ldtoken  [mscorlib]System.String
0x13a6d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13a72  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x13a77  ldarg.0
0x13a78  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x13a7d  ldc.i4.0
0x13a7e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x13a83  ldarg.0
0x13a84  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x13a89  ldc.i4.1
0x13a8a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x13a8f  ldarg.0
0x13a90  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x13a95  ldnull
0x13a96  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x13a9b  ldarg.0
0x13a9c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x13aa1  ldstr    aText// "Text"
0x13aa6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
  ... truncated ...
```
