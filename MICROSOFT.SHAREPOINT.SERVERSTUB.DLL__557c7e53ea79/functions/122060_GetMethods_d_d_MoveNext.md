# <GetMethods>d__d::MoveNext

- ea: `0x122060`
- end: `0x122a0c`
- name: `<GetMethods>d__d::MoveNext`
- size: `2476`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callees

- `0x4dbc0`
- `0x122060`
- `0x122a30`
- `0x122a90`

## string_xrefs

- `0x122612`: `Update`
- `0x12264a`: `Update`
- `0x122723`: `Update`
- `0x122130`: `DeleteObject`
- `0x122168`: `Delete`
- `0x1226ef`: `UpdateAndPushChanges`

## pseudocode

```c

```

## disassembly

```asm
0x122060  ldarg.0
0x122061  ldfld    int32 <GetMethods>d__d::<>1__state
0x122066  stloc.1
0x122067  ldloc.1
0x122068  switch   loc_12209A, loc_1229FF, loc_122104, loc_1221F4, loc_12234B, loc_1224A2, loc_1225F9, loc_1226D6, loc_122829, loc_1229F8
0x122095  br       loc_1229FF
0x12209a  ldarg.0
0x12209b  ldc.i4.m1
0x12209c  stfld    int32 <GetMethods>d__d::<>1__state
0x1220a1  ldarg.0
0x1220a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__d::proxyContext
0x1220a7  brtrue.s loc_1220B4
0x1220a9  ldstr    aProxycontext// "proxyContext"
0x1220ae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1220b3  throw
0x1220b4  ldarg.0
0x1220b5  ldarg.0
0x1220b6  ldfld    class Microsoft.SharePoint.ServerStub.SPFieldServerStub <GetMethods>d__d::<>4__this
0x1220bb  ldarg.0
0x1220bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__d::proxyContext
0x1220c1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPFieldServerStub::<>n__FabricatedMethod12(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x1220c6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x1220cb  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__d::<>7__wrap10
0x1220d0  ldarg.0
0x1220d1  ldc.i4.1
0x1220d2  stfld    int32 <GetMethods>d__d::<>1__state
0x1220d7  br.s     loc_12210B
0x1220d9  ldarg.0
0x1220da  ldarg.0
0x1220db  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__d::<>7__wrap10
0x1220e0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x1220e5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<itemBase>5__e
0x1220ea  ldarg.0
0x1220eb  ldarg.0
0x1220ec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<itemBase>5__e
0x1220f1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>2__current
0x1220f6  ldarg.0
0x1220f7  ldc.i4.2
0x1220f8  stfld    int32 <GetMethods>d__d::<>1__state
0x1220fd  ldc.i4.1
0x1220fe  stloc.0
0x1220ff  leave    loc_122A0A
0x122104  ldarg.0
0x122105  ldc.i4.1
0x122106  stfld    int32 <GetMethods>d__d::<>1__state
0x12210b  ldarg.0
0x12210c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__d::<>7__wrap10
0x122111  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x122116  brtrue.s loc_1220D9
0x122118  ldarg.0
0x122119  call     instance void <GetMethods>d__d::<>m__Finally11()
0x12211e  ldarg.0
0x12211f  ldarg.0
0x122120  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x122125  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x12212a  ldarg.0
0x12212b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x122130  ldstr    aDeleteobject// "DeleteObject"
0x122135  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x12213a  ldarg.0
0x12213b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x122140  ldc.i4.0
0x122141  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x122146  ldarg.0
0x122147  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x12214c  ldc.i4.0
0x12214d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x122152  ldarg.0
0x122153  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x122158  ldc.i4   0xFFFFFFF
0x12215d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x122162  ldarg.0
0x122163  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x122168  ldstr    aDelete// "Delete"
0x12216d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x122172  ldarg.0
0x122173  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x122178  ldc.i4.0
0x122179  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x12217e  ldarg.0
0x12217f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x122184  ldtoken  [mscorlib]System.Void
0x122189  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12218e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x122193  ldarg.0
0x122194  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x122199  ldc.i4.0
0x12219a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x12219f  ldarg.0
0x1221a0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x1221a5  ldc.i4.0
0x1221a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1221ab  ldarg.0
0x1221ac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x1221b1  ldc.i4.0
0x1221b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1221b7  ldarg.0
0x1221b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x1221bd  ldc.i4.0
0x1221be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1221c3  ldarg.0
0x1221c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x1221c9  ldc.i4.0
0x1221ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1221cf  ldarg.0
0x1221d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal0
0x1221d5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<item>5__f
0x1221da  ldarg.0
0x1221db  ldarg.0
0x1221dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<item>5__f
0x1221e1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>2__current
0x1221e6  ldarg.0
0x1221e7  ldc.i4.3
0x1221e8  stfld    int32 <GetMethods>d__d::<>1__state
0x1221ed  ldc.i4.1
0x1221ee  stloc.0
0x1221ef  leave    loc_122A0A
0x1221f4  ldarg.0
0x1221f5  ldc.i4.m1
0x1221f6  stfld    int32 <GetMethods>d__d::<>1__state
0x1221fb  ldarg.0
0x1221fc  ldarg.0
0x1221fd  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x122202  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x122207  ldarg.0
0x122208  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x12220d  ldstr    aSetshowindispl// "SetShowInDisplayForm"
0x122212  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x122217  ldarg.0
0x122218  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x12221d  ldc.i4.0
0x12221e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x122223  ldarg.0
0x122224  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x122229  ldc.i4.0
0x12222a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x12222f  ldarg.0
0x122230  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x122235  ldc.i4   0xFFFFFFF
0x12223a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x12223f  ldarg.0
0x122240  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x122245  ldstr    aSetshowindispl// "SetShowInDisplayForm"
0x12224a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x12224f  ldarg.0
0x122250  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x122255  ldc.i4.0
0x122256  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x12225b  ldarg.0
0x12225c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x122261  ldtoken  [mscorlib]System.Void
0x122266  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12226b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x122270  ldarg.0
0x122271  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x122276  ldc.i4.0
0x122277  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x12227c  ldarg.0
0x12227d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x122282  ldc.i4.0
0x122283  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x122288  ldarg.0
0x122289  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x12228e  ldc.i4.0
0x12228f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x122294  ldarg.0
0x122295  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x12229a  ldc.i4.0
0x12229b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1222a0  ldarg.0
0x1222a1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x1222a6  ldc.i4.0
0x1222a7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1222ac  ldarg.0
0x1222ad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal1
0x1222b2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<item>5__f
0x1222b7  ldarg.0
0x1222b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<item>5__f
0x1222bd  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1222c2  ldarg.0
0x1222c3  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1222c8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal2
0x1222cd  ldarg.0
0x1222ce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal2
0x1222d3  ldstr    aValue// "value"
0x1222d8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1222dd  ldarg.0
0x1222de  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal2
0x1222e3  ldc.i4.0
0x1222e4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1222e9  ldarg.0
0x1222ea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal2
0x1222ef  ldtoken  [mscorlib]System.Boolean
0x1222f4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1222f9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1222fe  ldarg.0
0x1222ff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal2
0x122304  ldc.i4.1
0x122305  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x12230a  ldarg.0
0x12230b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal2
0x122310  ldc.i4.0
0x122311  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x122316  ldarg.0
0x122317  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal2
0x12231c  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x122321  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x122326  ldarg.0
0x122327  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal2
0x12232c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x122331  ldarg.0
0x122332  ldarg.0
0x122333  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<item>5__f
0x122338  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>2__current
0x12233d  ldarg.0
0x12233e  ldc.i4.4
0x12233f  stfld    int32 <GetMethods>d__d::<>1__state
0x122344  ldc.i4.1
0x122345  stloc.0
0x122346  leave    loc_122A0A
0x12234b  ldarg.0
0x12234c  ldc.i4.m1
0x12234d  stfld    int32 <GetMethods>d__d::<>1__state
0x122352  ldarg.0
0x122353  ldarg.0
0x122354  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x122359  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x12235e  ldarg.0
0x12235f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x122364  ldstr    aSetshowineditf// "SetShowInEditForm"
0x122369  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x12236e  ldarg.0
0x12236f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x122374  ldc.i4.0
0x122375  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x12237a  ldarg.0
0x12237b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x122380  ldc.i4.0
0x122381  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x122386  ldarg.0
0x122387  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x12238c  ldc.i4   0xFFFFFFF
0x122391  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x122396  ldarg.0
0x122397  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x12239c  ldstr    aSetshowineditf// "SetShowInEditForm"
0x1223a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1223a6  ldarg.0
0x1223a7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x1223ac  ldc.i4.0
0x1223ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1223b2  ldarg.0
0x1223b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x1223b8  ldtoken  [mscorlib]System.Void
0x1223bd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1223c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1223c7  ldarg.0
0x1223c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x1223cd  ldc.i4.0
0x1223ce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1223d3  ldarg.0
0x1223d4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x1223d9  ldc.i4.0
0x1223da  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1223df  ldarg.0
0x1223e0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x1223e5  ldc.i4.0
0x1223e6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1223eb  ldarg.0
0x1223ec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x1223f1  ldc.i4.0
0x1223f2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1223f7  ldarg.0
0x1223f8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x1223fd  ldc.i4.0
0x1223fe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x122403  ldarg.0
0x122404  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<>g__initLocal3
0x122409  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<item>5__f
0x12240e  ldarg.0
0x12240f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__d::<item>5__f
0x122414  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x122419  ldarg.0
0x12241a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x12241f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal4
0x122424  ldarg.0
0x122425  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal4
0x12242a  ldstr    aValue// "value"
0x12242f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x122434  ldarg.0
0x122435  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal4
0x12243a  ldc.i4.0
0x12243b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x122440  ldarg.0
0x122441  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal4
0x122446  ldtoken  [mscorlib]System.Boolean
0x12244b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x122450  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x122455  ldarg.0
0x122456  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__d::<>g__initLocal4
  ... truncated ...
```
