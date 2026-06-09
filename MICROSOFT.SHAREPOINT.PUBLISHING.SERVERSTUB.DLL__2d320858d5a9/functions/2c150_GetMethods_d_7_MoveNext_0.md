# <GetMethods>d__7::MoveNext_0

- ea: `0x2c150`
- end: `0x2c67b`
- name: `<GetMethods>d__7::MoveNext_0`
- size: `1323`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x13650`
- `0x2c150`
- `0x2c6a0`
- `0x2c700`

## string_xrefs

- `0x2c4b6`: `UpdateListItems`
- `0x2c4ea`: `UpdateListItems`

## pseudocode

```c

```

## disassembly

```asm
0x2c150  ldarg.0
0x2c151  ldfld    int32 <GetMethods>d__7::<>1__state
0x2c156  stloc.1
0x2c157  ldloc.1
0x2c158  switch   loc_2C17A, loc_2C66E, loc_2C1E4, loc_2C2D0, loc_2C49D, loc_2C667
0x2c175  br       loc_2C66E
0x2c17a  ldarg.0
0x2c17b  ldc.i4.m1
0x2c17c  stfld    int32 <GetMethods>d__7::<>1__state
0x2c181  ldarg.0
0x2c182  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__7::proxyContext
0x2c187  brtrue.s loc_2C194
0x2c189  ldstr    aProxycontext// "proxyContext"
0x2c18e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2c193  throw
0x2c194  ldarg.0
0x2c195  ldarg.0
0x2c196  ldfld    class Microsoft.SharePoint.Publishing.VariationsServerStub <GetMethods>d__7::<>4__this
0x2c19b  ldarg.0
0x2c19c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__7::proxyContext
0x2c1a1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Publishing.VariationsServerStub::<>n__FabricatedMethodc(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <>1__state)
0x2c1a6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x2c1ab  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__7::<>7__wrapa
0x2c1b0  ldarg.0
0x2c1b1  ldc.i4.1
0x2c1b2  stfld    int32 <GetMethods>d__7::<>1__state
0x2c1b7  br.s     loc_2C1EB
0x2c1b9  ldarg.0
0x2c1ba  ldarg.0
0x2c1bb  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__7::<>7__wrapa
0x2c1c0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x2c1c5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<itemBase>5__8
0x2c1ca  ldarg.0
0x2c1cb  ldarg.0
0x2c1cc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<itemBase>5__8
0x2c1d1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>2__current
0x2c1d6  ldarg.0
0x2c1d7  ldc.i4.2
0x2c1d8  stfld    int32 <GetMethods>d__7::<>1__state
0x2c1dd  ldc.i4.1
0x2c1de  stloc.0
0x2c1df  leave    loc_2C679
0x2c1e4  ldarg.0
0x2c1e5  ldc.i4.1
0x2c1e6  stfld    int32 <GetMethods>d__7::<>1__state
0x2c1eb  ldarg.0
0x2c1ec  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__7::<>7__wrapa
0x2c1f1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2c1f6  brtrue.s loc_2C1B9
0x2c1f8  ldarg.0
0x2c1f9  call     instance void <GetMethods>d__7::<>m__Finallyb()
0x2c1fe  ldarg.0
0x2c1ff  ldarg.0
0x2c200  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x2c205  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x2c20a  ldarg.0
0x2c20b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x2c210  ldstr    aGetlabels// "GetLabels"
0x2c215  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x2c21a  ldarg.0
0x2c21b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x2c220  ldc.i4.1
0x2c221  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x2c226  ldarg.0
0x2c227  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x2c22c  ldc.i4.0
0x2c22d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x2c232  ldarg.0
0x2c233  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x2c238  ldc.i4.7
0x2c239  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x2c23e  ldarg.0
0x2c23f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x2c244  ldstr    aGetlabels// "GetLabels"
0x2c249  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x2c24e  ldarg.0
0x2c24f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x2c254  ldc.i4.0
0x2c255  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x2c25a  ldarg.0
0x2c25b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x2c260  ldtoken  class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.VariationLabel>
0x2c265  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2c26a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x2c26f  ldarg.0
0x2c270  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x2c275  ldc.i4.5
0x2c276  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2c27b  ldarg.0
0x2c27c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x2c281  ldc.i4.0
0x2c282  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x2c287  ldarg.0
0x2c288  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x2c28d  ldc.i4.0
0x2c28e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x2c293  ldarg.0
0x2c294  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x2c299  ldc.i4.1
0x2c29a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2c29f  ldarg.0
0x2c2a0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x2c2a5  ldc.i4.0
0x2c2a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x2c2ab  ldarg.0
0x2c2ac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x2c2b1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0x2c2b6  ldarg.0
0x2c2b7  ldarg.0
0x2c2b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0x2c2bd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>2__current
0x2c2c2  ldarg.0
0x2c2c3  ldc.i4.3
0x2c2c4  stfld    int32 <GetMethods>d__7::<>1__state
0x2c2c9  ldc.i4.1
0x2c2ca  stloc.0
0x2c2cb  leave    loc_2C679
0x2c2d0  ldarg.0
0x2c2d1  ldc.i4.m1
0x2c2d2  stfld    int32 <GetMethods>d__7::<>1__state
0x2c2d7  ldarg.0
0x2c2d8  ldarg.0
0x2c2d9  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x2c2de  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x2c2e3  ldarg.0
0x2c2e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x2c2e9  ldstr    aGetpeerurl// "GetPeerUrl"
0x2c2ee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x2c2f3  ldarg.0
0x2c2f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x2c2f9  ldc.i4.1
0x2c2fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x2c2ff  ldarg.0
0x2c300  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x2c305  ldc.i4.0
0x2c306  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x2c30b  ldarg.0
0x2c30c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x2c311  ldc.i4.7
0x2c312  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x2c317  ldarg.0
0x2c318  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x2c31d  ldstr    aGetpeerurl// "GetPeerUrl"
0x2c322  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x2c327  ldarg.0
0x2c328  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x2c32d  ldc.i4.0
0x2c32e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x2c333  ldarg.0
0x2c334  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x2c339  ldtoken  [mscorlib]System.String
0x2c33e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2c343  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x2c348  ldarg.0
0x2c349  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x2c34e  ldc.i4.1
0x2c34f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2c354  ldarg.0
0x2c355  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x2c35a  ldc.i4.0
0x2c35b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x2c360  ldarg.0
0x2c361  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x2c366  ldc.i4.0
0x2c367  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x2c36c  ldarg.0
0x2c36d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x2c372  ldc.i4.1
0x2c373  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2c378  ldarg.0
0x2c379  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x2c37e  ldc.i4.0
0x2c37f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x2c384  ldarg.0
0x2c385  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x2c38a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0x2c38f  ldarg.0
0x2c390  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0x2c395  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x2c39a  ldarg.0
0x2c39b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x2c3a0  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal2
0x2c3a5  ldarg.0
0x2c3a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal2
0x2c3ab  ldstr    aCurrenturl// "currentUrl"
0x2c3b0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x2c3b5  ldarg.0
0x2c3b6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal2
0x2c3bb  ldc.i4.0
0x2c3bc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x2c3c1  ldarg.0
0x2c3c2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal2
0x2c3c7  ldtoken  [mscorlib]System.String
0x2c3cc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2c3d1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x2c3d6  ldarg.0
0x2c3d7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal2
0x2c3dc  ldc.i4.1
0x2c3dd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2c3e2  ldarg.0
0x2c3e3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal2
0x2c3e8  ldc.i4.0
0x2c3e9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x2c3ee  ldarg.0
0x2c3ef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal2
0x2c3f4  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x2c3f9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x2c3fe  ldarg.0
0x2c3ff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal2
0x2c404  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x2c409  ldarg.0
0x2c40a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0x2c40f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x2c414  ldarg.0
0x2c415  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x2c41a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal3
0x2c41f  ldarg.0
0x2c420  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal3
0x2c425  ldstr    aLabeltitle// "labelTitle"
0x2c42a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x2c42f  ldarg.0
0x2c430  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal3
0x2c435  ldc.i4.0
0x2c436  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x2c43b  ldarg.0
0x2c43c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal3
0x2c441  ldtoken  [mscorlib]System.String
0x2c446  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2c44b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x2c450  ldarg.0
0x2c451  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal3
0x2c456  ldc.i4.1
0x2c457  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2c45c  ldarg.0
0x2c45d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal3
0x2c462  ldc.i4.0
0x2c463  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x2c468  ldarg.0
0x2c469  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal3
0x2c46e  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x2c473  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x2c478  ldarg.0
0x2c479  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal3
0x2c47e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x2c483  ldarg.0
0x2c484  ldarg.0
0x2c485  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0x2c48a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>2__current
0x2c48f  ldarg.0
0x2c490  ldc.i4.4
0x2c491  stfld    int32 <GetMethods>d__7::<>1__state
0x2c496  ldc.i4.1
0x2c497  stloc.0
0x2c498  leave    loc_2C679
0x2c49d  ldarg.0
0x2c49e  ldc.i4.m1
0x2c49f  stfld    int32 <GetMethods>d__7::<>1__state
0x2c4a4  ldarg.0
0x2c4a5  ldarg.0
0x2c4a6  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x2c4ab  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal4
0x2c4b0  ldarg.0
0x2c4b1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal4
0x2c4b6  ldstr    aUpdatelistitem// "UpdateListItems"
0x2c4bb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x2c4c0  ldarg.0
0x2c4c1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal4
0x2c4c6  ldc.i4.1
0x2c4c7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x2c4cc  ldarg.0
0x2c4cd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal4
0x2c4d2  ldc.i4.0
0x2c4d3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x2c4d8  ldarg.0
0x2c4d9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal4
0x2c4de  ldc.i4.7
0x2c4df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x2c4e4  ldarg.0
0x2c4e5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal4
0x2c4ea  ldstr    aUpdatelistitem// "UpdateListItems"
0x2c4ef  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x2c4f4  ldarg.0
0x2c4f5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal4
0x2c4fa  ldc.i4.0
0x2c4fb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x2c500  ldarg.0
0x2c501  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal4
0x2c506  ldtoken  [mscorlib]System.Void
0x2c50b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2c510  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x2c515  ldarg.0
0x2c516  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal4
0x2c51b  ldc.i4.0
0x2c51c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2c521  ldarg.0
0x2c522  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal4
0x2c527  ldc.i4.0
0x2c528  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x2c52d  ldarg.0
0x2c52e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal4
  ... truncated ...
```
