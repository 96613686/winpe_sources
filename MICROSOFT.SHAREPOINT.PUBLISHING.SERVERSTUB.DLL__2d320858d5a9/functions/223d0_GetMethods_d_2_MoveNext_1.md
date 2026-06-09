# <GetMethods>d__2::MoveNext_1

- ea: `0x223d0`
- end: `0x225d3`
- name: `<GetMethods>d__2::MoveNext_1`
- size: `515`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xc0b0`
- `0x223d0`
- `0x22600`
- `0x22660`

## string_xrefs

- `0x22488`: `CreatePageLayout`
- `0x224bc`: `CreatePageLayout`

## pseudocode

```c

```

## disassembly

```asm
0x223d0  ldarg.0
0x223d1  ldfld    int32 <GetMethods>d__2::<>1__state
0x223d6  stloc.1
0x223d7  ldloc.1
0x223d8  switch   loc_223F2, loc_225C6, loc_2245C, loc_225BF
0x223ed  br       loc_225C6
0x223f2  ldarg.0
0x223f3  ldc.i4.m1
0x223f4  stfld    int32 <GetMethods>d__2::<>1__state
0x223f9  ldarg.0
0x223fa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__2::proxyContext
0x223ff  brtrue.s loc_2240C
0x22401  ldstr    aProxycontext// "proxyContext"
0x22406  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2240b  throw
0x2240c  ldarg.0
0x2240d  ldarg.0
0x2240e  ldfld    class Microsoft.SharePoint.Publishing.PublishingSiteServerStub <GetMethods>d__2::<>4__this
0x22413  ldarg.0
0x22414  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__2::proxyContext
0x22419  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Publishing.PublishingSiteServerStub::<>n__FabricatedMethod7(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x2241e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x22423  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__2::<>7__wrap5
0x22428  ldarg.0
0x22429  ldc.i4.1
0x2242a  stfld    int32 <GetMethods>d__2::<>1__state
0x2242f  br.s     loc_22463
0x22431  ldarg.0
0x22432  ldarg.0
0x22433  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__2::<>7__wrap5
0x22438  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x2243d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<itemBase>5__3
0x22442  ldarg.0
0x22443  ldarg.0
0x22444  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<itemBase>5__3
0x22449  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>2__current
0x2244e  ldarg.0
0x2244f  ldc.i4.2
0x22450  stfld    int32 <GetMethods>d__2::<>1__state
0x22455  ldc.i4.1
0x22456  stloc.0
0x22457  leave    loc_225D1
0x2245c  ldarg.0
0x2245d  ldc.i4.1
0x2245e  stfld    int32 <GetMethods>d__2::<>1__state
0x22463  ldarg.0
0x22464  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__2::<>7__wrap5
0x22469  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2246e  brtrue.s loc_22431
0x22470  ldarg.0
0x22471  call     instance void <GetMethods>d__2::<>m__Finally6()
0x22476  ldarg.0
0x22477  ldarg.0
0x22478  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x2247d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x22482  ldarg.0
0x22483  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x22488  ldstr    aCreatepagelayo// "CreatePageLayout"
0x2248d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x22492  ldarg.0
0x22493  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x22498  ldc.i4.1
0x22499  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x2249e  ldarg.0
0x2249f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x224a4  ldc.i4.0
0x224a5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x224aa  ldarg.0
0x224ab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x224b0  ldc.i4.7
0x224b1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x224b6  ldarg.0
0x224b7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x224bc  ldstr    aCreatepagelayo// "CreatePageLayout"
0x224c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x224c6  ldarg.0
0x224c7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x224cc  ldc.i4.0
0x224cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x224d2  ldarg.0
0x224d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x224d8  ldtoken  [mscorlib]System.Void
0x224dd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x224e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x224e7  ldarg.0
0x224e8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x224ed  ldc.i4.0
0x224ee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x224f3  ldarg.0
0x224f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x224f9  ldc.i4.0
0x224fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x224ff  ldarg.0
0x22500  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x22505  ldc.i4.0
0x22506  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x2250b  ldarg.0
0x2250c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x22511  ldc.i4.0
0x22512  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x22517  ldarg.0
0x22518  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x2251d  ldc.i4.0
0x2251e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x22523  ldarg.0
0x22524  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x22529  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<item>5__4
0x2252e  ldarg.0
0x2252f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<item>5__4
0x22534  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x22539  ldarg.0
0x2253a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x2253f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x22544  ldarg.0
0x22545  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x2254a  ldstr    aParameters// "parameters"
0x2254f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x22554  ldarg.0
0x22555  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x2255a  ldc.i4.0
0x2255b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x22560  ldarg.0
0x22561  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x22566  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation
0x2256b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22570  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x22575  ldarg.0
0x22576  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x2257b  ldc.i4.2
0x2257c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x22581  ldarg.0
0x22582  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x22587  ldc.i4.0
0x22588  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x2258d  ldarg.0
0x2258e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x22593  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x22598  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x2259d  ldarg.0
0x2259e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x225a3  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x225a8  ldarg.0
0x225a9  ldarg.0
0x225aa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<item>5__4
0x225af  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>2__current
0x225b4  ldarg.0
0x225b5  ldc.i4.3
0x225b6  stfld    int32 <GetMethods>d__2::<>1__state
0x225bb  ldc.i4.1
0x225bc  stloc.0
0x225bd  leave.s  loc_225D1
0x225bf  ldarg.0
0x225c0  ldc.i4.m1
0x225c1  stfld    int32 <GetMethods>d__2::<>1__state
0x225c6  ldc.i4.0
0x225c7  stloc.0
0x225c8  leave.s  loc_225D1
0x225ca  ldarg.0
0x225cb  call     instance void <GetMethods>d__2::System.IDisposable.Dispose()
0x225d0  endfinally
0x225d1  ldloc.0
0x225d2  ret
```
