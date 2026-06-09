# <GetMethods>d__d::MoveNext_0

- ea: `0x135460`
- end: `0x135e10`
- name: `<GetMethods>d__d::MoveNext_0`
- size: `2480`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x5bbe0`
- `0x135460`
- `0x135e30`
- `0x135e90`

## string_xrefs

- `0x135530`: `DeleteAll`
- `0x135568`: `DeleteAll`
- `0x13560d`: `DeleteByID`
- `0x135645`: `DeleteByID`
- `0x135764`: `DeleteByLabel`
- `0x13579c`: `DeleteByLabel`

## pseudocode

```c

```

## disassembly

```asm
0x135460  ldarg.0
0x135461  ldfld    int32 <GetMethods>d__d::<>1__state
0x135466  stloc.1
0x135467  ldloc.1
0x135468  switch   loc_13549A, loc_135E03, loc_135504, loc_1355F4, loc_13574B, loc_1358A2, loc_1359F9, loc_135B50, loc_135CA7, loc_135DFC
0x135495  br       loc_135E03
0x13549a  ldarg.0
0x13549b  ldc.i4.m1
0x13549c  stfld    int32 <GetMethods>d__d::<>1__state
0x1354a1  ldarg.0
0x1354a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__d::proxyContext
0x1354a7  brtrue.s loc_1354B4
0x1354a9  ldstr    aProxycontext// "proxyContext"
0x1354ae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1354b3  throw
0x1354b4  ldarg.0
0x1354b5  ldarg.0
0x1354b6  ldfld    class Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub <GetMethods>d__d::<>4__this
0x1354bb  ldarg.0
0x1354bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__d::proxyContext
0x1354c1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::<>n__FabricatedMethod12(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext name)
0x1354c6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x1354cb  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__d::<>7__wrap10
0x1354d0  ldarg.0
0x1354d1  ldc.i4.1
0x1354d2  stfld    int32 <GetMethods>d__d::<>1__state
0x1354d7  br.s     loc_13550B
0x1354d9  ldarg.0
0x1354da  ldarg.0
0x1354db  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__d::<>7__wrap10
0x1354e0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x1354e5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<itemBase>5__e
0x1354ea  ldarg.0
0x1354eb  ldarg.0
0x1354ec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<itemBase>5__e
0x1354f1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>2__current
0x1354f6  ldarg.0
0x1354f7  ldc.i4.2
0x1354f8  stfld    int32 <GetMethods>d__d::<>1__state
0x1354fd  ldc.i4.1
0x1354fe  stloc.0
0x1354ff  leave    loc_135E0E
0x135504  ldarg.0
0x135505  ldc.i4.1
0x135506  stfld    int32 <GetMethods>d__d::<>1__state
0x13550b  ldarg.0
0x13550c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__d::<>7__wrap10
0x135511  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x135516  brtrue.s loc_1354D9
0x135518  ldarg.0
0x135519  call     instance void <GetMethods>d__d::<>m__Finally11()
0x13551e  ldarg.0
0x13551f  ldarg.0
0x135520  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x135525  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x13552a  ldarg.0
0x13552b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x135530  ldstr    aDeleteall// "DeleteAll"
0x135535  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x13553a  ldarg.0
0x13553b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x135540  ldc.i4.0
0x135541  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x135546  ldarg.0
0x135547  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x13554c  ldc.i4.0
0x13554d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x135552  ldarg.0
0x135553  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x135558  ldc.i4   0xFFFFFFF
0x13555d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x135562  ldarg.0
0x135563  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x135568  ldstr    aDeleteall// "DeleteAll"
0x13556d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x135572  ldarg.0
0x135573  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x135578  ldc.i4.0
0x135579  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x13557e  ldarg.0
0x13557f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x135584  ldtoken  [mscorlib]System.Void
0x135589  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13558e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x135593  ldarg.0
0x135594  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x135599  ldc.i4.0
0x13559a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13559f  ldarg.0
0x1355a0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x1355a5  ldc.i4.0
0x1355a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1355ab  ldarg.0
0x1355ac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x1355b1  ldc.i4.0
0x1355b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1355b7  ldarg.0
0x1355b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x1355bd  ldc.i4.0
0x1355be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1355c3  ldarg.0
0x1355c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x1355c9  ldc.i4.0
0x1355ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1355cf  ldarg.0
0x1355d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x1355d5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<item>5__f
0x1355da  ldarg.0
0x1355db  ldarg.0
0x1355dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<item>5__f
0x1355e1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>2__current
0x1355e6  ldarg.0
0x1355e7  ldc.i4.3
0x1355e8  stfld    int32 <GetMethods>d__d::<>1__state
0x1355ed  ldc.i4.1
0x1355ee  stloc.0
0x1355ef  leave    loc_135E0E
0x1355f4  ldarg.0
0x1355f5  ldc.i4.m1
0x1355f6  stfld    int32 <GetMethods>d__d::<>1__state
0x1355fb  ldarg.0
0x1355fc  ldarg.0
0x1355fd  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x135602  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x135607  ldarg.0
0x135608  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x13560d  ldstr    aDeletebyid// "DeleteByID"
0x135612  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x135617  ldarg.0
0x135618  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x13561d  ldc.i4.0
0x13561e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x135623  ldarg.0
0x135624  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x135629  ldc.i4.0
0x13562a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x13562f  ldarg.0
0x135630  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x135635  ldc.i4   0xFFFFFFF
0x13563a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x13563f  ldarg.0
0x135640  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x135645  ldstr    aDeletebyid// "DeleteByID"
0x13564a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x13564f  ldarg.0
0x135650  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x135655  ldc.i4.0
0x135656  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x13565b  ldarg.0
0x13565c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x135661  ldtoken  [mscorlib]System.Void
0x135666  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13566b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x135670  ldarg.0
0x135671  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x135676  ldc.i4.0
0x135677  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13567c  ldarg.0
0x13567d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x135682  ldc.i4.0
0x135683  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x135688  ldarg.0
0x135689  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x13568e  ldc.i4.0
0x13568f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x135694  ldarg.0
0x135695  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x13569a  ldc.i4.0
0x13569b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1356a0  ldarg.0
0x1356a1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x1356a6  ldc.i4.0
0x1356a7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1356ac  ldarg.0
0x1356ad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x1356b2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<item>5__f
0x1356b7  ldarg.0
0x1356b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<item>5__f
0x1356bd  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1356c2  ldarg.0
0x1356c3  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1356c8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal2
0x1356cd  ldarg.0
0x1356ce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal2
0x1356d3  ldstr    aVid// "vid"
0x1356d8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1356dd  ldarg.0
0x1356de  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal2
0x1356e3  ldc.i4.0
0x1356e4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1356e9  ldarg.0
0x1356ea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal2
0x1356ef  ldtoken  [mscorlib]System.Int32
0x1356f4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1356f9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1356fe  ldarg.0
0x1356ff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal2
0x135704  ldc.i4.1
0x135705  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13570a  ldarg.0
0x13570b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal2
0x135710  ldc.i4.0
0x135711  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x135716  ldarg.0
0x135717  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal2
0x13571c  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x135721  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x135726  ldarg.0
0x135727  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal2
0x13572c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x135731  ldarg.0
0x135732  ldarg.0
0x135733  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<item>5__f
0x135738  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>2__current
0x13573d  ldarg.0
0x13573e  ldc.i4.4
0x13573f  stfld    int32 <GetMethods>d__d::<>1__state
0x135744  ldc.i4.1
0x135745  stloc.0
0x135746  leave    loc_135E0E
0x13574b  ldarg.0
0x13574c  ldc.i4.m1
0x13574d  stfld    int32 <GetMethods>d__d::<>1__state
0x135752  ldarg.0
0x135753  ldarg.0
0x135754  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x135759  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x13575e  ldarg.0
0x13575f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x135764  ldstr    aDeletebylabel// "DeleteByLabel"
0x135769  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x13576e  ldarg.0
0x13576f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x135774  ldc.i4.0
0x135775  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x13577a  ldarg.0
0x13577b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x135780  ldc.i4.0
0x135781  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x135786  ldarg.0
0x135787  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x13578c  ldc.i4   0xFFFFFFF
0x135791  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x135796  ldarg.0
0x135797  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x13579c  ldstr    aDeletebylabel// "DeleteByLabel"
0x1357a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1357a6  ldarg.0
0x1357a7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x1357ac  ldc.i4.0
0x1357ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1357b2  ldarg.0
0x1357b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x1357b8  ldtoken  [mscorlib]System.Void
0x1357bd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1357c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1357c7  ldarg.0
0x1357c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x1357cd  ldc.i4.0
0x1357ce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1357d3  ldarg.0
0x1357d4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x1357d9  ldc.i4.0
0x1357da  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1357df  ldarg.0
0x1357e0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x1357e5  ldc.i4.0
0x1357e6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1357eb  ldarg.0
0x1357ec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x1357f1  ldc.i4.0
0x1357f2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1357f7  ldarg.0
0x1357f8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x1357fd  ldc.i4.0
0x1357fe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x135803  ldarg.0
0x135804  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x135809  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<item>5__f
0x13580e  ldarg.0
0x13580f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<item>5__f
0x135814  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x135819  ldarg.0
0x13581a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x13581f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal4
0x135824  ldarg.0
0x135825  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal4
0x13582a  ldstr    aVersionlabel// "versionlabel"
0x13582f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x135834  ldarg.0
0x135835  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal4
0x13583a  ldc.i4.0
0x13583b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x135840  ldarg.0
0x135841  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal4
0x135846  ldtoken  [mscorlib]System.String
0x13584b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x135850  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x135855  ldarg.0
0x135856  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal4
  ... truncated ...
```
