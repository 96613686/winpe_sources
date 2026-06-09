# <GetMethods>d__10::MoveNext_3

- ea: `0x16e520`
- end: `0x16ef6f`
- name: `<GetMethods>d__10::MoveNext_3`
- size: `2639`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x855d0`
- `0x16e520`
- `0x16ef90`
- `0x16eff0`

## string_xrefs

- `0x16ea50`: `folderPath`
- `0x16edf2`: `folderPath`
- `0x16ed2c`: `PromoteToTeamChannelByPath`
- `0x16e98a`: `DemoteTeamChannelByPath`
- `0x16e6ae`: `parentFolderPath`
- `0x16e728`: `newFolderPath`

## pseudocode

```c

```

## disassembly

```asm
0x16e520  ldarg.0
0x16e521  ldfld    int32 <GetMethods>d__10::<>1__state
0x16e526  stloc.1
0x16e527  ldloc.1
0x16e528  switch   loc_16E552, loc_16EF62, loc_16E5BC, loc_16E81A, loc_16E971, loc_16EAC8, loc_16ED13, loc_16EF5B
0x16e54d  br       loc_16EF62
0x16e552  ldarg.0
0x16e553  ldc.i4.m1
0x16e554  stfld    int32 <GetMethods>d__10::<>1__state
0x16e559  ldarg.0
0x16e55a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__10::proxyContext
0x16e55f  brtrue.s loc_16E56C
0x16e561  ldstr    aProxycontext// "proxyContext"
0x16e566  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x16e56b  throw
0x16e56c  ldarg.0
0x16e56d  ldarg.0
0x16e56e  ldfld    class Microsoft.SharePoint.ServerStub.SPTeamChannelManagerServerStub <GetMethods>d__10::<>4__this
0x16e573  ldarg.0
0x16e574  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__10::proxyContext
0x16e579  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPTeamChannelManagerServerStub::<>n__FabricatedMethod15(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x16e57e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x16e583  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__10::<>7__wrap13
0x16e588  ldarg.0
0x16e589  ldc.i4.1
0x16e58a  stfld    int32 <GetMethods>d__10::<>1__state
0x16e58f  br.s     loc_16E5C3
0x16e591  ldarg.0
0x16e592  ldarg.0
0x16e593  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__10::<>7__wrap13
0x16e598  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x16e59d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<itemBase>5__11
0x16e5a2  ldarg.0
0x16e5a3  ldarg.0
0x16e5a4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<itemBase>5__11
0x16e5a9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>2__current
0x16e5ae  ldarg.0
0x16e5af  ldc.i4.2
0x16e5b0  stfld    int32 <GetMethods>d__10::<>1__state
0x16e5b5  ldc.i4.1
0x16e5b6  stloc.0
0x16e5b7  leave    loc_16EF6D
0x16e5bc  ldarg.0
0x16e5bd  ldc.i4.1
0x16e5be  stfld    int32 <GetMethods>d__10::<>1__state
0x16e5c3  ldarg.0
0x16e5c4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__10::<>7__wrap13
0x16e5c9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x16e5ce  brtrue.s loc_16E591
0x16e5d0  ldarg.0
0x16e5d1  call     instance void <GetMethods>d__10::<>m__Finally14()
0x16e5d6  ldarg.0
0x16e5d7  ldarg.0
0x16e5d8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x16e5dd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x16e5e2  ldarg.0
0x16e5e3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x16e5e8  ldstr    aAddteamchannel// "AddTeamChannel"
0x16e5ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x16e5f2  ldarg.0
0x16e5f3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x16e5f8  ldc.i4.1
0x16e5f9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x16e5fe  ldarg.0
0x16e5ff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x16e604  ldc.i4.0
0x16e605  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x16e60a  ldarg.0
0x16e60b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x16e610  ldc.i4   0xFFFFFFF
0x16e615  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x16e61a  ldarg.0
0x16e61b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x16e620  ldstr    aAddteamchannel// "AddTeamChannel"
0x16e625  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x16e62a  ldarg.0
0x16e62b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x16e630  ldc.i4.0
0x16e631  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x16e636  ldarg.0
0x16e637  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x16e63c  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder
0x16e641  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16e646  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x16e64b  ldarg.0
0x16e64c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x16e651  ldc.i4.4
0x16e652  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x16e657  ldarg.0
0x16e658  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x16e65d  ldc.i4.0
0x16e65e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x16e663  ldarg.0
0x16e664  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x16e669  ldc.i4.0
0x16e66a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x16e66f  ldarg.0
0x16e670  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x16e675  ldc.i4.0
0x16e676  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x16e67b  ldarg.0
0x16e67c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x16e681  ldc.i4.1
0x16e682  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x16e687  ldarg.0
0x16e688  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x16e68d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x16e692  ldarg.0
0x16e693  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x16e698  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x16e69d  ldarg.0
0x16e69e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x16e6a3  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0x16e6a8  ldarg.0
0x16e6a9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0x16e6ae  ldstr    aParentfolderpa// "parentFolderPath"
0x16e6b3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x16e6b8  ldarg.0
0x16e6b9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0x16e6be  ldc.i4.1
0x16e6bf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x16e6c4  ldarg.0
0x16e6c5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0x16e6ca  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath
0x16e6cf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16e6d4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x16e6d9  ldarg.0
0x16e6da  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0x16e6df  ldc.i4.2
0x16e6e0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x16e6e5  ldarg.0
0x16e6e6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0x16e6eb  ldc.i4.0
0x16e6ec  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x16e6f1  ldarg.0
0x16e6f2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0x16e6f7  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x16e6fc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x16e701  ldarg.0
0x16e702  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0x16e707  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x16e70c  ldarg.0
0x16e70d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x16e712  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x16e717  ldarg.0
0x16e718  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x16e71d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0x16e722  ldarg.0
0x16e723  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0x16e728  ldstr    aNewfolderpath// "newFolderPath"
0x16e72d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x16e732  ldarg.0
0x16e733  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0x16e738  ldc.i4.1
0x16e739  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x16e73e  ldarg.0
0x16e73f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0x16e744  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath
0x16e749  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16e74e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x16e753  ldarg.0
0x16e754  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0x16e759  ldc.i4.2
0x16e75a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x16e75f  ldarg.0
0x16e760  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0x16e765  ldc.i4.0
0x16e766  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x16e76b  ldarg.0
0x16e76c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0x16e771  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x16e776  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x16e77b  ldarg.0
0x16e77c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0x16e781  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x16e786  ldarg.0
0x16e787  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x16e78c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x16e791  ldarg.0
0x16e792  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x16e797  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal3
0x16e79c  ldarg.0
0x16e79d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal3
0x16e7a2  ldstr    aTeamchannelurl// "teamChannelUrl"
0x16e7a7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x16e7ac  ldarg.0
0x16e7ad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal3
0x16e7b2  ldc.i4.0
0x16e7b3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x16e7b8  ldarg.0
0x16e7b9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal3
0x16e7be  ldtoken  [mscorlib]System.String
0x16e7c3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16e7c8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x16e7cd  ldarg.0
0x16e7ce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal3
0x16e7d3  ldc.i4.1
0x16e7d4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x16e7d9  ldarg.0
0x16e7da  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal3
0x16e7df  ldc.i4.0
0x16e7e0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x16e7e5  ldarg.0
0x16e7e6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal3
0x16e7eb  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x16e7f0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x16e7f5  ldarg.0
0x16e7f6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal3
0x16e7fb  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x16e800  ldarg.0
0x16e801  ldarg.0
0x16e802  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x16e807  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>2__current
0x16e80c  ldarg.0
0x16e80d  ldc.i4.3
0x16e80e  stfld    int32 <GetMethods>d__10::<>1__state
0x16e813  ldc.i4.1
0x16e814  stloc.0
0x16e815  leave    loc_16EF6D
0x16e81a  ldarg.0
0x16e81b  ldc.i4.m1
0x16e81c  stfld    int32 <GetMethods>d__10::<>1__state
0x16e821  ldarg.0
0x16e822  ldarg.0
0x16e823  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x16e828  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x16e82d  ldarg.0
0x16e82e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x16e833  ldstr    aDemoteteamchan_0// "DemoteTeamChannelById"
0x16e838  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x16e83d  ldarg.0
0x16e83e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x16e843  ldc.i4.1
0x16e844  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x16e849  ldarg.0
0x16e84a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x16e84f  ldc.i4.0
0x16e850  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x16e855  ldarg.0
0x16e856  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x16e85b  ldc.i4   0xFFFFFFF
0x16e860  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x16e865  ldarg.0
0x16e866  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x16e86b  ldstr    aDemoteteamchan_1// "DemoteTeamChannel"
0x16e870  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x16e875  ldarg.0
0x16e876  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x16e87b  ldc.i4.0
0x16e87c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x16e881  ldarg.0
0x16e882  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x16e887  ldtoken  [mscorlib]System.Boolean
0x16e88c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16e891  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x16e896  ldarg.0
0x16e897  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x16e89c  ldc.i4.1
0x16e89d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x16e8a2  ldarg.0
0x16e8a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x16e8a8  ldc.i4.0
0x16e8a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x16e8ae  ldarg.0
0x16e8af  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x16e8b4  ldc.i4.0
0x16e8b5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x16e8ba  ldarg.0
0x16e8bb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x16e8c0  ldc.i4.0
0x16e8c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x16e8c6  ldarg.0
0x16e8c7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x16e8cc  ldc.i4.1
0x16e8cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x16e8d2  ldarg.0
0x16e8d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x16e8d8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x16e8dd  ldarg.0
0x16e8de  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x16e8e3  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x16e8e8  ldarg.0
0x16e8e9  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x16e8ee  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal5
0x16e8f3  ldarg.0
0x16e8f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal5
0x16e8f9  ldstr    aFolderid// "folderId"
0x16e8fe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x16e903  ldarg.0
0x16e904  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal5
0x16e909  ldc.i4.1
0x16e90a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x16e90f  ldarg.0
0x16e910  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal5
0x16e915  ldtoken  [mscorlib]System.Guid
0x16e91a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16e91f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x16e924  ldarg.0
0x16e925  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal5
0x16e92a  ldc.i4.1
  ... truncated ...
```
