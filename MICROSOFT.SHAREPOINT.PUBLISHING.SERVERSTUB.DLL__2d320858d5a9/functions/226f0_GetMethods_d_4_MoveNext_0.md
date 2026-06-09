# <GetMethods>d__4::MoveNext_0

- ea: `0x226f0`
- end: `0x22a4a`
- name: `<GetMethods>d__4::MoveNext_0`
- size: `858`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xc520`
- `0x226f0`
- `0x22a70`
- `0x22ad0`

## pseudocode

```c

```

## disassembly

```asm
0x226f0  ldarg.0
0x226f1  ldfld    int32 <GetMethods>d__4::<>1__state
0x226f6  stloc.1
0x226f7  ldloc.1
0x226f8  switch   loc_22716, loc_22A3D, loc_22780, loc_228E6, loc_22A36
0x22711  br       loc_22A3D
0x22716  ldarg.0
0x22717  ldc.i4.m1
0x22718  stfld    int32 <GetMethods>d__4::<>1__state
0x2271d  ldarg.0
0x2271e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__4::proxyContext
0x22723  brtrue.s loc_22730
0x22725  ldstr    aProxycontext// "proxyContext"
0x2272a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2272f  throw
0x22730  ldarg.0
0x22731  ldarg.0
0x22732  ldfld    class Microsoft.SharePoint.Publishing.PublishingWebServerStub <GetMethods>d__4::<>4__this
0x22737  ldarg.0
0x22738  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__4::proxyContext
0x2273d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Publishing.PublishingWebServerStub::<>n__FabricatedMethod9(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x22742  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x22747  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__4::<>7__wrap7
0x2274c  ldarg.0
0x2274d  ldc.i4.1
0x2274e  stfld    int32 <GetMethods>d__4::<>1__state
0x22753  br.s     loc_22787
0x22755  ldarg.0
0x22756  ldarg.0
0x22757  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__4::<>7__wrap7
0x2275c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x22761  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<itemBase>5__5
0x22766  ldarg.0
0x22767  ldarg.0
0x22768  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<itemBase>5__5
0x2276d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>2__current
0x22772  ldarg.0
0x22773  ldc.i4.2
0x22774  stfld    int32 <GetMethods>d__4::<>1__state
0x22779  ldc.i4.1
0x2277a  stloc.0
0x2277b  leave    loc_22A48
0x22780  ldarg.0
0x22781  ldc.i4.1
0x22782  stfld    int32 <GetMethods>d__4::<>1__state
0x22787  ldarg.0
0x22788  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__4::<>7__wrap7
0x2278d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x22792  brtrue.s loc_22755
0x22794  ldarg.0
0x22795  call     instance void <GetMethods>d__4::<>m__Finally8()
0x2279a  ldarg.0
0x2279b  ldarg.0
0x2279c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x227a1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x227a6  ldarg.0
0x227a7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x227ac  ldstr    aAddpublishingp// "AddPublishingPage"
0x227b1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x227b6  ldarg.0
0x227b7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x227bc  ldc.i4.0
0x227bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x227c2  ldarg.0
0x227c3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x227c8  ldc.i4.0
0x227c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x227ce  ldarg.0
0x227cf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x227d4  ldc.i4.7
0x227d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x227da  ldarg.0
0x227db  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x227e0  ldstr    aAddpublishingp_0// "AddPublishingPageCsom"
0x227e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x227ea  ldarg.0
0x227eb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x227f0  ldc.i4.0
0x227f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x227f6  ldarg.0
0x227f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x227fc  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PublishingPage
0x22801  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22806  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x2280b  ldarg.0
0x2280c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x22811  ldc.i4.4
0x22812  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x22817  ldarg.0
0x22818  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x2281d  ldc.i4.0
0x2281e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x22823  ldarg.0
0x22824  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x22829  ldc.i4.0
0x2282a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x2282f  ldarg.0
0x22830  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x22835  ldc.i4.0
0x22836  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2283b  ldarg.0
0x2283c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x22841  ldc.i4.0
0x22842  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x22847  ldarg.0
0x22848  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x2284d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x22852  ldarg.0
0x22853  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x22858  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x2285d  ldarg.0
0x2285e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x22863  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal1
0x22868  ldarg.0
0x22869  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal1
0x2286e  ldstr    aPageinformatio// "pageInformation"
0x22873  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x22878  ldarg.0
0x22879  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal1
0x2287e  ldc.i4.0
0x2287f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x22884  ldarg.0
0x22885  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal1
0x2288a  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PublishingPageInformationCsom
0x2288f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22894  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x22899  ldarg.0
0x2289a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal1
0x2289f  ldc.i4.2
0x228a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x228a5  ldarg.0
0x228a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal1
0x228ab  ldc.i4.0
0x228ac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x228b1  ldarg.0
0x228b2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal1
0x228b7  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x228bc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x228c1  ldarg.0
0x228c2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal1
0x228c7  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x228cc  ldarg.0
0x228cd  ldarg.0
0x228ce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x228d3  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>2__current
0x228d8  ldarg.0
0x228d9  ldc.i4.3
0x228da  stfld    int32 <GetMethods>d__4::<>1__state
0x228df  ldc.i4.1
0x228e0  stloc.0
0x228e1  leave    loc_22A48
0x228e6  ldarg.0
0x228e7  ldc.i4.m1
0x228e8  stfld    int32 <GetMethods>d__4::<>1__state
0x228ed  ldarg.0
0x228ee  ldarg.0
0x228ef  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x228f4  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x228f9  ldarg.0
0x228fa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x228ff  ldstr    aGetpublishingw// "GetPublishingWeb"
0x22904  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x22909  ldarg.0
0x2290a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x2290f  ldc.i4.1
0x22910  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x22915  ldarg.0
0x22916  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x2291b  ldc.i4.0
0x2291c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x22921  ldarg.0
0x22922  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x22927  ldc.i4.7
0x22928  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x2292d  ldarg.0
0x2292e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x22933  ldstr    aGetpublishingw// "GetPublishingWeb"
0x22938  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x2293d  ldarg.0
0x2293e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x22943  ldc.i4.0
0x22944  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x22949  ldarg.0
0x2294a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x2294f  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PublishingWeb
0x22954  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22959  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x2295e  ldarg.0
0x2295f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x22964  ldc.i4.4
0x22965  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2296a  ldarg.0
0x2296b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x22970  ldc.i4.0
0x22971  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x22976  ldarg.0
0x22977  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x2297c  ldc.i4.0
0x2297d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x22982  ldarg.0
0x22983  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x22988  ldc.i4.0
0x22989  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2298e  ldarg.0
0x2298f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x22994  ldc.i4.0
0x22995  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x2299a  ldarg.0
0x2299b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x229a0  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x229a5  ldarg.0
0x229a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x229ab  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x229b0  ldarg.0
0x229b1  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x229b6  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x229bb  ldarg.0
0x229bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x229c1  ldstr    aWeb// "web"
0x229c6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x229cb  ldarg.0
0x229cc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x229d1  ldc.i4.0
0x229d2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x229d7  ldarg.0
0x229d8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x229dd  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb
0x229e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x229e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x229ec  ldarg.0
0x229ed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x229f2  ldc.i4.0
0x229f3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x229f8  ldarg.0
0x229f9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x229fe  ldc.i4.0
0x229ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x22a04  ldarg.0
0x22a05  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x22a0a  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x22a0f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x22a14  ldarg.0
0x22a15  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x22a1a  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x22a1f  ldarg.0
0x22a20  ldarg.0
0x22a21  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x22a26  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>2__current
0x22a2b  ldarg.0
0x22a2c  ldc.i4.4
0x22a2d  stfld    int32 <GetMethods>d__4::<>1__state
0x22a32  ldc.i4.1
0x22a33  stloc.0
0x22a34  leave.s  loc_22A48
0x22a36  ldarg.0
0x22a37  ldc.i4.m1
0x22a38  stfld    int32 <GetMethods>d__4::<>1__state
0x22a3d  ldc.i4.0
0x22a3e  stloc.0
0x22a3f  leave.s  loc_22A48
0x22a41  ldarg.0
0x22a42  call     instance void <GetMethods>d__4::System.IDisposable.Dispose()
0x22a47  endfinally
0x22a48  ldloc.0
0x22a49  ret
```
