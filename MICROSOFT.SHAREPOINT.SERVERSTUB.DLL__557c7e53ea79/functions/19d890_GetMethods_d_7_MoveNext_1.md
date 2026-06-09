# <GetMethods>d__7::MoveNext_1

- ea: `0x19d890`
- end: `0x19de95`
- name: `<GetMethods>d__7::MoveNext_1`
- size: `1541`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xa5060`
- `0x19d890`
- `0x19dec0`
- `0x19df20`

## string_xrefs

- `0x19dce3`: `OpenWebPart`
- `0x19dd1b`: `OpenWebPart`
- `0x19da35`: `DeleteWebPart`
- `0x19da6d`: `DeleteWebPart`
- `0x19db12`: `MoveWebPartTo`
- `0x19db4a`: `MoveWebPartTo`

## pseudocode

```c

```

## disassembly

```asm
0x19d890  ldarg.0
0x19d891  ldfld    int32 <GetMethods>d__7::<>1__state
0x19d896  stloc.1
0x19d897  ldloc.1
0x19d898  switch   loc_19D8C2, loc_19DE88, loc_19D92C, loc_19DA1C, loc_19DAF9, loc_19DCCA, loc_19DDA7, loc_19DE81
0x19d8bd  br       loc_19DE88
0x19d8c2  ldarg.0
0x19d8c3  ldc.i4.m1
0x19d8c4  stfld    int32 <GetMethods>d__7::<>1__state
0x19d8c9  ldarg.0
0x19d8ca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__7::proxyContext
0x19d8cf  brtrue.s loc_19D8DC
0x19d8d1  ldstr    aProxycontext// "proxyContext"
0x19d8d6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x19d8db  throw
0x19d8dc  ldarg.0
0x19d8dd  ldarg.0
0x19d8de  ldfld    class Microsoft.SharePoint.ServerStub.WebParts.SPWebPartDefinitionServerStub <GetMethods>d__7::<>4__this
0x19d8e3  ldarg.0
0x19d8e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__7::proxyContext
0x19d8e9  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.WebParts.SPWebPartDefinitionServerStub::<>n__FabricatedMethodc(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x19d8ee  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x19d8f3  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__7::<>7__wrapa
0x19d8f8  ldarg.0
0x19d8f9  ldc.i4.1
0x19d8fa  stfld    int32 <GetMethods>d__7::<>1__state
0x19d8ff  br.s     loc_19D933
0x19d901  ldarg.0
0x19d902  ldarg.0
0x19d903  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__7::<>7__wrapa
0x19d908  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x19d90d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<itemBase>5__8
0x19d912  ldarg.0
0x19d913  ldarg.0
0x19d914  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<itemBase>5__8
0x19d919  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>2__current
0x19d91e  ldarg.0
0x19d91f  ldc.i4.2
0x19d920  stfld    int32 <GetMethods>d__7::<>1__state
0x19d925  ldc.i4.1
0x19d926  stloc.0
0x19d927  leave    loc_19DE93
0x19d92c  ldarg.0
0x19d92d  ldc.i4.1
0x19d92e  stfld    int32 <GetMethods>d__7::<>1__state
0x19d933  ldarg.0
0x19d934  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__7::<>7__wrapa
0x19d939  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19d93e  brtrue.s loc_19D901
0x19d940  ldarg.0
0x19d941  call     instance void <GetMethods>d__7::<>m__Finallyb()
0x19d946  ldarg.0
0x19d947  ldarg.0
0x19d948  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x19d94d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x19d952  ldarg.0
0x19d953  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x19d958  ldstr    aClosewebpart// "CloseWebPart"
0x19d95d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x19d962  ldarg.0
0x19d963  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x19d968  ldc.i4.0
0x19d969  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x19d96e  ldarg.0
0x19d96f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x19d974  ldc.i4.0
0x19d975  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x19d97a  ldarg.0
0x19d97b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x19d980  ldc.i4   0xFFFFFFF
0x19d985  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x19d98a  ldarg.0
0x19d98b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x19d990  ldstr    aClosewebpart// "CloseWebPart"
0x19d995  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x19d99a  ldarg.0
0x19d99b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x19d9a0  ldc.i4.0
0x19d9a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x19d9a6  ldarg.0
0x19d9a7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x19d9ac  ldtoken  [mscorlib]System.Void
0x19d9b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19d9b6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x19d9bb  ldarg.0
0x19d9bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x19d9c1  ldc.i4.0
0x19d9c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x19d9c7  ldarg.0
0x19d9c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x19d9cd  ldc.i4.0
0x19d9ce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x19d9d3  ldarg.0
0x19d9d4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x19d9d9  ldc.i4.0
0x19d9da  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x19d9df  ldarg.0
0x19d9e0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x19d9e5  ldc.i4.0
0x19d9e6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x19d9eb  ldarg.0
0x19d9ec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x19d9f1  ldc.i4.0
0x19d9f2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x19d9f7  ldarg.0
0x19d9f8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal0
0x19d9fd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0x19da02  ldarg.0
0x19da03  ldarg.0
0x19da04  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0x19da09  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>2__current
0x19da0e  ldarg.0
0x19da0f  ldc.i4.3
0x19da10  stfld    int32 <GetMethods>d__7::<>1__state
0x19da15  ldc.i4.1
0x19da16  stloc.0
0x19da17  leave    loc_19DE93
0x19da1c  ldarg.0
0x19da1d  ldc.i4.m1
0x19da1e  stfld    int32 <GetMethods>d__7::<>1__state
0x19da23  ldarg.0
0x19da24  ldarg.0
0x19da25  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x19da2a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x19da2f  ldarg.0
0x19da30  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x19da35  ldstr    aDeletewebpart// "DeleteWebPart"
0x19da3a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x19da3f  ldarg.0
0x19da40  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x19da45  ldc.i4.0
0x19da46  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x19da4b  ldarg.0
0x19da4c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x19da51  ldc.i4.0
0x19da52  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x19da57  ldarg.0
0x19da58  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x19da5d  ldc.i4   0xFFFFFFF
0x19da62  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x19da67  ldarg.0
0x19da68  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x19da6d  ldstr    aDeletewebpart// "DeleteWebPart"
0x19da72  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x19da77  ldarg.0
0x19da78  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x19da7d  ldc.i4.0
0x19da7e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x19da83  ldarg.0
0x19da84  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x19da89  ldtoken  [mscorlib]System.Void
0x19da8e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19da93  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x19da98  ldarg.0
0x19da99  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x19da9e  ldc.i4.0
0x19da9f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x19daa4  ldarg.0
0x19daa5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x19daaa  ldc.i4.0
0x19daab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x19dab0  ldarg.0
0x19dab1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x19dab6  ldc.i4.0
0x19dab7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x19dabc  ldarg.0
0x19dabd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x19dac2  ldc.i4.0
0x19dac3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x19dac8  ldarg.0
0x19dac9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x19dace  ldc.i4.0
0x19dacf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x19dad4  ldarg.0
0x19dad5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal1
0x19dada  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0x19dadf  ldarg.0
0x19dae0  ldarg.0
0x19dae1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0x19dae6  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>2__current
0x19daeb  ldarg.0
0x19daec  ldc.i4.4
0x19daed  stfld    int32 <GetMethods>d__7::<>1__state
0x19daf2  ldc.i4.1
0x19daf3  stloc.0
0x19daf4  leave    loc_19DE93
0x19daf9  ldarg.0
0x19dafa  ldc.i4.m1
0x19dafb  stfld    int32 <GetMethods>d__7::<>1__state
0x19db00  ldarg.0
0x19db01  ldarg.0
0x19db02  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x19db07  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0x19db0c  ldarg.0
0x19db0d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0x19db12  ldstr    aMovewebpartto// "MoveWebPartTo"
0x19db17  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x19db1c  ldarg.0
0x19db1d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0x19db22  ldc.i4.0
0x19db23  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x19db28  ldarg.0
0x19db29  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0x19db2e  ldc.i4.0
0x19db2f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x19db34  ldarg.0
0x19db35  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0x19db3a  ldc.i4   0xFFFFFFF
0x19db3f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x19db44  ldarg.0
0x19db45  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0x19db4a  ldstr    aMovewebpartto// "MoveWebPartTo"
0x19db4f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x19db54  ldarg.0
0x19db55  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0x19db5a  ldc.i4.0
0x19db5b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x19db60  ldarg.0
0x19db61  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0x19db66  ldtoken  [mscorlib]System.Void
0x19db6b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19db70  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x19db75  ldarg.0
0x19db76  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0x19db7b  ldc.i4.0
0x19db7c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x19db81  ldarg.0
0x19db82  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0x19db87  ldc.i4.0
0x19db88  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x19db8d  ldarg.0
0x19db8e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0x19db93  ldc.i4.0
0x19db94  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x19db99  ldarg.0
0x19db9a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0x19db9f  ldc.i4.0
0x19dba0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x19dba5  ldarg.0
0x19dba6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0x19dbab  ldc.i4.0
0x19dbac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x19dbb1  ldarg.0
0x19dbb2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<>g__initLocal2
0x19dbb7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0x19dbbc  ldarg.0
0x19dbbd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0x19dbc2  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x19dbc7  ldarg.0
0x19dbc8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x19dbcd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal3
0x19dbd2  ldarg.0
0x19dbd3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal3
0x19dbd8  ldstr    aZoneid_1// "zoneID"
0x19dbdd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x19dbe2  ldarg.0
0x19dbe3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal3
0x19dbe8  ldc.i4.0
0x19dbe9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x19dbee  ldarg.0
0x19dbef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal3
0x19dbf4  ldtoken  [mscorlib]System.String
0x19dbf9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19dbfe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x19dc03  ldarg.0
0x19dc04  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal3
0x19dc09  ldc.i4.1
0x19dc0a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x19dc0f  ldarg.0
0x19dc10  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal3
0x19dc15  ldc.i4.0
0x19dc16  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x19dc1b  ldarg.0
0x19dc1c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal3
0x19dc21  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x19dc26  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x19dc2b  ldarg.0
0x19dc2c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal3
0x19dc31  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x19dc36  ldarg.0
0x19dc37  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__7::<item>5__9
0x19dc3c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x19dc41  ldarg.0
0x19dc42  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x19dc47  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal4
0x19dc4c  ldarg.0
0x19dc4d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal4
0x19dc52  ldstr    aZoneindex// "zoneIndex"
0x19dc57  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x19dc5c  ldarg.0
0x19dc5d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal4
0x19dc62  ldc.i4.0
0x19dc63  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x19dc68  ldarg.0
0x19dc69  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal4
0x19dc6e  ldtoken  [mscorlib]System.Int32
0x19dc73  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19dc78  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x19dc7d  ldarg.0
0x19dc7e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__7::<>g__initLocal4
  ... truncated ...
```
