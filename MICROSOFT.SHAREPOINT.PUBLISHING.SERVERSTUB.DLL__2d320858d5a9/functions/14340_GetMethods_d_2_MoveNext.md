# <GetMethods>d__2::MoveNext

- ea: `0x14340`
- end: `0x1453a`
- name: `<GetMethods>d__2::MoveNext`
- size: `506`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1750`
- `0x14340`
- `0x14560`
- `0x145c0`

## pseudocode

```c

```

## disassembly

```asm
0x14340  ldarg.0
0x14341  ldfld    int32 <GetMethods>d__2::<>1__state
0x14346  stloc.1
0x14347  ldloc.1
0x14348  switch   loc_14362, loc_1452D, loc_143CC, loc_14526
0x1435d  br       loc_1452D
0x14362  ldarg.0
0x14363  ldc.i4.m1
0x14364  stfld    int32 <GetMethods>d__2::<>1__state
0x14369  ldarg.0
0x1436a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__2::proxyContext
0x1436f  brtrue.s loc_1437C
0x14371  ldstr    aProxycontext// "proxyContext"
0x14376  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1437b  throw
0x1437c  ldarg.0
0x1437d  ldarg.0
0x1437e  ldfld    class Microsoft.SharePoint.Publishing.AddinSettingsServerStub <GetMethods>d__2::<>4__this
0x14383  ldarg.0
0x14384  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__2::proxyContext
0x14389  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Publishing.AddinSettingsServerStub::<>n__FabricatedMethod7(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x1438e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x14393  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__2::<>7__wrap5
0x14398  ldarg.0
0x14399  ldc.i4.1
0x1439a  stfld    int32 <GetMethods>d__2::<>1__state
0x1439f  br.s     loc_143D3
0x143a1  ldarg.0
0x143a2  ldarg.0
0x143a3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__2::<>7__wrap5
0x143a8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x143ad  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<itemBase>5__3
0x143b2  ldarg.0
0x143b3  ldarg.0
0x143b4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<itemBase>5__3
0x143b9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>2__current
0x143be  ldarg.0
0x143bf  ldc.i4.2
0x143c0  stfld    int32 <GetMethods>d__2::<>1__state
0x143c5  ldc.i4.1
0x143c6  stloc.0
0x143c7  leave    loc_14538
0x143cc  ldarg.0
0x143cd  ldc.i4.1
0x143ce  stfld    int32 <GetMethods>d__2::<>1__state
0x143d3  ldarg.0
0x143d4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__2::<>7__wrap5
0x143d9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x143de  brtrue.s loc_143A1
0x143e0  ldarg.0
0x143e1  call     instance void <GetMethods>d__2::<>m__Finally6()
0x143e6  ldarg.0
0x143e7  ldarg.0
0x143e8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x143ed  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x143f2  ldarg.0
0x143f3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x143f8  ldstr    aCtor// ".ctor"
0x143fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x14402  ldarg.0
0x14403  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x14408  ldc.i4.0
0x14409  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1440e  ldarg.0
0x1440f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x14414  ldc.i4.0
0x14415  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1441a  ldarg.0
0x1441b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x14420  ldc.i4.7
0x14421  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x14426  ldarg.0
0x14427  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x1442c  ldstr    aCtor// ".ctor"
0x14431  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x14436  ldarg.0
0x14437  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x1443c  ldc.i4.0
0x1443d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x14442  ldarg.0
0x14443  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x14448  ldnull
0x14449  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1444e  ldarg.0
0x1444f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x14454  ldc.i4.0
0x14455  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1445a  ldarg.0
0x1445b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x14460  ldc.i4.0
0x14461  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x14466  ldarg.0
0x14467  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x1446c  ldc.i4.0
0x1446d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x14472  ldarg.0
0x14473  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x14478  ldc.i4.0
0x14479  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1447e  ldarg.0
0x1447f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x14484  ldc.i4.0
0x14485  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1448a  ldarg.0
0x1448b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x14490  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<item>5__4
0x14495  ldarg.0
0x14496  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<item>5__4
0x1449b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x144a0  ldarg.0
0x144a1  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x144a6  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x144ab  ldarg.0
0x144ac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x144b1  ldstr    aId_0// "id"
0x144b6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x144bb  ldarg.0
0x144bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x144c1  ldc.i4.0
0x144c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x144c7  ldarg.0
0x144c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x144cd  ldtoken  [mscorlib]System.Guid
0x144d2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x144d7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x144dc  ldarg.0
0x144dd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x144e2  ldc.i4.1
0x144e3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x144e8  ldarg.0
0x144e9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x144ee  ldc.i4.0
0x144ef  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x144f4  ldarg.0
0x144f5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x144fa  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x144ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x14504  ldarg.0
0x14505  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x1450a  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1450f  ldarg.0
0x14510  ldarg.0
0x14511  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<item>5__4
0x14516  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>2__current
0x1451b  ldarg.0
0x1451c  ldc.i4.3
0x1451d  stfld    int32 <GetMethods>d__2::<>1__state
0x14522  ldc.i4.1
0x14523  stloc.0
0x14524  leave.s  loc_14538
0x14526  ldarg.0
0x14527  ldc.i4.m1
0x14528  stfld    int32 <GetMethods>d__2::<>1__state
0x1452d  ldc.i4.0
0x1452e  stloc.0
0x1452f  leave.s  loc_14538
0x14531  ldarg.0
0x14532  call     instance void <GetMethods>d__2::System.IDisposable.Dispose()
0x14537  endfinally
0x14538  ldloc.0
0x14539  ret
```
