# <GetMethods>d__7::MoveNext_0

- ea: `0xe6530`
- end: `0xe6b84`
- name: `<GetMethods>d__7::MoveNext_0`
- size: `1620`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callees

- `0x211b0`
- `0xe6530`
- `0xe6bb0`
- `0xe6c10`

## string_xrefs

- `0xe69da`: `Uninstall`
- `0xe6a0e`: `Uninstall`
- `0xe674f`: `Install`
- `0xe6783`: `Install`
- `0xe6828`: `Remove`
- `0xe685c`: `Remove`

## pseudocode

```c

```

## disassembly

```asm
0xe6530  ldarg.0
0xe6531  ldfld    int32 <GetMethods>d__7::<>1__state
0xe6536  stloc.1
0xe6537  ldloc.1
0xe6538  switch   loc_E6566, loc_E6B77, loc_E65D0, loc_E6736, loc_E680F, loc_E68E8, loc_E69C1, loc_E6A9A, loc_E6B70
0xe6561  br       loc_E6B77
0xe6566  ldarg.0
0xe6567  ldc.i4.m1
0xe6568  stfld    int32 <GetMethods>d__7::<>1__state
0xe656d  ldarg.0
0xe656e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__7::proxyContext
0xe6573  brtrue.s loc_E6580
0xe6575  ldstr    aProxycontext// "proxyContext"
0xe657a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe657f  throw
0xe6580  ldarg.0
0xe6581  ldarg.0
0xe6582  ldfld    class Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub <GetMethods>d__7::<>4__this
0xe6587  ldarg.0
0xe6588  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__7::proxyContext
0xe658d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::<>n__FabricatedMethodc(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0xe6592  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0xe6597  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__7::<>7__wrapa
0xe659c  ldarg.0
0xe659d  ldc.i4.1
0xe659e  stfld    int32 <GetMethods>d__7::<>1__state
0xe65a3  br.s     loc_E65D7
0xe65a5  ldarg.0
0xe65a6  ldarg.0
0xe65a7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__7::<>7__wrapa
0xe65ac  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0xe65b1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<itemBase>5__8
0xe65b6  ldarg.0
0xe65b7  ldarg.0
0xe65b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<itemBase>5__8
0xe65bd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>2__current
0xe65c2  ldarg.0
0xe65c3  ldc.i4.2
0xe65c4  stfld    int32 <GetMethods>d__7::<>1__state
0xe65c9  ldc.i4.1
0xe65ca  stloc.0
0xe65cb  leave    loc_E6B82
0xe65d0  ldarg.0
0xe65d1  ldc.i4.1
0xe65d2  stfld    int32 <GetMethods>d__7::<>1__state
0xe65d7  ldarg.0
0xe65d8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__7::<>7__wrapa
0xe65dd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe65e2  brtrue.s loc_E65A5
0xe65e4  ldarg.0
0xe65e5  call     instance void <GetMethods>d__7::<>m__Finallyb()
0xe65ea  ldarg.0
0xe65eb  ldarg.0
0xe65ec  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xe65f1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0xe65f6  ldarg.0
0xe65f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0xe65fc  ldstr    aDeploy// "Deploy"
0xe6601  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xe6606  ldarg.0
0xe6607  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0xe660c  ldc.i4.0
0xe660d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xe6612  ldarg.0
0xe6613  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0xe6618  ldc.i4.0
0xe6619  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xe661e  ldarg.0
0xe661f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0xe6624  ldc.i4.8
0xe6625  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xe662a  ldarg.0
0xe662b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0xe6630  ldstr    aDeploy// "Deploy"
0xe6635  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xe663a  ldarg.0
0xe663b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0xe6640  ldc.i4.0
0xe6641  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xe6646  ldarg.0
0xe6647  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0xe664c  ldtoken  [mscorlib]System.Void
0xe6651  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe6656  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xe665b  ldarg.0
0xe665c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0xe6661  ldc.i4.0
0xe6662  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe6667  ldarg.0
0xe6668  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0xe666d  ldc.i4.0
0xe666e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xe6673  ldarg.0
0xe6674  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0xe6679  ldc.i4.0
0xe667a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0xe667f  ldarg.0
0xe6680  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0xe6685  ldc.i4.0
0xe6686  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xe668b  ldarg.0
0xe668c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0xe6691  ldc.i4.1
0xe6692  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0xe6697  ldarg.0
0xe6698  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0xe669d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0xe66a2  ldarg.0
0xe66a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0xe66a8  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xe66ad  ldarg.0
0xe66ae  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xe66b3  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal1
0xe66b8  ldarg.0
0xe66b9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal1
0xe66be  ldstr    aSkipfeaturedep// "skipFeatureDeployment"
0xe66c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xe66c8  ldarg.0
0xe66c9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal1
0xe66ce  ldc.i4.0
0xe66cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xe66d4  ldarg.0
0xe66d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal1
0xe66da  ldtoken  [mscorlib]System.Boolean
0xe66df  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe66e4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xe66e9  ldarg.0
0xe66ea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal1
0xe66ef  ldc.i4.1
0xe66f0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe66f5  ldarg.0
0xe66f6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal1
0xe66fb  ldc.i4.0
0xe66fc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0xe6701  ldarg.0
0xe6702  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal1
0xe6707  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xe670c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0xe6711  ldarg.0
0xe6712  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal1
0xe6717  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0xe671c  ldarg.0
0xe671d  ldarg.0
0xe671e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0xe6723  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>2__current
0xe6728  ldarg.0
0xe6729  ldc.i4.3
0xe672a  stfld    int32 <GetMethods>d__7::<>1__state
0xe672f  ldc.i4.1
0xe6730  stloc.0
0xe6731  leave    loc_E6B82
0xe6736  ldarg.0
0xe6737  ldc.i4.m1
0xe6738  stfld    int32 <GetMethods>d__7::<>1__state
0xe673d  ldarg.0
0xe673e  ldarg.0
0xe673f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xe6744  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0xe6749  ldarg.0
0xe674a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0xe674f  ldstr    aInstall// "Install"
0xe6754  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xe6759  ldarg.0
0xe675a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0xe675f  ldc.i4.0
0xe6760  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xe6765  ldarg.0
0xe6766  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0xe676b  ldc.i4.0
0xe676c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xe6771  ldarg.0
0xe6772  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0xe6777  ldc.i4.8
0xe6778  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xe677d  ldarg.0
0xe677e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0xe6783  ldstr    aInstall// "Install"
0xe6788  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xe678d  ldarg.0
0xe678e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0xe6793  ldc.i4.0
0xe6794  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xe6799  ldarg.0
0xe679a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0xe679f  ldtoken  [mscorlib]System.Void
0xe67a4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe67a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xe67ae  ldarg.0
0xe67af  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0xe67b4  ldc.i4.0
0xe67b5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe67ba  ldarg.0
0xe67bb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0xe67c0  ldc.i4.0
0xe67c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xe67c6  ldarg.0
0xe67c7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0xe67cc  ldc.i4.0
0xe67cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0xe67d2  ldarg.0
0xe67d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0xe67d8  ldc.i4.0
0xe67d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xe67de  ldarg.0
0xe67df  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0xe67e4  ldc.i4.1
0xe67e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0xe67ea  ldarg.0
0xe67eb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0xe67f0  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0xe67f5  ldarg.0
0xe67f6  ldarg.0
0xe67f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0xe67fc  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>2__current
0xe6801  ldarg.0
0xe6802  ldc.i4.4
0xe6803  stfld    int32 <GetMethods>d__7::<>1__state
0xe6808  ldc.i4.1
0xe6809  stloc.0
0xe680a  leave    loc_E6B82
0xe680f  ldarg.0
0xe6810  ldc.i4.m1
0xe6811  stfld    int32 <GetMethods>d__7::<>1__state
0xe6816  ldarg.0
0xe6817  ldarg.0
0xe6818  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xe681d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal3
0xe6822  ldarg.0
0xe6823  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal3
0xe6828  ldstr    aRemove// "Remove"
0xe682d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xe6832  ldarg.0
0xe6833  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal3
0xe6838  ldc.i4.0
0xe6839  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xe683e  ldarg.0
0xe683f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal3
0xe6844  ldc.i4.0
0xe6845  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xe684a  ldarg.0
0xe684b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal3
0xe6850  ldc.i4.8
0xe6851  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xe6856  ldarg.0
0xe6857  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal3
0xe685c  ldstr    aRemove// "Remove"
0xe6861  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xe6866  ldarg.0
0xe6867  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal3
0xe686c  ldc.i4.0
0xe686d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xe6872  ldarg.0
0xe6873  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal3
0xe6878  ldtoken  [mscorlib]System.Void
0xe687d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe6882  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xe6887  ldarg.0
0xe6888  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal3
0xe688d  ldc.i4.0
0xe688e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe6893  ldarg.0
0xe6894  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal3
0xe6899  ldc.i4.0
0xe689a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xe689f  ldarg.0
0xe68a0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal3
0xe68a5  ldc.i4.0
0xe68a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0xe68ab  ldarg.0
0xe68ac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal3
0xe68b1  ldc.i4.0
0xe68b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xe68b7  ldarg.0
0xe68b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal3
0xe68bd  ldc.i4.1
0xe68be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0xe68c3  ldarg.0
0xe68c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal3
0xe68c9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0xe68ce  ldarg.0
0xe68cf  ldarg.0
0xe68d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0xe68d5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>2__current
0xe68da  ldarg.0
0xe68db  ldc.i4.5
0xe68dc  stfld    int32 <GetMethods>d__7::<>1__state
0xe68e1  ldc.i4.1
0xe68e2  stloc.0
0xe68e3  leave    loc_E6B82
0xe68e8  ldarg.0
0xe68e9  ldc.i4.m1
0xe68ea  stfld    int32 <GetMethods>d__7::<>1__state
0xe68ef  ldarg.0
0xe68f0  ldarg.0
0xe68f1  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xe68f6  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal4
0xe68fb  ldarg.0
0xe68fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal4
0xe6901  ldstr    aRetract// "Retract"
0xe6906  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
  ... truncated ...
```
