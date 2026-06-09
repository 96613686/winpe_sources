# <GetMethods>d__22::MoveNext

- ea: `0x1b4e50`
- end: `0x1b65ce`
- name: `<GetMethods>d__22::MoveNext`
- size: `6014`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0xb6510`
- `0x1b4e50`
- `0x1b65f0`
- `0x1b6650`

## string_xrefs

- `0x1b64fc`: `ValidatePendingWebTemplateExtension`
- `0x1b6530`: `ValidatePendingWebTemplateExtension`
- `0x1b5341`: `CreateSiteScript`
- `0x1b5375`: `CreateSiteScript`
- `0x1b55e7`: `DeleteSiteScript`
- `0x1b561b`: `DeleteSiteScript`
- `0x1b51ee`: `CreateSiteDesign`
- `0x1b5222`: `CreateSiteDesign`
- `0x1b5494`: `DeleteSiteDesign`
- `0x1b54c8`: `DeleteSiteDesign`
- `0x1b6254`: `UpdateSiteScript`
- `0x1b6288`: `UpdateSiteScript`
- `0x1b63a8`: `UpdateSiteScriptContent`
- `0x1b63dc`: `UpdateSiteScriptContent`
- `0x1b6100`: `UpdateSiteDesign`
- `0x1b6134`: `UpdateSiteDesign`
- `0x1b61c2`: `updateInfo`
- `0x1b6316`: `updateInfo`
- `0x1b646a`: `updateInfo`

## pseudocode

```c

