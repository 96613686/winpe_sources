# <GetProperties>d__2b::MoveNext

- ea: `0x139570`
- end: `0x13a7a5`
- name: `<GetProperties>d__2b::MoveNext`
- size: `4661`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x5f560`
- `0x139570`
- `0x13a7d0`
- `0x13a830`

## string_xrefs

- `0x139fdb`: `ServerRelativePath`
- `0x13a048`: `ServerRelativePath`
- `0x13a343`: `TimeCreated`
- `0x13a3bd`: `TimeCreated`
- `0x13a6d3`: `WelcomePage`
- `0x13a740`: `WelcomePage`

## pseudocode

```c

```

## disassembly

```asm
0x139570  ldarg.0
0x139571  ldfld    int32 <GetProperties>d__2b::<>1__state
0x139576  stloc.1
0x139577  ldloc.1
0x139578  switch   loc_1395DE, loc_13A798, loc_139648, loc_139734, loc_13980D, loc_1398EB, loc_1399C4, loc_139AA2, loc_139B7B, loc_139C5A, loc_139D34, loc_139E0E, loc_139EE8, loc_139FC2, loc_13A09C, loc_13A176, loc_13A250, loc_13A32A, loc_13A411, loc_13A4F8, loc_13A5D2, loc_13A6BA, loc_13A791
0x1395d9  br       loc_13A798
0x1395de  ldarg.0
0x1395df  ldc.i4.m1
0x1395e0  stfld    int32 <GetProperties>d__2b::<>1__state
0x1395e5  ldarg.0
0x1395e6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__2b::proxyContext
0x1395eb  brtrue.s loc_1395F8
0x1395ed  ldstr    aProxycontext// "proxyContext"
0x1395f2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1395f7  throw
0x1395f8  ldarg.0
0x1395f9  ldarg.0
0x1395fa  ldfld    class Microsoft.SharePoint.ServerStub.SPFolderServerStub <GetProperties>d__2b::<>4__this
0x1395ff  ldarg.0
0x139600  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__2b::proxyContext
0x139605  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPFolderServerStub::<>n__FabricatedMethod2f(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x13960a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x13960f  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__2b::<>7__wrap2d
0x139614  ldarg.0
0x139615  ldc.i4.1
0x139616  stfld    int32 <GetProperties>d__2b::<>1__state
0x13961b  br.s     loc_13964F
0x13961d  ldarg.0
0x13961e  ldarg.0
0x13961f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__2b::<>7__wrap2d
0x139624  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x139629  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<item>5__2c
0x13962e  ldarg.0
0x13962f  ldarg.0
0x139630  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<item>5__2c
0x139635  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>2__current
0x13963a  ldarg.0
0x13963b  ldc.i4.2
0x13963c  stfld    int32 <GetProperties>d__2b::<>1__state
0x139641  ldc.i4.1
0x139642  stloc.0
0x139643  leave    loc_13A7A3
0x139648  ldarg.0
0x139649  ldc.i4.1
0x13964a  stfld    int32 <GetProperties>d__2b::<>1__state
0x13964f  ldarg.0
0x139650  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__2b::<>7__wrap2d
0x139655  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13965a  brtrue.s loc_13961D
0x13965c  ldarg.0
0x13965d  call     instance void <GetProperties>d__2b::<>m__Finally2e()
0x139662  ldarg.0
0x139663  ldarg.0
0x139664  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x139669  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal17
0x13966e  ldarg.0
0x13966f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal17
0x139674  ldstr    aActivities// "Activities"
0x139679  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x13967e  ldarg.0
0x13967f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal17
0x139684  ldc.i4.0
0x139685  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x13968a  ldarg.0
0x13968b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal17
0x139690  ldc.i4.5
0x139691  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x139696  ldarg.0
0x139697  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal17
0x13969c  ldc.i4.1
0x13969d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1396a2  ldarg.0
0x1396a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal17
0x1396a8  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityEntitySet
0x1396ad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1396b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1396b7  ldarg.0
0x1396b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal17
0x1396bd  ldc.i4.1
0x1396be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1396c3  ldarg.0
0x1396c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal17
0x1396c9  ldc.i4.1
0x1396ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1396cf  ldarg.0
0x1396d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal17
0x1396d5  ldnull
0x1396d6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1396db  ldarg.0
0x1396dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal17
0x1396e1  ldstr    aActivities// "Activities"
0x1396e6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1396eb  ldarg.0
0x1396ec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal17
0x1396f1  ldnull
0x1396f2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1396f7  ldarg.0
0x1396f8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal17
0x1396fd  ldc.i4.0
0x1396fe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x139703  ldarg.0
0x139704  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal17
0x139709  ldc.i4.1
0x13970a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x13970f  ldarg.0
0x139710  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal17
0x139715  ldc.i4.0
0x139716  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x13971b  ldarg.0
0x13971c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal17
0x139721  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>2__current
0x139726  ldarg.0
0x139727  ldc.i4.3
0x139728  stfld    int32 <GetProperties>d__2b::<>1__state
0x13972d  ldc.i4.1
0x13972e  stloc.0
0x13972f  leave    loc_13A7A3
0x139734  ldarg.0
0x139735  ldc.i4.m1
0x139736  stfld    int32 <GetProperties>d__2b::<>1__state
0x13973b  ldarg.0
0x13973c  ldarg.0
0x13973d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x139742  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal18
0x139747  ldarg.0
0x139748  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal18
0x13974d  ldstr    aContenttypeord// "ContentTypeOrder"
0x139752  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x139757  ldarg.0
0x139758  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal18
0x13975d  ldc.i4.0
0x13975e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x139763  ldarg.0
0x139764  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal18
0x139769  ldc.i4.3
0x13976a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13976f  ldarg.0
0x139770  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal18
0x139775  ldc.i4.1
0x139776  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x13977b  ldarg.0
0x13977c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal18
0x139781  ldtoken  class [mscorlib]System.Collections.Generic.IList`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId>
0x139786  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13978b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x139790  ldarg.0
0x139791  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal18
0x139796  ldc.i4.1
0x139797  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x13979c  ldarg.0
0x13979d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal18
0x1397a2  ldc.i4.1
0x1397a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1397a8  ldarg.0
0x1397a9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal18
0x1397ae  ldnull
0x1397af  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1397b4  ldarg.0
0x1397b5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal18
0x1397ba  ldstr    aContenttypeord_0// "ContentTypeOrder_Client"
0x1397bf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1397c4  ldarg.0
0x1397c5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal18
0x1397ca  ldnull
0x1397cb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1397d0  ldarg.0
0x1397d1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal18
0x1397d6  ldc.i4.0
0x1397d7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1397dc  ldarg.0
0x1397dd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal18
0x1397e2  ldc.i4.0
0x1397e3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1397e8  ldarg.0
0x1397e9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal18
0x1397ee  ldc.i4.0
0x1397ef  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1397f4  ldarg.0
0x1397f5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal18
0x1397fa  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>2__current
0x1397ff  ldarg.0
0x139800  ldc.i4.4
0x139801  stfld    int32 <GetProperties>d__2b::<>1__state
0x139806  ldc.i4.1
0x139807  stloc.0
0x139808  leave    loc_13A7A3
0x13980d  ldarg.0
0x13980e  ldc.i4.m1
0x13980f  stfld    int32 <GetProperties>d__2b::<>1__state
0x139814  ldarg.0
0x139815  ldarg.0
0x139816  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x13981b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal19
0x139820  ldarg.0
0x139821  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal19
0x139826  ldstr    aExists// "Exists"
0x13982b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x139830  ldarg.0
0x139831  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal19
0x139836  ldc.i4.0
0x139837  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x13983c  ldarg.0
0x13983d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal19
0x139842  ldc.i4.1
0x139843  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x139848  ldarg.0
0x139849  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal19
0x13984e  ldc.i4.0
0x13984f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x139854  ldarg.0
0x139855  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal19
0x13985a  ldtoken  [mscorlib]System.Boolean
0x13985f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x139864  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x139869  ldarg.0
0x13986a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal19
0x13986f  ldc.i4.1
0x139870  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x139875  ldarg.0
0x139876  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal19
0x13987b  ldc.i4.1
0x13987c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x139881  ldarg.0
0x139882  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal19
0x139887  ldc.i4.0
0x139888  box      [mscorlib]System.Boolean
0x13988d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x139892  ldarg.0
0x139893  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal19
0x139898  ldstr    aExists// "Exists"
0x13989d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1398a2  ldarg.0
0x1398a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal19
0x1398a8  ldnull
0x1398a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1398ae  ldarg.0
0x1398af  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal19
0x1398b4  ldc.i4.0
0x1398b5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1398ba  ldarg.0
0x1398bb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal19
0x1398c0  ldc.i4.0
0x1398c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1398c6  ldarg.0
0x1398c7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal19
0x1398cc  ldc.i4.0
0x1398cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1398d2  ldarg.0
0x1398d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal19
0x1398d8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>2__current
0x1398dd  ldarg.0
0x1398de  ldc.i4.5
0x1398df  stfld    int32 <GetProperties>d__2b::<>1__state
0x1398e4  ldc.i4.1
0x1398e5  stloc.0
0x1398e6  leave    loc_13A7A3
0x1398eb  ldarg.0
0x1398ec  ldc.i4.m1
0x1398ed  stfld    int32 <GetProperties>d__2b::<>1__state
0x1398f2  ldarg.0
0x1398f3  ldarg.0
0x1398f4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1398f9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal1a
0x1398fe  ldarg.0
0x1398ff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal1a
0x139904  ldstr    aFiles// "Files"
0x139909  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x13990e  ldarg.0
0x13990f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal1a
0x139914  ldc.i4.0
0x139915  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x13991a  ldarg.0
0x13991b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal1a
0x139920  ldc.i4.5
0x139921  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x139926  ldarg.0
0x139927  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal1a
0x13992c  ldc.i4.0
0x13992d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x139932  ldarg.0
0x139933  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal1a
0x139938  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection
0x13993d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x139942  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x139947  ldarg.0
0x139948  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal1a
0x13994d  ldc.i4.1
0x13994e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x139953  ldarg.0
0x139954  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal1a
0x139959  ldc.i4.1
0x13995a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x13995f  ldarg.0
0x139960  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal1a
0x139965  ldnull
0x139966  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x13996b  ldarg.0
0x13996c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__2b::<>g__initLocal1a
0x139971  ldstr    aFiles// "Files"
0x139976  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
  ... truncated ...
```
