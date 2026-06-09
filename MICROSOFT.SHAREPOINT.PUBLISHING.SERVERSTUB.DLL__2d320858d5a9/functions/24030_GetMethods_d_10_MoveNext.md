# <GetMethods>d__10::MoveNext

- ea: `0x24030`
- end: `0x24b90`
- name: `<GetMethods>d__10::MoveNext`
- size: `2912`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xd830`
- `0x24030`
- `0x24bb0`
- `0x24c10`

## string_xrefs

- `0x241d8`: `Create`
- `0x2420d`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x24030  ldarg.0
0x24031  ldfld    int32 <GetMethods>d__10::<>1__state
0x24036  stloc.1
0x24037  ldloc.1
0x24038  switch   loc_2406E, loc_24B83, loc_240D8, loc_241BF, loc_2430F, loc_243E8, loc_24631, loc_24784, loc_248D7, loc_24A2B, loc_24B7C
0x24069  br       loc_24B83
0x2406e  ldarg.0
0x2406f  ldc.i4.m1
0x24070  stfld    int32 <GetMethods>d__10::<>1__state
0x24075  ldarg.0
0x24076  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__10::proxyContext
0x2407b  brtrue.s loc_24088
0x2407d  ldstr    aProxycontext// "proxyContext"
0x24082  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x24087  throw
0x24088  ldarg.0
0x24089  ldarg.0
0x2408a  ldfld    class Microsoft.SharePoint.Publishing.SitePageCollectionServerStub <GetMethods>d__10::<>4__this
0x2408f  ldarg.0
0x24090  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__10::proxyContext
0x24095  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::<>n__FabricatedMethod15(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x2409a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x2409f  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__10::<>7__wrap13
0x240a4  ldarg.0
0x240a5  ldc.i4.1
0x240a6  stfld    int32 <GetMethods>d__10::<>1__state
0x240ab  br.s     loc_240DF
0x240ad  ldarg.0
0x240ae  ldarg.0
0x240af  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__10::<>7__wrap13
0x240b4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x240b9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<itemBase>5__11
0x240be  ldarg.0
0x240bf  ldarg.0
0x240c0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<itemBase>5__11
0x240c5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>2__current
0x240ca  ldarg.0
0x240cb  ldc.i4.2
0x240cc  stfld    int32 <GetMethods>d__10::<>1__state
0x240d1  ldc.i4.1
0x240d2  stloc.0
0x240d3  leave    loc_24B8E
0x240d8  ldarg.0
0x240d9  ldc.i4.1
0x240da  stfld    int32 <GetMethods>d__10::<>1__state
0x240df  ldarg.0
0x240e0  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__10::<>7__wrap13
0x240e5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x240ea  brtrue.s loc_240AD
0x240ec  ldarg.0
0x240ed  call     instance void <GetMethods>d__10::<>m__Finally14()
0x240f2  ldarg.0
0x240f3  ldarg.0
0x240f4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x240f9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x240fe  ldarg.0
0x240ff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x24104  ldstr    aCtor// ".ctor"
0x24109  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x2410e  ldarg.0
0x2410f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x24114  ldc.i4.0
0x24115  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x2411a  ldarg.0
0x2411b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x24120  ldc.i4.0
0x24121  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x24126  ldarg.0
0x24127  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x2412c  ldc.i4   0xFFFFFFF
0x24131  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x24136  ldarg.0
0x24137  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x2413c  ldstr    aCtor// ".ctor"
0x24141  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x24146  ldarg.0
0x24147  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x2414c  ldc.i4.0
0x2414d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x24152  ldarg.0
0x24153  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x24158  ldnull
0x24159  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x2415e  ldarg.0
0x2415f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x24164  ldc.i4.0
0x24165  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2416a  ldarg.0
0x2416b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x24170  ldc.i4.0
0x24171  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x24176  ldarg.0
0x24177  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x2417c  ldc.i4.0
0x2417d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x24182  ldarg.0
0x24183  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x24188  ldc.i4.0
0x24189  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2418e  ldarg.0
0x2418f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x24194  ldc.i4.1
0x24195  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x2419a  ldarg.0
0x2419b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x241a0  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x241a5  ldarg.0
0x241a6  ldarg.0
0x241a7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x241ac  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>2__current
0x241b1  ldarg.0
0x241b2  ldc.i4.3
0x241b3  stfld    int32 <GetMethods>d__10::<>1__state
0x241b8  ldc.i4.1
0x241b9  stloc.0
0x241ba  leave    loc_24B8E
0x241bf  ldarg.0
0x241c0  ldc.i4.m1
0x241c1  stfld    int32 <GetMethods>d__10::<>1__state
0x241c6  ldarg.0
0x241c7  ldarg.0
0x241c8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x241cd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal1
0x241d2  ldarg.0
0x241d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal1
0x241d8  ldstr    aCreate// "Create"
0x241dd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x241e2  ldarg.0
0x241e3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal1
0x241e8  ldc.i4.0
0x241e9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x241ee  ldarg.0
0x241ef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal1
0x241f4  ldc.i4.0
0x241f5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x241fa  ldarg.0
0x241fb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal1
0x24200  ldc.i4.s 0x10
0x24202  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x24207  ldarg.0
0x24208  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal1
0x2420d  ldstr    aCreate// "Create"
0x24212  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x24217  ldarg.0
0x24218  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal1
0x2421d  ldc.i4.0
0x2421e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x24223  ldarg.0
0x24224  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal1
0x24229  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage
0x2422e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x24233  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x24238  ldarg.0
0x24239  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal1
0x2423e  ldc.i4.4
0x2423f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x24244  ldarg.0
0x24245  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal1
0x2424a  ldc.i4.0
0x2424b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x24250  ldarg.0
0x24251  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal1
0x24256  ldc.i4.0
0x24257  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x2425c  ldarg.0
0x2425d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal1
0x24262  ldc.i4.0
0x24263  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x24268  ldarg.0
0x24269  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal1
0x2426e  ldc.i4.1
0x2426f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x24274  ldarg.0
0x24275  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal1
0x2427a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x2427f  ldarg.0
0x24280  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x24285  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x2428a  ldarg.0
0x2428b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x24290  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0x24295  ldarg.0
0x24296  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0x2429b  ldstr    aSitepageinfo// "sitePageInfo"
0x242a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x242a5  ldarg.0
0x242a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0x242ab  ldc.i4.0
0x242ac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x242b1  ldarg.0
0x242b2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0x242b7  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo
0x242bc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x242c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x242c6  ldarg.0
0x242c7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0x242cc  ldc.i4.2
0x242cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x242d2  ldarg.0
0x242d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0x242d8  ldc.i4.1
0x242d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x242de  ldarg.0
0x242df  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0x242e4  ldnull
0x242e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x242ea  ldarg.0
0x242eb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0x242f0  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x242f5  ldarg.0
0x242f6  ldarg.0
0x242f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x242fc  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>2__current
0x24301  ldarg.0
0x24302  ldc.i4.4
0x24303  stfld    int32 <GetMethods>d__10::<>1__state
0x24308  ldc.i4.1
0x24309  stloc.0
0x2430a  leave    loc_24B8E
0x2430f  ldarg.0
0x24310  ldc.i4.m1
0x24311  stfld    int32 <GetMethods>d__10::<>1__state
0x24316  ldarg.0
0x24317  ldarg.0
0x24318  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x2431d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0x24322  ldarg.0
0x24323  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0x24328  ldstr    aEnsuretitleres// "EnsureTitleResource"
0x2432d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x24332  ldarg.0
0x24333  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0x24338  ldc.i4.0
0x24339  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x2433e  ldarg.0
0x2433f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0x24344  ldc.i4.0
0x24345  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x2434a  ldarg.0
0x2434b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0x24350  ldc.i4.8
0x24351  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x24356  ldarg.0
0x24357  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0x2435c  ldstr    aEnsuretitleres// "EnsureTitleResource"
0x24361  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x24366  ldarg.0
0x24367  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0x2436c  ldc.i4.0
0x2436d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x24372  ldarg.0
0x24373  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0x24378  ldtoken  [mscorlib]System.Void
0x2437d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x24382  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x24387  ldarg.0
0x24388  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0x2438d  ldc.i4.0
0x2438e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x24393  ldarg.0
0x24394  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0x24399  ldc.i4.0
0x2439a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x2439f  ldarg.0
0x243a0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0x243a5  ldc.i4.0
0x243a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x243ab  ldarg.0
0x243ac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0x243b1  ldc.i4.0
0x243b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x243b7  ldarg.0
0x243b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0x243bd  ldc.i4.1
0x243be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x243c3  ldarg.0
0x243c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0x243c9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x243ce  ldarg.0
0x243cf  ldarg.0
0x243d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x243d5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>2__current
0x243da  ldarg.0
0x243db  ldc.i4.5
0x243dc  stfld    int32 <GetMethods>d__10::<>1__state
0x243e1  ldc.i4.1
0x243e2  stloc.0
0x243e3  leave    loc_24B8E
0x243e8  ldarg.0
0x243e9  ldc.i4.m1
0x243ea  stfld    int32 <GetMethods>d__10::<>1__state
0x243ef  ldarg.0
0x243f0  ldarg.0
0x243f1  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x243f6  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x243fb  ldarg.0
0x243fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x24401  ldstr    aFeed// "Feed"
0x24406  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x2440b  ldarg.0
  ... truncated ...
```