```

## disassembly

```asm
0x1b4e50  ldarg.0
0x1b4e51  ldfld    int32 <GetMethods>d__22::<>1__state
0x1b4e56  stloc.1
0x1b4e57  ldloc.1
0x1b4e58  switch   loc_1B4EB2, loc_1B65C1, loc_1B4F1C, loc_1B5008, loc_1B51D5, loc_1B5328, loc_1B547B, loc_1B55CE, loc_1B5721, loc_1B5875, loc_1B59C9, loc_1B5AA3, loc_1B5BF7, loc_1B5CD1, loc_1B5F19, loc_1B60E7, loc_1B623B, loc_1B638F, loc_1B64E3, loc_1B65BA
0x1b4ead  br       loc_1B65C1
0x1b4eb2  ldarg.0
0x1b4eb3  ldc.i4.m1
0x1b4eb4  stfld    int32 <GetMethods>d__22::<>1__state
0x1b4eb9  ldarg.0
0x1b4eba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__22::proxyContext
0x1b4ebf  brtrue.s loc_1B4ECC
0x1b4ec1  ldstr    aProxycontext// "proxyContext"
0x1b4ec6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1b4ecb  throw
0x1b4ecc  ldarg.0
0x1b4ecd  ldarg.0
0x1b4ece  ldfld    class Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub <GetMethods>d__22::<>4__this
0x1b4ed3  ldarg.0
0x1b4ed4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__22::proxyContext
0x1b4ed9  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::<>n__FabricatedMethod27(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext xmlargs)
0x1b4ede  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x1b4ee3  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__22::<>7__wrap25
0x1b4ee8  ldarg.0
0x1b4ee9  ldc.i4.1
0x1b4eea  stfld    int32 <GetMethods>d__22::<>1__state
0x1b4eef  br.s     loc_1B4F23
0x1b4ef1  ldarg.0
0x1b4ef2  ldarg.0
0x1b4ef3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__22::<>7__wrap25
0x1b4ef8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x1b4efd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<itemBase>5__23
0x1b4f02  ldarg.0
0x1b4f03  ldarg.0
0x1b4f04  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<itemBase>5__23
0x1b4f09  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>2__current
0x1b4f0e  ldarg.0
0x1b4f0f  ldc.i4.2
0x1b4f10  stfld    int32 <GetMethods>d__22::<>1__state
0x1b4f15  ldc.i4.1
0x1b4f16  stloc.0
0x1b4f17  leave    loc_1B65CC
0x1b4f1c  ldarg.0
0x1b4f1d  ldc.i4.1
0x1b4f1e  stfld    int32 <GetMethods>d__22::<>1__state
0x1b4f23  ldarg.0
0x1b4f24  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__22::<>7__wrap25
0x1b4f29  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1b4f2e  brtrue.s loc_1B4EF1
0x1b4f30  ldarg.0
0x1b4f31  call     instance void <GetMethods>d__22::<>m__Finally26()
0x1b4f36  ldarg.0
0x1b4f37  ldarg.0
0x1b4f38  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1b4f3d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal0
0x1b4f42  ldarg.0
0x1b4f43  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal0
0x1b4f48  ldstr    aApplyimplicits// "ApplyImplicitSiteDesign"
0x1b4f4d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1b4f52  ldarg.0
0x1b4f53  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal0
0x1b4f58  ldc.i4.1
0x1b4f59  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1b4f5e  ldarg.0
0x1b4f5f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal0
0x1b4f64  ldc.i4.0
0x1b4f65  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1b4f6a  ldarg.0
0x1b4f6b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal0
0x1b4f70  ldc.i4.8
0x1b4f71  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1b4f76  ldarg.0
0x1b4f77  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal0
0x1b4f7c  ldstr    aApplyimplicits// "ApplyImplicitSiteDesign"
0x1b4f81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1b4f86  ldarg.0
0x1b4f87  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal0
0x1b4f8c  ldc.i4.0
0x1b4f8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1b4f92  ldarg.0
0x1b4f93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal0
0x1b4f98  ldtoken  [mscorlib]System.Boolean
0x1b4f9d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b4fa2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1b4fa7  ldarg.0
0x1b4fa8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal0
0x1b4fad  ldc.i4.1
0x1b4fae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1b4fb3  ldarg.0
0x1b4fb4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal0
0x1b4fb9  ldc.i4.0
0x1b4fba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1b4fbf  ldarg.0
0x1b4fc0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal0
0x1b4fc5  ldc.i4.0
0x1b4fc6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1b4fcb  ldarg.0
0x1b4fcc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal0
0x1b4fd1  ldc.i4.0
0x1b4fd2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1b4fd7  ldarg.0
0x1b4fd8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal0
0x1b4fdd  ldc.i4.1
0x1b4fde  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1b4fe3  ldarg.0
0x1b4fe4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal0
0x1b4fe9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<item>5__24
0x1b4fee  ldarg.0
0x1b4fef  ldarg.0
0x1b4ff0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<item>5__24
0x1b4ff5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>2__current
0x1b4ffa  ldarg.0
0x1b4ffb  ldc.i4.3
0x1b4ffc  stfld    int32 <GetMethods>d__22::<>1__state
0x1b5001  ldc.i4.1
0x1b5002  stloc.0
0x1b5003  leave    loc_1B65CC
0x1b5008  ldarg.0
0x1b5009  ldc.i4.m1
0x1b500a  stfld    int32 <GetMethods>d__22::<>1__state
0x1b500f  ldarg.0
0x1b5010  ldarg.0
0x1b5011  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1b5016  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal1
0x1b501b  ldarg.0
0x1b501c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal1
0x1b5021  ldstr    aApplysitedesig// "ApplySiteDesign"
0x1b5026  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1b502b  ldarg.0
0x1b502c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal1
0x1b5031  ldc.i4.1
0x1b5032  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1b5037  ldarg.0
0x1b5038  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal1
0x1b503d  ldc.i4.0
0x1b503e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1b5043  ldarg.0
0x1b5044  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal1
0x1b5049  ldc.i4.8
0x1b504a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1b504f  ldarg.0
0x1b5050  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal1
0x1b5055  ldstr    aApplysitedesig// "ApplySiteDesign"
0x1b505a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1b505f  ldarg.0
0x1b5060  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal1
0x1b5065  ldc.i4.0
0x1b5066  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1b506b  ldarg.0
0x1b506c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal1
0x1b5071  ldtoken  class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptActionResult>
0x1b5076  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b507b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1b5080  ldarg.0
0x1b5081  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal1
0x1b5086  ldc.i4.3
0x1b5087  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1b508c  ldarg.0
0x1b508d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal1
0x1b5092  ldc.i4.0
0x1b5093  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1b5098  ldarg.0
0x1b5099  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal1
0x1b509e  ldc.i4.0
0x1b509f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1b50a4  ldarg.0
0x1b50a5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal1
0x1b50aa  ldc.i4.0
0x1b50ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1b50b0  ldarg.0
0x1b50b1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal1
0x1b50b6  ldc.i4.1
0x1b50b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1b50bc  ldarg.0
0x1b50bd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal1
0x1b50c2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<item>5__24
0x1b50c7  ldarg.0
0x1b50c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<item>5__24
0x1b50cd  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1b50d2  ldarg.0
0x1b50d3  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1b50d8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__22::<>g__initLocal2
0x1b50dd  ldarg.0
0x1b50de  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__22::<>g__initLocal2
0x1b50e3  ldstr    aWeburl_0// "webUrl"
0x1b50e8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1b50ed  ldarg.0
0x1b50ee  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__22::<>g__initLocal2
0x1b50f3  ldc.i4.0
0x1b50f4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1b50f9  ldarg.0
0x1b50fa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__22::<>g__initLocal2
0x1b50ff  ldtoken  [mscorlib]System.String
0x1b5104  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b5109  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1b510e  ldarg.0
0x1b510f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__22::<>g__initLocal2
0x1b5114  ldc.i4.1
0x1b5115  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1b511a  ldarg.0
0x1b511b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__22::<>g__initLocal2
0x1b5120  ldc.i4.0
0x1b5121  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1b5126  ldarg.0
0x1b5127  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__22::<>g__initLocal2
0x1b512c  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1b5131  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1b5136  ldarg.0
0x1b5137  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__22::<>g__initLocal2
0x1b513c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1b5141  ldarg.0
0x1b5142  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<item>5__24
0x1b5147  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1b514c  ldarg.0
0x1b514d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1b5152  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__22::<>g__initLocal3
0x1b5157  ldarg.0
0x1b5158  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__22::<>g__initLocal3
0x1b515d  ldstr    aSitedesignid_0// "siteDesignId"
0x1b5162  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1b5167  ldarg.0
0x1b5168  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__22::<>g__initLocal3
0x1b516d  ldc.i4.0
0x1b516e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1b5173  ldarg.0
0x1b5174  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__22::<>g__initLocal3
0x1b5179  ldtoken  [mscorlib]System.Guid
0x1b517e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b5183  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1b5188  ldarg.0
0x1b5189  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__22::<>g__initLocal3
0x1b518e  ldc.i4.1
0x1b518f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1b5194  ldarg.0
0x1b5195  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__22::<>g__initLocal3
0x1b519a  ldc.i4.0
0x1b519b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1b51a0  ldarg.0
0x1b51a1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__22::<>g__initLocal3
0x1b51a6  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1b51ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1b51b0  ldarg.0
0x1b51b1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__22::<>g__initLocal3
0x1b51b6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1b51bb  ldarg.0
0x1b51bc  ldarg.0
0x1b51bd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<item>5__24
0x1b51c2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>2__current
0x1b51c7  ldarg.0
0x1b51c8  ldc.i4.4
0x1b51c9  stfld    int32 <GetMethods>d__22::<>1__state
0x1b51ce  ldc.i4.1
0x1b51cf  stloc.0
0x1b51d0  leave    loc_1B65CC
0x1b51d5  ldarg.0
0x1b51d6  ldc.i4.m1
0x1b51d7  stfld    int32 <GetMethods>d__22::<>1__state
0x1b51dc  ldarg.0
0x1b51dd  ldarg.0
0x1b51de  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1b51e3  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal4
0x1b51e8  ldarg.0
0x1b51e9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal4
0x1b51ee  ldstr    aCreatesitedesi// "CreateSiteDesign"
0x1b51f3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1b51f8  ldarg.0
0x1b51f9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal4
0x1b51fe  ldc.i4.1
0x1b51ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1b5204  ldarg.0
0x1b5205  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal4
0x1b520a  ldc.i4.0
0x1b520b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1b5210  ldarg.0
0x1b5211  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal4
0x1b5216  ldc.i4.8
0x1b5217  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1b521c  ldarg.0
0x1b521d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal4
0x1b5222  ldstr    aCreatesitedesi// "CreateSiteDesign"
0x1b5227  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1b522c  ldarg.0
0x1b522d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal4
0x1b5232  ldc.i4.0
0x1b5233  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1b5238  ldarg.0
0x1b5239  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal4
0x1b523e  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignMetadata
0x1b5243  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b5248  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1b524d  ldarg.0
0x1b524e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal4
0x1b5253  ldc.i4.2
0x1b5254  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1b5259  ldarg.0
0x1b525a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal4
0x1b525f  ldc.i4.0
0x1b5260  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1b5265  ldarg.0
0x1b5266  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__22::<>g__initLocal4
  ... truncated ...
```
