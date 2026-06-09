# <GetMethods>d__14::MoveNext

- ea: `0x1043e0`
- end: `0x1051b6`
- name: `<GetMethods>d__14::MoveNext`
- size: `3542`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x35da0`
- `0x1043e0`
- `0x1051e0`
- `0x105240`

## string_xrefs

- `0x1047e0`: `DeleteAppPrincipal`
- `0x104818`: `DeleteAppPrincipal`
- `0x104689`: `CreateAppPrincipal`
- `0x104a8e`: `GetAppPrincipalConfiguration`
- `0x105066`: `SetAppPrincipalConfiguration`
- `0x104937`: `DeleteAppPrincipalCredential`
- `0x1046c1`: `CreateAppPrincipal_Client`
- `0x10496f`: `DeleteAppPrincipalCredential_Client`
- `0x104ac6`: `GetAppPrincipalConfiguration_Client`
- `0x10509e`: `SetAppPrincipalConfiguration_Client`
- `0x10512c`: `appPrincipalConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x1043e0  ldarg.0
0x1043e1  ldfld    int32 <GetMethods>d__14::<>1__state
0x1043e6  stloc.1
0x1043e7  ldloc.1
0x1043e8  switch   loc_104422, loc_1051A9, loc_10448C, loc_104670, loc_1047C7, loc_10491E, loc_104A75, loc_104BCC, loc_104D23, loc_104E7B, loc_10504D, loc_1051A2
0x10441d  br       loc_1051A9
0x104422  ldarg.0
0x104423  ldc.i4.m1
0x104424  stfld    int32 <GetMethods>d__14::<>1__state
0x104429  ldarg.0
0x10442a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__14::proxyContext
0x10442f  brtrue.s loc_10443C
0x104431  ldstr    aProxycontext// "proxyContext"
0x104436  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10443b  throw
0x10443c  ldarg.0
0x10443d  ldarg.0
0x10443e  ldfld    class Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub <GetMethods>d__14::<>4__this
0x104443  ldarg.0
0x104444  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__14::proxyContext
0x104449  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::<>n__FabricatedMethod19(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext xmlargs)
0x10444e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x104453  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__14::<>7__wrap17
0x104458  ldarg.0
0x104459  ldc.i4.1
0x10445a  stfld    int32 <GetMethods>d__14::<>1__state
0x10445f  br.s     loc_104493
0x104461  ldarg.0
0x104462  ldarg.0
0x104463  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__14::<>7__wrap17
0x104468  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x10446d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<itemBase>5__15
0x104472  ldarg.0
0x104473  ldarg.0
0x104474  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<itemBase>5__15
0x104479  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>2__current
0x10447e  ldarg.0
0x10447f  ldc.i4.2
0x104480  stfld    int32 <GetMethods>d__14::<>1__state
0x104485  ldc.i4.1
0x104486  stloc.0
0x104487  leave    loc_1051B4
0x10448c  ldarg.0
0x10448d  ldc.i4.1
0x10448e  stfld    int32 <GetMethods>d__14::<>1__state
0x104493  ldarg.0
0x104494  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__14::<>7__wrap17
0x104499  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10449e  brtrue.s loc_104461
0x1044a0  ldarg.0
0x1044a1  call     instance void <GetMethods>d__14::<>m__Finally18()
0x1044a6  ldarg.0
0x1044a7  ldarg.0
0x1044a8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1044ad  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x1044b2  ldarg.0
0x1044b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x1044b8  ldstr    aAddappprincipa// "AddAppPrincipalCredential"
0x1044bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1044c2  ldarg.0
0x1044c3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x1044c8  ldc.i4.0
0x1044c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1044ce  ldarg.0
0x1044cf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x1044d4  ldc.i4.0
0x1044d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1044da  ldarg.0
0x1044db  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x1044e0  ldc.i4   0xFFFFFFF
0x1044e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1044ea  ldarg.0
0x1044eb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x1044f0  ldstr    aAddappprincipa// "AddAppPrincipalCredential"
0x1044f5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1044fa  ldarg.0
0x1044fb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x104500  ldc.i4.0
0x104501  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x104506  ldarg.0
0x104507  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x10450c  ldtoken  [mscorlib]System.Void
0x104511  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x104516  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x10451b  ldarg.0
0x10451c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x104521  ldc.i4.0
0x104522  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x104527  ldarg.0
0x104528  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x10452d  ldc.i4.0
0x10452e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x104533  ldarg.0
0x104534  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x104539  ldc.i4.0
0x10453a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x10453f  ldarg.0
0x104540  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x104545  ldc.i4.0
0x104546  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x10454b  ldarg.0
0x10454c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x104551  ldc.i4.0
0x104552  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x104557  ldarg.0
0x104558  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x10455d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<item>5__16
0x104562  ldarg.0
0x104563  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<item>5__16
0x104568  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x10456d  ldarg.0
0x10456e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x104573  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal1
0x104578  ldarg.0
0x104579  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal1
0x10457e  ldstr    aAppprincipal// "appPrincipal"
0x104583  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x104588  ldarg.0
0x104589  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal1
0x10458e  ldc.i4.0
0x10458f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x104594  ldarg.0
0x104595  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal1
0x10459a  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipal
0x10459f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1045a4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1045a9  ldarg.0
0x1045aa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal1
0x1045af  ldc.i4.0
0x1045b0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1045b5  ldarg.0
0x1045b6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal1
0x1045bb  ldc.i4.0
0x1045bc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1045c1  ldarg.0
0x1045c2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal1
0x1045c7  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1045cc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1045d1  ldarg.0
0x1045d2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal1
0x1045d7  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1045dc  ldarg.0
0x1045dd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<item>5__16
0x1045e2  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1045e7  ldarg.0
0x1045e8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1045ed  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal2
0x1045f2  ldarg.0
0x1045f3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal2
0x1045f8  ldstr    aCredential// "credential"
0x1045fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x104602  ldarg.0
0x104603  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal2
0x104608  ldc.i4.0
0x104609  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x10460e  ldarg.0
0x10460f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal2
0x104614  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalCredential
0x104619  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10461e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x104623  ldarg.0
0x104624  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal2
0x104629  ldc.i4.0
0x10462a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x10462f  ldarg.0
0x104630  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal2
0x104635  ldc.i4.0
0x104636  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x10463b  ldarg.0
0x10463c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal2
0x104641  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x104646  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x10464b  ldarg.0
0x10464c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal2
0x104651  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x104656  ldarg.0
0x104657  ldarg.0
0x104658  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<item>5__16
0x10465d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>2__current
0x104662  ldarg.0
0x104663  ldc.i4.3
0x104664  stfld    int32 <GetMethods>d__14::<>1__state
0x104669  ldc.i4.1
0x10466a  stloc.0
0x10466b  leave    loc_1051B4
0x104670  ldarg.0
0x104671  ldc.i4.m1
0x104672  stfld    int32 <GetMethods>d__14::<>1__state
0x104677  ldarg.0
0x104678  ldarg.0
0x104679  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x10467e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal3
0x104683  ldarg.0
0x104684  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal3
0x104689  ldstr    aCreateappprinc// "CreateAppPrincipal"
0x10468e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x104693  ldarg.0
0x104694  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal3
0x104699  ldc.i4.0
0x10469a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x10469f  ldarg.0
0x1046a0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal3
0x1046a5  ldc.i4.0
0x1046a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1046ab  ldarg.0
0x1046ac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal3
0x1046b1  ldc.i4   0xFFFFFFF
0x1046b6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1046bb  ldarg.0
0x1046bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal3
0x1046c1  ldstr    aCreateappprinc_0// "CreateAppPrincipal_Client"
0x1046c6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1046cb  ldarg.0
0x1046cc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal3
0x1046d1  ldc.i4.0
0x1046d2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1046d7  ldarg.0
0x1046d8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal3
0x1046dd  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipal
0x1046e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1046e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1046ec  ldarg.0
0x1046ed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal3
0x1046f2  ldc.i4.4
0x1046f3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1046f8  ldarg.0
0x1046f9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal3
0x1046fe  ldc.i4.0
0x1046ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x104704  ldarg.0
0x104705  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal3
0x10470a  ldc.i4.0
0x10470b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x104710  ldarg.0
0x104711  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal3
0x104716  ldc.i4.0
0x104717  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x10471c  ldarg.0
0x10471d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal3
0x104722  ldc.i4.0
0x104723  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x104728  ldarg.0
0x104729  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal3
0x10472e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<item>5__16
0x104733  ldarg.0
0x104734  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<item>5__16
0x104739  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x10473e  ldarg.0
0x10473f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x104744  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal4
0x104749  ldarg.0
0x10474a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal4
0x10474f  ldstr    aParameters// "parameters"
0x104754  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x104759  ldarg.0
0x10475a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal4
0x10475f  ldc.i4.0
0x104760  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x104765  ldarg.0
0x104766  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal4
0x10476b  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPExternalAppPrincipalCreationParameters_Client
0x104770  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x104775  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x10477a  ldarg.0
0x10477b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal4
0x104780  ldc.i4.2
0x104781  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x104786  ldarg.0
0x104787  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal4
0x10478c  ldc.i4.0
0x10478d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x104792  ldarg.0
0x104793  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal4
0x104798  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x10479d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1047a2  ldarg.0
0x1047a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal4
0x1047a8  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1047ad  ldarg.0
0x1047ae  ldarg.0
0x1047af  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<item>5__16
0x1047b4  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>2__current
0x1047b9  ldarg.0
0x1047ba  ldc.i4.4
0x1047bb  stfld    int32 <GetMethods>d__14::<>1__state
0x1047c0  ldc.i4.1
0x1047c1  stloc.0
0x1047c2  leave    loc_1051B4
0x1047c7  ldarg.0
0x1047c8  ldc.i4.m1
0x1047c9  stfld    int32 <GetMethods>d__14::<>1__state
0x1047ce  ldarg.0
0x1047cf  ldarg.0
0x1047d0  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1047d5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal5
0x1047da  ldarg.0
0x1047db  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal5
0x1047e0  ldstr    aDeleteappprinc// "DeleteAppPrincipal"
0x1047e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1047ea  ldarg.0
  ... truncated ...
```
