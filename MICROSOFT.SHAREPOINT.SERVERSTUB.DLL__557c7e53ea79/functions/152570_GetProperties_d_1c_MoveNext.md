# <GetProperties>d__1c::MoveNext

- ea: `0x152570`
- end: `0x1534fe`
- name: `<GetProperties>d__1c::MoveNext`
- size: `3982`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x72c90`
- `0x152570`
- `0x153520`
- `0x153580`

## string_xrefs

- `0x1528f3`: `DeletedBy`
- `0x152960`: `DeletedBy`
- `0x1529cc`: `DeletedByEmail`
- `0x152a39`: `DeletedByEmail`
- `0x152aa5`: `DeletedByName`
- `0x152b12`: `DeletedByName`
- `0x152b7e`: `DeletedDate`
- `0x152bf8`: `DeletedDate`
- `0x152c65`: `DeletedDateLocalFormatted`
- `0x152cd2`: `DeletedDateLocalFormatted`
- `0x152e19`: `DirNamePath`
- `0x152e86`: `DirNamePath`
- `0x153272`: `LeafNamePath`
- `0x1532df`: `LeafNamePath`

## pseudocode

```c

```

## disassembly

```asm
0x152570  ldarg.0
0x152571  ldfld    int32 <GetProperties>d__1c::<>1__state
0x152576  stloc.1
0x152577  ldloc.1
0x152578  switch   loc_1525D2, loc_1534F1, loc_15263C, loc_152728, loc_152801, loc_1528DA, loc_1529B3, loc_152A8C, loc_152B65, loc_152C4C, loc_152D26, loc_152E00, loc_152EDA, loc_152FC1, loc_1530A0, loc_15317F, loc_153259, loc_153333, loc_153413, loc_1534EA
0x1525cd  br       loc_1534F1
0x1525d2  ldarg.0
0x1525d3  ldc.i4.m1
0x1525d4  stfld    int32 <GetProperties>d__1c::<>1__state
0x1525d9  ldarg.0
0x1525da  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__1c::proxyContext
0x1525df  brtrue.s loc_1525EC
0x1525e1  ldstr    aProxycontext// "proxyContext"
0x1525e6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1525eb  throw
0x1525ec  ldarg.0
0x1525ed  ldarg.0
0x1525ee  ldfld    class Microsoft.SharePoint.ServerStub.SPRecycleBinItemServerStub <GetProperties>d__1c::<>4__this
0x1525f3  ldarg.0
0x1525f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__1c::proxyContext
0x1525f9  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPRecycleBinItemServerStub::<>n__FabricatedMethod20(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x1525fe  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x152603  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1c::<>7__wrap1e
0x152608  ldarg.0
0x152609  ldc.i4.1
0x15260a  stfld    int32 <GetProperties>d__1c::<>1__state
0x15260f  br.s     loc_152643
0x152611  ldarg.0
0x152612  ldarg.0
0x152613  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1c::<>7__wrap1e
0x152618  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x15261d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<item>5__1d
0x152622  ldarg.0
0x152623  ldarg.0
0x152624  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<item>5__1d
0x152629  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>2__current
0x15262e  ldarg.0
0x15262f  ldc.i4.2
0x152630  stfld    int32 <GetProperties>d__1c::<>1__state
0x152635  ldc.i4.1
0x152636  stloc.0
0x152637  leave    loc_1534FC
0x15263c  ldarg.0
0x15263d  ldc.i4.1
0x15263e  stfld    int32 <GetProperties>d__1c::<>1__state
0x152643  ldarg.0
0x152644  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1c::<>7__wrap1e
0x152649  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x15264e  brtrue.s loc_152611
0x152650  ldarg.0
0x152651  call     instance void <GetProperties>d__1c::<>m__Finally1f()
0x152656  ldarg.0
0x152657  ldarg.0
0x152658  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x15265d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x152662  ldarg.0
0x152663  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x152668  ldstr    aAuthor_0// "Author"
0x15266d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x152672  ldarg.0
0x152673  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x152678  ldc.i4.0
0x152679  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x15267e  ldarg.0
0x15267f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x152684  ldc.i4.4
0x152685  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x15268a  ldarg.0
0x15268b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x152690  ldc.i4.0
0x152691  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x152696  ldarg.0
0x152697  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x15269c  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPUser
0x1526a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1526a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1526ab  ldarg.0
0x1526ac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1526b1  ldc.i4.1
0x1526b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1526b7  ldarg.0
0x1526b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1526bd  ldc.i4.1
0x1526be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1526c3  ldarg.0
0x1526c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1526c9  ldnull
0x1526ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1526cf  ldarg.0
0x1526d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1526d5  ldstr    aAuthor_0// "Author"
0x1526da  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1526df  ldarg.0
0x1526e0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1526e5  ldnull
0x1526e6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1526eb  ldarg.0
0x1526ec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1526f1  ldc.i4.0
0x1526f2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1526f7  ldarg.0
0x1526f8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1526fd  ldc.i4.0
0x1526fe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x152703  ldarg.0
0x152704  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x152709  ldc.i4.0
0x15270a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x15270f  ldarg.0
0x152710  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x152715  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>2__current
0x15271a  ldarg.0
0x15271b  ldc.i4.3
0x15271c  stfld    int32 <GetProperties>d__1c::<>1__state
0x152721  ldc.i4.1
0x152722  stloc.0
0x152723  leave    loc_1534FC
0x152728  ldarg.0
0x152729  ldc.i4.m1
0x15272a  stfld    int32 <GetProperties>d__1c::<>1__state
0x15272f  ldarg.0
0x152730  ldarg.0
0x152731  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x152736  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x15273b  ldarg.0
0x15273c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x152741  ldstr    aAuthoremail// "AuthorEmail"
0x152746  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x15274b  ldarg.0
0x15274c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x152751  ldc.i4.0
0x152752  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x152757  ldarg.0
0x152758  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x15275d  ldc.i4.1
0x15275e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x152763  ldarg.0
0x152764  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x152769  ldc.i4.0
0x15276a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x15276f  ldarg.0
0x152770  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x152775  ldtoken  [mscorlib]System.String
0x15277a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15277f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x152784  ldarg.0
0x152785  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x15278a  ldc.i4.1
0x15278b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x152790  ldarg.0
0x152791  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x152796  ldc.i4.1
0x152797  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x15279c  ldarg.0
0x15279d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1527a2  ldnull
0x1527a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1527a8  ldarg.0
0x1527a9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1527ae  ldstr    aAuthoremail// "AuthorEmail"
0x1527b3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1527b8  ldarg.0
0x1527b9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1527be  ldnull
0x1527bf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1527c4  ldarg.0
0x1527c5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1527ca  ldc.i4.0
0x1527cb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1527d0  ldarg.0
0x1527d1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1527d6  ldc.i4.0
0x1527d7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1527dc  ldarg.0
0x1527dd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1527e2  ldc.i4.0
0x1527e3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1527e8  ldarg.0
0x1527e9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1527ee  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>2__current
0x1527f3  ldarg.0
0x1527f4  ldc.i4.4
0x1527f5  stfld    int32 <GetProperties>d__1c::<>1__state
0x1527fa  ldc.i4.1
0x1527fb  stloc.0
0x1527fc  leave    loc_1534FC
0x152801  ldarg.0
0x152802  ldc.i4.m1
0x152803  stfld    int32 <GetProperties>d__1c::<>1__state
0x152808  ldarg.0
0x152809  ldarg.0
0x15280a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x15280f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x152814  ldarg.0
0x152815  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x15281a  ldstr    aAuthorname// "AuthorName"
0x15281f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x152824  ldarg.0
0x152825  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x15282a  ldc.i4.0
0x15282b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x152830  ldarg.0
0x152831  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x152836  ldc.i4.1
0x152837  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x15283c  ldarg.0
0x15283d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x152842  ldc.i4.0
0x152843  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x152848  ldarg.0
0x152849  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x15284e  ldtoken  [mscorlib]System.String
0x152853  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x152858  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x15285d  ldarg.0
0x15285e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x152863  ldc.i4.1
0x152864  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x152869  ldarg.0
0x15286a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x15286f  ldc.i4.1
0x152870  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x152875  ldarg.0
0x152876  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x15287b  ldnull
0x15287c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x152881  ldarg.0
0x152882  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x152887  ldstr    aAuthorname// "AuthorName"
0x15288c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x152891  ldarg.0
0x152892  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x152897  ldnull
0x152898  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x15289d  ldarg.0
0x15289e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x1528a3  ldc.i4.0
0x1528a4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1528a9  ldarg.0
0x1528aa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x1528af  ldc.i4.0
0x1528b0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1528b5  ldarg.0
0x1528b6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x1528bb  ldc.i4.0
0x1528bc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1528c1  ldarg.0
0x1528c2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x1528c7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>2__current
0x1528cc  ldarg.0
0x1528cd  ldc.i4.5
0x1528ce  stfld    int32 <GetProperties>d__1c::<>1__state
0x1528d3  ldc.i4.1
0x1528d4  stloc.0
0x1528d5  leave    loc_1534FC
0x1528da  ldarg.0
0x1528db  ldc.i4.m1
0x1528dc  stfld    int32 <GetProperties>d__1c::<>1__state
0x1528e1  ldarg.0
0x1528e2  ldarg.0
0x1528e3  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1528e8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocale
0x1528ed  ldarg.0
0x1528ee  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocale
0x1528f3  ldstr    aDeletedby// "DeletedBy"
0x1528f8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1528fd  ldarg.0
0x1528fe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocale
0x152903  ldc.i4.0
0x152904  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x152909  ldarg.0
0x15290a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocale
0x15290f  ldc.i4.4
0x152910  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x152915  ldarg.0
0x152916  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocale
0x15291b  ldc.i4.0
0x15291c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x152921  ldarg.0
0x152922  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocale
0x152927  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPUser
0x15292c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x152931  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x152936  ldarg.0
0x152937  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocale
0x15293c  ldc.i4.1
0x15293d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x152942  ldarg.0
0x152943  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocale
0x152948  ldc.i4.1
0x152949  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x15294e  ldarg.0
0x15294f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocale
0x152954  ldnull
0x152955  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x15295a  ldarg.0
0x15295b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocale
0x152960  ldstr    aDeletedby// "DeletedBy"
0x152965  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x15296a  ldarg.0
  ... truncated ...
```
