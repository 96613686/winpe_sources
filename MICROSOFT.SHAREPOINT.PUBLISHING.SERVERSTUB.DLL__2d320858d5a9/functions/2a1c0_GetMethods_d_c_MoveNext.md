# <GetMethods>d__c::MoveNext

- ea: `0x2a1c0`
- end: `0x2aa76`
- name: `<GetMethods>d__c::MoveNext`
- size: `2230`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x11e90`
- `0x2a1c0`
- `0x2aaa0`
- `0x2ab00`

## string_xrefs

- `0x2a3df`: `DeleteSettings`
- `0x2a413`: `DeleteSettings`
- `0x2a532`: `GetPlugin`
- `0x2a566`: `GetPlugin`
- `0x2a7d8`: `SetPlugin`
- `0x2a80c`: `SetPlugin`
- `0x2a28c`: `DeletePlugin`
- `0x2a2c0`: `DeletePlugin`
- `0x2a34e`: `pluginName`
- `0x2a5f4`: `pluginName`
- `0x2a89a`: `plugin`

## pseudocode

```c

```

## disassembly

```asm
0x2a1c0  ldarg.0
0x2a1c1  ldfld    int32 <GetMethods>d__c::<>1__state
0x2a1c6  stloc.1
0x2a1c7  ldloc.1
0x2a1c8  switch   loc_2A1F6, loc_2AA69, loc_2A260, loc_2A3C6, loc_2A519, loc_2A66C, loc_2A7BF, loc_2A912, loc_2AA62
0x2a1f1  br       loc_2AA69
0x2a1f6  ldarg.0
0x2a1f7  ldc.i4.m1
0x2a1f8  stfld    int32 <GetMethods>d__c::<>1__state
0x2a1fd  ldarg.0
0x2a1fe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__c::proxyContext
0x2a203  brtrue.s loc_2A210
0x2a205  ldstr    aProxycontext// "proxyContext"
0x2a20a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2a20f  throw
0x2a210  ldarg.0
0x2a211  ldarg.0
0x2a212  ldfld    class Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub <GetMethods>d__c::<>4__this
0x2a217  ldarg.0
0x2a218  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__c::proxyContext
0x2a21d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub::<>n__FabricatedMethod11(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x2a222  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x2a227  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__c::<>7__wrapf
0x2a22c  ldarg.0
0x2a22d  ldc.i4.1
0x2a22e  stfld    int32 <GetMethods>d__c::<>1__state
0x2a233  br.s     loc_2A267
0x2a235  ldarg.0
0x2a236  ldarg.0
0x2a237  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__c::<>7__wrapf
0x2a23c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x2a241  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<itemBase>5__d
0x2a246  ldarg.0
0x2a247  ldarg.0
0x2a248  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<itemBase>5__d
0x2a24d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>2__current
0x2a252  ldarg.0
0x2a253  ldc.i4.2
0x2a254  stfld    int32 <GetMethods>d__c::<>1__state
0x2a259  ldc.i4.1
0x2a25a  stloc.0
0x2a25b  leave    loc_2AA74
0x2a260  ldarg.0
0x2a261  ldc.i4.1
0x2a262  stfld    int32 <GetMethods>d__c::<>1__state
0x2a267  ldarg.0
0x2a268  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__c::<>7__wrapf
0x2a26d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2a272  brtrue.s loc_2A235
0x2a274  ldarg.0
0x2a275  call     instance void <GetMethods>d__c::<>m__Finally10()
0x2a27a  ldarg.0
0x2a27b  ldarg.0
0x2a27c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x2a281  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x2a286  ldarg.0
0x2a287  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x2a28c  ldstr    aDeleteplugin// "DeletePlugin"
0x2a291  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x2a296  ldarg.0
0x2a297  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x2a29c  ldc.i4.1
0x2a29d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x2a2a2  ldarg.0
0x2a2a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x2a2a8  ldc.i4.0
0x2a2a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x2a2ae  ldarg.0
0x2a2af  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x2a2b4  ldc.i4.7
0x2a2b5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x2a2ba  ldarg.0
0x2a2bb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x2a2c0  ldstr    aDeleteplugin// "DeletePlugin"
0x2a2c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x2a2ca  ldarg.0
0x2a2cb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x2a2d0  ldc.i4.0
0x2a2d1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x2a2d6  ldarg.0
0x2a2d7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x2a2dc  ldtoken  [mscorlib]System.Void
0x2a2e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a2e6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x2a2eb  ldarg.0
0x2a2ec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x2a2f1  ldc.i4.0
0x2a2f2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2a2f7  ldarg.0
0x2a2f8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x2a2fd  ldc.i4.0
0x2a2fe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x2a303  ldarg.0
0x2a304  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x2a309  ldc.i4.0
0x2a30a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x2a30f  ldarg.0
0x2a310  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x2a315  ldc.i4.0
0x2a316  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2a31b  ldarg.0
0x2a31c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x2a321  ldc.i4.0
0x2a322  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x2a327  ldarg.0
0x2a328  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x2a32d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<item>5__e
0x2a332  ldarg.0
0x2a333  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<item>5__e
0x2a338  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x2a33d  ldarg.0
0x2a33e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x2a343  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal1
0x2a348  ldarg.0
0x2a349  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal1
0x2a34e  ldstr    aPluginname// "pluginName"
0x2a353  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x2a358  ldarg.0
0x2a359  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal1
0x2a35e  ldc.i4.0
0x2a35f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x2a364  ldarg.0
0x2a365  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal1
0x2a36a  ldtoken  [mscorlib]System.String
0x2a36f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a374  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x2a379  ldarg.0
0x2a37a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal1
0x2a37f  ldc.i4.1
0x2a380  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2a385  ldarg.0
0x2a386  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal1
0x2a38b  ldc.i4.0
0x2a38c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x2a391  ldarg.0
0x2a392  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal1
0x2a397  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x2a39c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x2a3a1  ldarg.0
0x2a3a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal1
0x2a3a7  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x2a3ac  ldarg.0
0x2a3ad  ldarg.0
0x2a3ae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<item>5__e
0x2a3b3  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>2__current
0x2a3b8  ldarg.0
0x2a3b9  ldc.i4.3
0x2a3ba  stfld    int32 <GetMethods>d__c::<>1__state
0x2a3bf  ldc.i4.1
0x2a3c0  stloc.0
0x2a3c1  leave    loc_2AA74
0x2a3c6  ldarg.0
0x2a3c7  ldc.i4.m1
0x2a3c8  stfld    int32 <GetMethods>d__c::<>1__state
0x2a3cd  ldarg.0
0x2a3ce  ldarg.0
0x2a3cf  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x2a3d4  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal2
0x2a3d9  ldarg.0
0x2a3da  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal2
0x2a3df  ldstr    aDeletesettings// "DeleteSettings"
0x2a3e4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x2a3e9  ldarg.0
0x2a3ea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal2
0x2a3ef  ldc.i4.1
0x2a3f0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x2a3f5  ldarg.0
0x2a3f6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal2
0x2a3fb  ldc.i4.0
0x2a3fc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x2a401  ldarg.0
0x2a402  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal2
0x2a407  ldc.i4.7
0x2a408  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x2a40d  ldarg.0
0x2a40e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal2
0x2a413  ldstr    aDeletesettings// "DeleteSettings"
0x2a418  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x2a41d  ldarg.0
0x2a41e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal2
0x2a423  ldc.i4.0
0x2a424  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x2a429  ldarg.0
0x2a42a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal2
0x2a42f  ldtoken  [mscorlib]System.Void
0x2a434  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a439  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x2a43e  ldarg.0
0x2a43f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal2
0x2a444  ldc.i4.0
0x2a445  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2a44a  ldarg.0
0x2a44b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal2
0x2a450  ldc.i4.0
0x2a451  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x2a456  ldarg.0
0x2a457  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal2
0x2a45c  ldc.i4.0
0x2a45d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x2a462  ldarg.0
0x2a463  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal2
0x2a468  ldc.i4.0
0x2a469  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2a46e  ldarg.0
0x2a46f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal2
0x2a474  ldc.i4.0
0x2a475  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x2a47a  ldarg.0
0x2a47b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal2
0x2a480  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<item>5__e
0x2a485  ldarg.0
0x2a486  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<item>5__e
0x2a48b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x2a490  ldarg.0
0x2a491  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x2a496  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal3
0x2a49b  ldarg.0
0x2a49c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal3
0x2a4a1  ldstr    aAddinid// "addinId"
0x2a4a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x2a4ab  ldarg.0
0x2a4ac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal3
0x2a4b1  ldc.i4.0
0x2a4b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x2a4b7  ldarg.0
0x2a4b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal3
0x2a4bd  ldtoken  [mscorlib]System.Guid
0x2a4c2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a4c7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x2a4cc  ldarg.0
0x2a4cd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal3
0x2a4d2  ldc.i4.1
0x2a4d3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2a4d8  ldarg.0
0x2a4d9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal3
0x2a4de  ldc.i4.0
0x2a4df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x2a4e4  ldarg.0
0x2a4e5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal3
0x2a4ea  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x2a4ef  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x2a4f4  ldarg.0
0x2a4f5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal3
0x2a4fa  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x2a4ff  ldarg.0
0x2a500  ldarg.0
0x2a501  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<item>5__e
0x2a506  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>2__current
0x2a50b  ldarg.0
0x2a50c  ldc.i4.4
0x2a50d  stfld    int32 <GetMethods>d__c::<>1__state
0x2a512  ldc.i4.1
0x2a513  stloc.0
0x2a514  leave    loc_2AA74
0x2a519  ldarg.0
0x2a51a  ldc.i4.m1
0x2a51b  stfld    int32 <GetMethods>d__c::<>1__state
0x2a520  ldarg.0
0x2a521  ldarg.0
0x2a522  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x2a527  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x2a52c  ldarg.0
0x2a52d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x2a532  ldstr    aGetplugin// "GetPlugin"
0x2a537  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x2a53c  ldarg.0
0x2a53d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x2a542  ldc.i4.1
0x2a543  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x2a548  ldarg.0
0x2a549  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x2a54e  ldc.i4.0
0x2a54f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x2a554  ldarg.0
0x2a555  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x2a55a  ldc.i4.7
0x2a55b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x2a560  ldarg.0
0x2a561  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x2a566  ldstr    aGetplugin// "GetPlugin"
0x2a56b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x2a570  ldarg.0
0x2a571  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x2a576  ldc.i4.0
0x2a577  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x2a57c  ldarg.0
0x2a57d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x2a582  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin
0x2a587  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a58c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x2a591  ldarg.0
0x2a592  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x2a597  ldc.i4.4
0x2a598  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2a59d  ldarg.0
0x2a59e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x2a5a3  ldc.i4.0
0x2a5a4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x2a5a9  ldarg.0
0x2a5aa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
  ... truncated ...
```
