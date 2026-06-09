# <GetMethods>d__3::MoveNext

- ea: `0x23840`
- end: `0x23b1f`
- name: `<GetMethods>d__3::MoveNext`
- size: `735`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xcea0`
- `0x23840`
- `0x23b40`
- `0x23ba0`

## pseudocode

```c

```

## disassembly

```asm
0x23840  ldarg.0
0x23841  ldfld    int32 <GetMethods>d__3::<>1__state
0x23846  stloc.1
0x23847  ldloc.1
0x23848  switch   loc_23866, loc_23B12, loc_238D0, loc_239B7, loc_23B0B
0x23861  br       loc_23B12
0x23866  ldarg.0
0x23867  ldc.i4.m1
0x23868  stfld    int32 <GetMethods>d__3::<>1__state
0x2386d  ldarg.0
0x2386e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__3::proxyContext
0x23873  brtrue.s loc_23880
0x23875  ldstr    aProxycontext// "proxyContext"
0x2387a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2387f  throw
0x23880  ldarg.0
0x23881  ldarg.0
0x23882  ldfld    class Microsoft.SharePoint.Publishing.SharePointHomeServiceManagerServerStub <GetMethods>d__3::<>4__this
0x23887  ldarg.0
0x23888  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__3::proxyContext
0x2388d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Publishing.SharePointHomeServiceManagerServerStub::<>n__FabricatedMethod8(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext xmlargs)
0x23892  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x23897  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__3::<>7__wrap6
0x2389c  ldarg.0
0x2389d  ldc.i4.1
0x2389e  stfld    int32 <GetMethods>d__3::<>1__state
0x238a3  br.s     loc_238D7
0x238a5  ldarg.0
0x238a6  ldarg.0
0x238a7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__3::<>7__wrap6
0x238ac  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x238b1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<itemBase>5__4
0x238b6  ldarg.0
0x238b7  ldarg.0
0x238b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<itemBase>5__4
0x238bd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>2__current
0x238c2  ldarg.0
0x238c3  ldc.i4.2
0x238c4  stfld    int32 <GetMethods>d__3::<>1__state
0x238c9  ldc.i4.1
0x238ca  stloc.0
0x238cb  leave    loc_23B1D
0x238d0  ldarg.0
0x238d1  ldc.i4.1
0x238d2  stfld    int32 <GetMethods>d__3::<>1__state
0x238d7  ldarg.0
0x238d8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__3::<>7__wrap6
0x238dd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x238e2  brtrue.s loc_238A5
0x238e4  ldarg.0
0x238e5  call     instance void <GetMethods>d__3::<>m__Finally7()
0x238ea  ldarg.0
0x238eb  ldarg.0
0x238ec  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x238f1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x238f6  ldarg.0
0x238f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x238fc  ldstr    aCtor// ".ctor"
0x23901  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x23906  ldarg.0
0x23907  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x2390c  ldc.i4.0
0x2390d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x23912  ldarg.0
0x23913  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23918  ldc.i4.0
0x23919  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x2391e  ldarg.0
0x2391f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23924  ldc.i4   0xFFFFFFF
0x23929  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x2392e  ldarg.0
0x2392f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23934  ldstr    aCtor// ".ctor"
0x23939  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x2393e  ldarg.0
0x2393f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23944  ldc.i4.0
0x23945  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x2394a  ldarg.0
0x2394b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23950  ldnull
0x23951  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x23956  ldarg.0
0x23957  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x2395c  ldc.i4.0
0x2395d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x23962  ldarg.0
0x23963  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23968  ldc.i4.0
0x23969  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x2396e  ldarg.0
0x2396f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23974  ldc.i4.0
0x23975  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x2397a  ldarg.0
0x2397b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23980  ldc.i4.0
0x23981  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x23986  ldarg.0
0x23987  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x2398c  ldc.i4.1
0x2398d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x23992  ldarg.0
0x23993  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23998  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x2399d  ldarg.0
0x2399e  ldarg.0
0x2399f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x239a4  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>2__current
0x239a9  ldarg.0
0x239aa  ldc.i4.3
0x239ab  stfld    int32 <GetMethods>d__3::<>1__state
0x239b0  ldc.i4.1
0x239b1  stloc.0
0x239b2  leave    loc_23B1D
0x239b7  ldarg.0
0x239b8  ldc.i4.m1
0x239b9  stfld    int32 <GetMethods>d__3::<>1__state
0x239be  ldarg.0
0x239bf  ldarg.0
0x239c0  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x239c5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x239ca  ldarg.0
0x239cb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x239d0  ldstr    aGetacronymsand// "GetAcronymsAndColors"
0x239d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x239da  ldarg.0
0x239db  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x239e0  ldc.i4.0
0x239e1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x239e6  ldarg.0
0x239e7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x239ec  ldc.i4.1
0x239ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x239f2  ldarg.0
0x239f3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x239f8  ldc.i4   0xFFFFFFF
0x239fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x23a02  ldarg.0
0x23a03  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23a08  ldstr    aGetacronymsand// "GetAcronymsAndColors"
0x23a0d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x23a12  ldarg.0
0x23a13  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23a18  ldc.i4.0
0x23a19  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x23a1e  ldarg.0
0x23a1f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23a24  ldtoken  class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/AcronymInformation[]
0x23a29  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23a2e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x23a33  ldarg.0
0x23a34  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23a39  ldc.i4.3
0x23a3a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x23a3f  ldarg.0
0x23a40  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23a45  ldc.i4.0
0x23a46  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x23a4b  ldarg.0
0x23a4c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23a51  ldc.i4.0
0x23a52  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x23a57  ldarg.0
0x23a58  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23a5d  ldc.i4.1
0x23a5e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x23a63  ldarg.0
0x23a64  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23a69  ldc.i4.1
0x23a6a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x23a6f  ldarg.0
0x23a70  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23a75  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x23a7a  ldarg.0
0x23a7b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x23a80  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x23a85  ldarg.0
0x23a86  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x23a8b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x23a90  ldarg.0
0x23a91  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x23a96  ldstr    aLabels// "labels"
0x23a9b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x23aa0  ldarg.0
0x23aa1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x23aa6  ldc.i4.0
0x23aa7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x23aac  ldarg.0
0x23aad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x23ab2  ldtoken  class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/TextValueWithLanguage[]
0x23ab7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23abc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x23ac1  ldarg.0
0x23ac2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x23ac7  ldc.i4.3
0x23ac8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x23acd  ldarg.0
0x23ace  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x23ad3  ldc.i4.0
0x23ad4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x23ad9  ldarg.0
0x23ada  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x23adf  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x23ae4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x23ae9  ldarg.0
0x23aea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x23aef  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x23af4  ldarg.0
0x23af5  ldarg.0
0x23af6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x23afb  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>2__current
0x23b00  ldarg.0
0x23b01  ldc.i4.4
0x23b02  stfld    int32 <GetMethods>d__3::<>1__state
0x23b07  ldc.i4.1
0x23b08  stloc.0
0x23b09  leave.s  loc_23B1D
0x23b0b  ldarg.0
0x23b0c  ldc.i4.m1
0x23b0d  stfld    int32 <GetMethods>d__3::<>1__state
0x23b12  ldc.i4.0
0x23b13  stloc.0
0x23b14  leave.s  loc_23B1D
0x23b16  ldarg.0
0x23b17  call     instance void <GetMethods>d__3::System.IDisposable.Dispose()
0x23b1c  endfinally
0x23b1d  ldloc.0
0x23b1e  ret
```
