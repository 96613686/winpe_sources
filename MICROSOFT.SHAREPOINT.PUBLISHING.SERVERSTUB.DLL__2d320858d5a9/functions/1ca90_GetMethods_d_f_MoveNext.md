# <GetMethods>d__f::MoveNext

- ea: `0x1ca90`
- end: `0x1d518`
- name: `<GetMethods>d__f::MoveNext`
- size: `2696`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x85f0`
- `0x1ca90`
- `0x1d540`
- `0x1d5a0`

## pseudocode

```c

```

## disassembly

```asm
0x1ca90  ldarg.0
0x1ca91  ldfld    int32 <GetMethods>d__f::<>1__state
0x1ca96  stloc.1
0x1ca97  ldloc.1
0x1ca98  switch   loc_1CACA, loc_1D50B, loc_1CB34, loc_1CC9A, loc_1CD73, loc_1CEC6, loc_1D093, loc_1D2DA, loc_1D3B3, loc_1D504
0x1cac5  br       loc_1D50B
0x1caca  ldarg.0
0x1cacb  ldc.i4.m1
0x1cacc  stfld    int32 <GetMethods>d__f::<>1__state
0x1cad1  ldarg.0
0x1cad2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__f::proxyContext
0x1cad7  brtrue.s loc_1CAE4
0x1cad9  ldstr    aProxycontext// "proxyContext"
0x1cade  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1cae3  throw
0x1cae4  ldarg.0
0x1cae5  ldarg.0
0x1cae6  ldfld    class Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetServerStub <GetMethods>d__f::<>4__this
0x1caeb  ldarg.0
0x1caec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__f::proxyContext
0x1caf1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetServerStub::<>n__FabricatedMethod14(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x1caf6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x1cafb  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__f::<>7__wrap12
0x1cb00  ldarg.0
0x1cb01  ldc.i4.1
0x1cb02  stfld    int32 <GetMethods>d__f::<>1__state
0x1cb07  br.s     loc_1CB3B
0x1cb09  ldarg.0
0x1cb0a  ldarg.0
0x1cb0b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__f::<>7__wrap12
0x1cb10  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x1cb15  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<itemBase>5__10
0x1cb1a  ldarg.0
0x1cb1b  ldarg.0
0x1cb1c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<itemBase>5__10
0x1cb21  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>2__current
0x1cb26  ldarg.0
0x1cb27  ldc.i4.2
0x1cb28  stfld    int32 <GetMethods>d__f::<>1__state
0x1cb2d  ldc.i4.1
0x1cb2e  stloc.0
0x1cb2f  leave    loc_1D516
0x1cb34  ldarg.0
0x1cb35  ldc.i4.1
0x1cb36  stfld    int32 <GetMethods>d__f::<>1__state
0x1cb3b  ldarg.0
0x1cb3c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__f::<>7__wrap12
0x1cb41  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1cb46  brtrue.s loc_1CB09
0x1cb48  ldarg.0
0x1cb49  call     instance void <GetMethods>d__f::<>m__Finally13()
0x1cb4e  ldarg.0
0x1cb4f  ldarg.0
0x1cb50  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1cb55  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1cb5a  ldarg.0
0x1cb5b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1cb60  ldstr    aFindtermforurl// "FindTermForUrl"
0x1cb65  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1cb6a  ldarg.0
0x1cb6b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1cb70  ldc.i4.0
0x1cb71  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1cb76  ldarg.0
0x1cb77  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1cb7c  ldc.i4.0
0x1cb7d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1cb82  ldarg.0
0x1cb83  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1cb88  ldc.i4.7
0x1cb89  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1cb8e  ldarg.0
0x1cb8f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1cb94  ldstr    aFindtermforurl// "FindTermForUrl"
0x1cb99  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1cb9e  ldarg.0
0x1cb9f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1cba4  ldc.i4.0
0x1cba5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1cbaa  ldarg.0
0x1cbab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1cbb0  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm
0x1cbb5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1cbba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1cbbf  ldarg.0
0x1cbc0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1cbc5  ldc.i4.4
0x1cbc6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1cbcb  ldarg.0
0x1cbcc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1cbd1  ldc.i4.0
0x1cbd2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1cbd7  ldarg.0
0x1cbd8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1cbdd  ldc.i4.0
0x1cbde  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1cbe3  ldarg.0
0x1cbe4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1cbe9  ldc.i4.0
0x1cbea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1cbef  ldarg.0
0x1cbf0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1cbf5  ldc.i4.0
0x1cbf6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1cbfb  ldarg.0
0x1cbfc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1cc01  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x1cc06  ldarg.0
0x1cc07  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x1cc0c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1cc11  ldarg.0
0x1cc12  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1cc17  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x1cc1c  ldarg.0
0x1cc1d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x1cc22  ldstr    aUrl_0// "url"
0x1cc27  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1cc2c  ldarg.0
0x1cc2d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x1cc32  ldc.i4.0
0x1cc33  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1cc38  ldarg.0
0x1cc39  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x1cc3e  ldtoken  [mscorlib]System.String
0x1cc43  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1cc48  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1cc4d  ldarg.0
0x1cc4e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x1cc53  ldc.i4.1
0x1cc54  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1cc59  ldarg.0
0x1cc5a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x1cc5f  ldc.i4.0
0x1cc60  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1cc65  ldarg.0
0x1cc66  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x1cc6b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1cc70  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1cc75  ldarg.0
0x1cc76  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x1cc7b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1cc80  ldarg.0
0x1cc81  ldarg.0
0x1cc82  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x1cc87  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>2__current
0x1cc8c  ldarg.0
0x1cc8d  ldc.i4.3
0x1cc8e  stfld    int32 <GetMethods>d__f::<>1__state
0x1cc93  ldc.i4.1
0x1cc94  stloc.0
0x1cc95  leave    loc_1D516
0x1cc9a  ldarg.0
0x1cc9b  ldc.i4.m1
0x1cc9c  stfld    int32 <GetMethods>d__f::<>1__state
0x1cca1  ldarg.0
0x1cca2  ldarg.0
0x1cca3  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1cca8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1ccad  ldarg.0
0x1ccae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1ccb3  ldstr    aGetallterms// "GetAllTerms"
0x1ccb8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1ccbd  ldarg.0
0x1ccbe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1ccc3  ldc.i4.0
0x1ccc4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1ccc9  ldarg.0
0x1ccca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1cccf  ldc.i4.0
0x1ccd0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1ccd5  ldarg.0
0x1ccd6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1ccdb  ldc.i4.7
0x1ccdc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1cce1  ldarg.0
0x1cce2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1cce7  ldstr    aGetallterms// "GetAllTerms"
0x1ccec  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1ccf1  ldarg.0
0x1ccf2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1ccf7  ldc.i4.0
0x1ccf8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1ccfd  ldarg.0
0x1ccfe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1cd03  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermCollectionCsom
0x1cd08  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1cd0d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1cd12  ldarg.0
0x1cd13  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1cd18  ldc.i4.5
0x1cd19  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1cd1e  ldarg.0
0x1cd1f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1cd24  ldc.i4.0
0x1cd25  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1cd2a  ldarg.0
0x1cd2b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1cd30  ldc.i4.0
0x1cd31  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1cd36  ldarg.0
0x1cd37  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1cd3c  ldc.i4.0
0x1cd3d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1cd42  ldarg.0
0x1cd43  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1cd48  ldc.i4.0
0x1cd49  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1cd4e  ldarg.0
0x1cd4f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1cd54  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x1cd59  ldarg.0
0x1cd5a  ldarg.0
0x1cd5b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x1cd60  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>2__current
0x1cd65  ldarg.0
0x1cd66  ldc.i4.4
0x1cd67  stfld    int32 <GetMethods>d__f::<>1__state
0x1cd6c  ldc.i4.1
0x1cd6d  stloc.0
0x1cd6e  leave    loc_1D516
0x1cd73  ldarg.0
0x1cd74  ldc.i4.m1
0x1cd75  stfld    int32 <GetMethods>d__f::<>1__state
0x1cd7a  ldarg.0
0x1cd7b  ldarg.0
0x1cd7c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1cd81  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal3
0x1cd86  ldarg.0
0x1cd87  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal3
0x1cd8c  ldstr    aGetaseditable// "GetAsEditable"
0x1cd91  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1cd96  ldarg.0
0x1cd97  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal3
0x1cd9c  ldc.i4.0
0x1cd9d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1cda2  ldarg.0
0x1cda3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal3
0x1cda8  ldc.i4.0
0x1cda9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1cdae  ldarg.0
0x1cdaf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal3
0x1cdb4  ldc.i4.7
0x1cdb5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1cdba  ldarg.0
0x1cdbb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal3
0x1cdc0  ldstr    aGetaseditable// "GetAsEditable"
0x1cdc5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1cdca  ldarg.0
0x1cdcb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal3
0x1cdd0  ldc.i4.0
0x1cdd1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1cdd6  ldarg.0
0x1cdd7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal3
0x1cddc  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet
0x1cde1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1cde6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1cdeb  ldarg.0
0x1cdec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal3
0x1cdf1  ldc.i4.4
0x1cdf2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1cdf7  ldarg.0
0x1cdf8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal3
0x1cdfd  ldc.i4.0
0x1cdfe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1ce03  ldarg.0
0x1ce04  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal3
0x1ce09  ldc.i4.0
0x1ce0a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1ce0f  ldarg.0
0x1ce10  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal3
0x1ce15  ldc.i4.0
0x1ce16  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1ce1b  ldarg.0
0x1ce1c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal3
0x1ce21  ldc.i4.0
0x1ce22  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1ce27  ldarg.0
0x1ce28  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal3
0x1ce2d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x1ce32  ldarg.0
0x1ce33  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x1ce38  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1ce3d  ldarg.0
0x1ce3e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1ce43  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal4
0x1ce48  ldarg.0
0x1ce49  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal4
0x1ce4e  ldstr    aTaxonomysessio// "taxonomySession"
0x1ce53  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1ce58  ldarg.0
0x1ce59  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal4
0x1ce5e  ldc.i4.0
0x1ce5f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1ce64  ldarg.0
0x1ce65  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal4
0x1ce6a  ldtoken  [Microsoft.SharePoint.Taxonomy]Microsoft.SharePoint.Taxonomy.TaxonomySession
0x1ce6f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ce74  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1ce79  ldarg.0
0x1ce7a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal4
  ... truncated ...
```
