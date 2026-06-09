# <GetMethods>d__8::MoveNext

- ea: `0xe7580`
- end: `0xe7b98`
- name: `<GetMethods>d__8::MoveNext`
- size: `1560`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x21650`
- `0xe7580`
- `0xe7bc0`
- `0xe7c20`

## string_xrefs

- `0xe78f2`: `Remove`
- `0xe792a`: `Remove`
- `0xe7a49`: `RemoveById`
- `0xe7a81`: `RemoveById`
- `0xe770a`: `absolutePath`
- `0xe7861`: `absolutePath`
- `0xe79b8`: `absolutePath`

## pseudocode

```c

```

## disassembly

```asm
0xe7580  ldarg.0
0xe7581  ldfld    int32 <GetMethods>d__8::<>1__state
0xe7586  stloc.1
0xe7587  ldloc.1
0xe7588  switch   loc_E75AE, loc_E7B8B, loc_E7618, loc_E7782, loc_E78D9, loc_E7A30, loc_E7B84
0xe75a9  br       loc_E7B8B
0xe75ae  ldarg.0
0xe75af  ldc.i4.m1
0xe75b0  stfld    int32 <GetMethods>d__8::<>1__state
0xe75b5  ldarg.0
0xe75b6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__8::proxyContext
0xe75bb  brtrue.s loc_E75C8
0xe75bd  ldstr    aProxycontext// "proxyContext"
0xe75c2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe75c7  throw
0xe75c8  ldarg.0
0xe75c9  ldarg.0
0xe75ca  ldfld    class Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPSiteCollectionAppCatalogAllowedCollectionServerStub <GetMethods>d__8::<>4__this
0xe75cf  ldarg.0
0xe75d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__8::proxyContext
0xe75d5  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPSiteCollectionAppCatalogAllowedCollectionServerStub::<>n__FabricatedMethodd(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0xe75da  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0xe75df  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__8::<>7__wrapb
0xe75e4  ldarg.0
0xe75e5  ldc.i4.1
0xe75e6  stfld    int32 <GetMethods>d__8::<>1__state
0xe75eb  br.s     loc_E761F
0xe75ed  ldarg.0
0xe75ee  ldarg.0
0xe75ef  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__8::<>7__wrapb
0xe75f4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0xe75f9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<itemBase>5__9
0xe75fe  ldarg.0
0xe75ff  ldarg.0
0xe7600  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<itemBase>5__9
0xe7605  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>2__current
0xe760a  ldarg.0
0xe760b  ldc.i4.2
0xe760c  stfld    int32 <GetMethods>d__8::<>1__state
0xe7611  ldc.i4.1
0xe7612  stloc.0
0xe7613  leave    loc_E7B96
0xe7618  ldarg.0
0xe7619  ldc.i4.1
0xe761a  stfld    int32 <GetMethods>d__8::<>1__state
0xe761f  ldarg.0
0xe7620  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__8::<>7__wrapb
0xe7625  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe762a  brtrue.s loc_E75ED
0xe762c  ldarg.0
0xe762d  call     instance void <GetMethods>d__8::<>m__Finallyc()
0xe7632  ldarg.0
0xe7633  ldarg.0
0xe7634  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xe7639  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal0
0xe763e  ldarg.0
0xe763f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal0
0xe7644  ldstr    aAdd// "Add"
0xe7649  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xe764e  ldarg.0
0xe764f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal0
0xe7654  ldc.i4.0
0xe7655  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xe765a  ldarg.0
0xe765b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal0
0xe7660  ldc.i4.0
0xe7661  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xe7666  ldarg.0
0xe7667  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal0
0xe766c  ldc.i4   0xFFFFFFF
0xe7671  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xe7676  ldarg.0
0xe7677  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal0
0xe767c  ldstr    aAdd// "Add"
0xe7681  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xe7686  ldarg.0
0xe7687  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal0
0xe768c  ldc.i4.0
0xe768d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xe7692  ldarg.0
0xe7693  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal0
0xe7698  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPSiteCollectionAppCatalogAllowedItem
0xe769d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe76a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xe76a7  ldarg.0
0xe76a8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal0
0xe76ad  ldc.i4.4
0xe76ae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe76b3  ldarg.0
0xe76b4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal0
0xe76b9  ldc.i4.0
0xe76ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xe76bf  ldarg.0
0xe76c0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal0
0xe76c5  ldc.i4.0
0xe76c6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0xe76cb  ldarg.0
0xe76cc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal0
0xe76d1  ldc.i4.0
0xe76d2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xe76d7  ldarg.0
0xe76d8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal0
0xe76dd  ldc.i4.0
0xe76de  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0xe76e3  ldarg.0
0xe76e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal0
0xe76e9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<item>5__a
0xe76ee  ldarg.0
0xe76ef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<item>5__a
0xe76f4  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xe76f9  ldarg.0
0xe76fa  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xe76ff  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__8::<>g__initLocal1
0xe7704  ldarg.0
0xe7705  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__8::<>g__initLocal1
0xe770a  ldstr    aAbsolutepath// "absolutePath"
0xe770f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xe7714  ldarg.0
0xe7715  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__8::<>g__initLocal1
0xe771a  ldc.i4.0
0xe771b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xe7720  ldarg.0
0xe7721  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__8::<>g__initLocal1
0xe7726  ldtoken  [mscorlib]System.String
0xe772b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe7730  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xe7735  ldarg.0
0xe7736  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__8::<>g__initLocal1
0xe773b  ldc.i4.1
0xe773c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe7741  ldarg.0
0xe7742  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__8::<>g__initLocal1
0xe7747  ldc.i4.0
0xe7748  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0xe774d  ldarg.0
0xe774e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__8::<>g__initLocal1
0xe7753  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xe7758  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0xe775d  ldarg.0
0xe775e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__8::<>g__initLocal1
0xe7763  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0xe7768  ldarg.0
0xe7769  ldarg.0
0xe776a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<item>5__a
0xe776f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>2__current
0xe7774  ldarg.0
0xe7775  ldc.i4.3
0xe7776  stfld    int32 <GetMethods>d__8::<>1__state
0xe777b  ldc.i4.1
0xe777c  stloc.0
0xe777d  leave    loc_E7B96
0xe7782  ldarg.0
0xe7783  ldc.i4.m1
0xe7784  stfld    int32 <GetMethods>d__8::<>1__state
0xe7789  ldarg.0
0xe778a  ldarg.0
0xe778b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xe7790  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal2
0xe7795  ldarg.0
0xe7796  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal2
0xe779b  ldstr    aGetbyabsoluteu// "GetByAbsoluteUrl"
0xe77a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xe77a5  ldarg.0
0xe77a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal2
0xe77ab  ldc.i4.0
0xe77ac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xe77b1  ldarg.0
0xe77b2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal2
0xe77b7  ldc.i4.1
0xe77b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xe77bd  ldarg.0
0xe77be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal2
0xe77c3  ldc.i4   0xFFFFFFF
0xe77c8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xe77cd  ldarg.0
0xe77ce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal2
0xe77d3  ldstr    aGetbyabsoluteu// "GetByAbsoluteUrl"
0xe77d8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xe77dd  ldarg.0
0xe77de  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal2
0xe77e3  ldc.i4.0
0xe77e4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xe77e9  ldarg.0
0xe77ea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal2
0xe77ef  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPSiteCollectionAppCatalogAllowedItem
0xe77f4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe77f9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xe77fe  ldarg.0
0xe77ff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal2
0xe7804  ldc.i4.4
0xe7805  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe780a  ldarg.0
0xe780b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal2
0xe7810  ldc.i4.0
0xe7811  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xe7816  ldarg.0
0xe7817  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal2
0xe781c  ldc.i4.0
0xe781d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0xe7822  ldarg.0
0xe7823  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal2
0xe7828  ldc.i4.0
0xe7829  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xe782e  ldarg.0
0xe782f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal2
0xe7834  ldc.i4.0
0xe7835  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0xe783a  ldarg.0
0xe783b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal2
0xe7840  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<item>5__a
0xe7845  ldarg.0
0xe7846  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<item>5__a
0xe784b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xe7850  ldarg.0
0xe7851  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xe7856  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__8::<>g__initLocal3
0xe785b  ldarg.0
0xe785c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__8::<>g__initLocal3
0xe7861  ldstr    aAbsolutepath// "absolutePath"
0xe7866  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xe786b  ldarg.0
0xe786c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__8::<>g__initLocal3
0xe7871  ldc.i4.0
0xe7872  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xe7877  ldarg.0
0xe7878  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__8::<>g__initLocal3
0xe787d  ldtoken  [mscorlib]System.String
0xe7882  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe7887  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xe788c  ldarg.0
0xe788d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__8::<>g__initLocal3
0xe7892  ldc.i4.1
0xe7893  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe7898  ldarg.0
0xe7899  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__8::<>g__initLocal3
0xe789e  ldc.i4.0
0xe789f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0xe78a4  ldarg.0
0xe78a5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__8::<>g__initLocal3
0xe78aa  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xe78af  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0xe78b4  ldarg.0
0xe78b5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__8::<>g__initLocal3
0xe78ba  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0xe78bf  ldarg.0
0xe78c0  ldarg.0
0xe78c1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<item>5__a
0xe78c6  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>2__current
0xe78cb  ldarg.0
0xe78cc  ldc.i4.4
0xe78cd  stfld    int32 <GetMethods>d__8::<>1__state
0xe78d2  ldc.i4.1
0xe78d3  stloc.0
0xe78d4  leave    loc_E7B96
0xe78d9  ldarg.0
0xe78da  ldc.i4.m1
0xe78db  stfld    int32 <GetMethods>d__8::<>1__state
0xe78e0  ldarg.0
0xe78e1  ldarg.0
0xe78e2  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xe78e7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal4
0xe78ec  ldarg.0
0xe78ed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal4
0xe78f2  ldstr    aRemove// "Remove"
0xe78f7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xe78fc  ldarg.0
0xe78fd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal4
0xe7902  ldc.i4.0
0xe7903  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xe7908  ldarg.0
0xe7909  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal4
0xe790e  ldc.i4.0
0xe790f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xe7914  ldarg.0
0xe7915  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal4
0xe791a  ldc.i4   0xFFFFFFF
0xe791f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xe7924  ldarg.0
0xe7925  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal4
0xe792a  ldstr    aRemove// "Remove"
0xe792f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xe7934  ldarg.0
0xe7935  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal4
0xe793a  ldc.i4.0
0xe793b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xe7940  ldarg.0
0xe7941  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal4
0xe7946  ldtoken  [mscorlib]System.Void
0xe794b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe7950  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xe7955  ldarg.0
0xe7956  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal4
0xe795b  ldc.i4.0
0xe795c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe7961  ldarg.0
0xe7962  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal4
0xe7967  ldc.i4.0
0xe7968  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xe796d  ldarg.0
0xe796e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__8::<>g__initLocal4
  ... truncated ...
```
