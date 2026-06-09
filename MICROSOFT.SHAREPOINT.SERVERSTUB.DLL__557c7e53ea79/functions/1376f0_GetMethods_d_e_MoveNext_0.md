# <GetMethods>d__e::MoveNext_0

- ea: `0x1376f0`
- end: `0x1380af`
- name: `<GetMethods>d__e::MoveNext_0`
- size: `2495`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x5d890`
- `0x1376f0`
- `0x1380d0`
- `0x138130`

## string_xrefs

- `0x137cb5`: `Create`
- `0x137cea`: `Create_Client`
- `0x137913`: `AddUsingPath`
- `0x137e09`: `GetByPath`
- `0x137e41`: `GetByPath_Client`
- `0x137ae4`: `AddWithOverwrite`
- `0x137b1c`: `AddWithOverwrite`
- `0x137c24`: `overwrite`

## pseudocode

```c

```

## disassembly

```asm
0x1376f0  ldarg.0
0x1376f1  ldfld    int32 <GetMethods>d__e::<>1__state
0x1376f6  stloc.1
0x1376f7  ldloc.1
0x1376f8  switch   loc_137726, loc_1380A2, loc_137790, loc_1378FA, loc_137ACB, loc_137C9C, loc_137DF0, loc_137F47, loc_13809B
0x137721  br       loc_1380A2
0x137726  ldarg.0
0x137727  ldc.i4.m1
0x137728  stfld    int32 <GetMethods>d__e::<>1__state
0x13772d  ldarg.0
0x13772e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__e::proxyContext
0x137733  brtrue.s loc_137740
0x137735  ldstr    aProxycontext// "proxyContext"
0x13773a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13773f  throw
0x137740  ldarg.0
0x137741  ldarg.0
0x137742  ldfld    class Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub <GetMethods>d__e::<>4__this
0x137747  ldarg.0
0x137748  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__e::proxyContext
0x13774d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub::<>n__FabricatedMethod13(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x137752  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x137757  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__e::<>7__wrap11
0x13775c  ldarg.0
0x13775d  ldc.i4.1
0x13775e  stfld    int32 <GetMethods>d__e::<>1__state
0x137763  br.s     loc_137797
0x137765  ldarg.0
0x137766  ldarg.0
0x137767  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__e::<>7__wrap11
0x13776c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x137771  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<itemBase>5__f
0x137776  ldarg.0
0x137777  ldarg.0
0x137778  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<itemBase>5__f
0x13777d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>2__current
0x137782  ldarg.0
0x137783  ldc.i4.2
0x137784  stfld    int32 <GetMethods>d__e::<>1__state
0x137789  ldc.i4.1
0x13778a  stloc.0
0x13778b  leave    loc_1380AD
0x137790  ldarg.0
0x137791  ldc.i4.1
0x137792  stfld    int32 <GetMethods>d__e::<>1__state
0x137797  ldarg.0
0x137798  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__e::<>7__wrap11
0x13779d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1377a2  brtrue.s loc_137765
0x1377a4  ldarg.0
0x1377a5  call     instance void <GetMethods>d__e::<>m__Finally12()
0x1377aa  ldarg.0
0x1377ab  ldarg.0
0x1377ac  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1377b1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x1377b6  ldarg.0
0x1377b7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x1377bc  ldstr    aAdd// "Add"
0x1377c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1377c6  ldarg.0
0x1377c7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x1377cc  ldc.i4.0
0x1377cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1377d2  ldarg.0
0x1377d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x1377d8  ldc.i4.0
0x1377d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1377de  ldarg.0
0x1377df  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x1377e4  ldc.i4   0xFFFFFFF
0x1377e9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1377ee  ldarg.0
0x1377ef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x1377f4  ldstr    aAdd// "Add"
0x1377f9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1377fe  ldarg.0
0x1377ff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x137804  ldc.i4.0
0x137805  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x13780a  ldarg.0
0x13780b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x137810  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder
0x137815  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13781a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x13781f  ldarg.0
0x137820  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x137825  ldc.i4.4
0x137826  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13782b  ldarg.0
0x13782c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x137831  ldc.i4.0
0x137832  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x137837  ldarg.0
0x137838  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x13783d  ldc.i4.0
0x13783e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x137843  ldarg.0
0x137844  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x137849  ldc.i4.0
0x13784a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x13784f  ldarg.0
0x137850  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x137855  ldc.i4.0
0x137856  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x13785b  ldarg.0
0x13785c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x137861  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<item>5__10
0x137866  ldarg.0
0x137867  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<item>5__10
0x13786c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x137871  ldarg.0
0x137872  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x137877  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal1
0x13787c  ldarg.0
0x13787d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal1
0x137882  ldstr    aUrl_0// "url"
0x137887  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x13788c  ldarg.0
0x13788d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal1
0x137892  ldc.i4.0
0x137893  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x137898  ldarg.0
0x137899  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal1
0x13789e  ldtoken  [mscorlib]System.String
0x1378a3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1378a8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1378ad  ldarg.0
0x1378ae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal1
0x1378b3  ldc.i4.1
0x1378b4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1378b9  ldarg.0
0x1378ba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal1
0x1378bf  ldc.i4.0
0x1378c0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1378c5  ldarg.0
0x1378c6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal1
0x1378cb  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1378d0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1378d5  ldarg.0
0x1378d6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal1
0x1378db  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1378e0  ldarg.0
0x1378e1  ldarg.0
0x1378e2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<item>5__10
0x1378e7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>2__current
0x1378ec  ldarg.0
0x1378ed  ldc.i4.3
0x1378ee  stfld    int32 <GetMethods>d__e::<>1__state
0x1378f3  ldc.i4.1
0x1378f4  stloc.0
0x1378f5  leave    loc_1380AD
0x1378fa  ldarg.0
0x1378fb  ldc.i4.m1
0x1378fc  stfld    int32 <GetMethods>d__e::<>1__state
0x137901  ldarg.0
0x137902  ldarg.0
0x137903  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x137908  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13790d  ldarg.0
0x13790e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x137913  ldstr    aAddusingpath// "AddUsingPath"
0x137918  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x13791d  ldarg.0
0x13791e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x137923  ldc.i4.0
0x137924  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x137929  ldarg.0
0x13792a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13792f  ldc.i4.0
0x137930  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x137935  ldarg.0
0x137936  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13793b  ldc.i4   0xFFFFFFF
0x137940  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x137945  ldarg.0
0x137946  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13794b  ldstr    aAdd// "Add"
0x137950  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x137955  ldarg.0
0x137956  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13795b  ldc.i4.0
0x13795c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x137961  ldarg.0
0x137962  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x137967  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder
0x13796c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x137971  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x137976  ldarg.0
0x137977  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13797c  ldc.i4.4
0x13797d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x137982  ldarg.0
0x137983  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x137988  ldc.i4.0
0x137989  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x13798e  ldarg.0
0x13798f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x137994  ldc.i4.0
0x137995  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x13799a  ldarg.0
0x13799b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x1379a0  ldc.i4.0
0x1379a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1379a6  ldarg.0
0x1379a7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x1379ac  ldc.i4.0
0x1379ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1379b2  ldarg.0
0x1379b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x1379b8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<item>5__10
0x1379bd  ldarg.0
0x1379be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<item>5__10
0x1379c3  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1379c8  ldarg.0
0x1379c9  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1379ce  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal3
0x1379d3  ldarg.0
0x1379d4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal3
0x1379d9  ldstr    aPath// "path"
0x1379de  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1379e3  ldarg.0
0x1379e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal3
0x1379e9  ldc.i4.1
0x1379ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1379ef  ldarg.0
0x1379f0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal3
0x1379f5  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath
0x1379fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1379ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x137a04  ldarg.0
0x137a05  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal3
0x137a0a  ldc.i4.2
0x137a0b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x137a10  ldarg.0
0x137a11  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal3
0x137a16  ldc.i4.0
0x137a17  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x137a1c  ldarg.0
0x137a1d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal3
0x137a22  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x137a27  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x137a2c  ldarg.0
0x137a2d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal3
0x137a32  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x137a37  ldarg.0
0x137a38  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<item>5__10
0x137a3d  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x137a42  ldarg.0
0x137a43  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x137a48  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal4
0x137a4d  ldarg.0
0x137a4e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal4
0x137a53  ldstr    aParameters// "parameters"
0x137a58  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x137a5d  ldarg.0
0x137a5e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal4
0x137a63  ldc.i4.1
0x137a64  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x137a69  ldarg.0
0x137a6a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal4
0x137a6f  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPFolderCreationInformation
0x137a74  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x137a79  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x137a7e  ldarg.0
0x137a7f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal4
0x137a84  ldc.i4.2
0x137a85  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x137a8a  ldarg.0
0x137a8b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal4
0x137a90  ldc.i4.0
0x137a91  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x137a96  ldarg.0
0x137a97  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal4
0x137a9c  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x137aa1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x137aa6  ldarg.0
0x137aa7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal4
0x137aac  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x137ab1  ldarg.0
0x137ab2  ldarg.0
0x137ab3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<item>5__10
0x137ab8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>2__current
0x137abd  ldarg.0
0x137abe  ldc.i4.4
0x137abf  stfld    int32 <GetMethods>d__e::<>1__state
0x137ac4  ldc.i4.1
0x137ac5  stloc.0
0x137ac6  leave    loc_1380AD
0x137acb  ldarg.0
0x137acc  ldc.i4.m1
0x137acd  stfld    int32 <GetMethods>d__e::<>1__state
0x137ad2  ldarg.0
0x137ad3  ldarg.0
0x137ad4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x137ad9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal5
0x137ade  ldarg.0
0x137adf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal5
0x137ae4  ldstr    aAddwithoverwri// "AddWithOverwrite"
0x137ae9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x137aee  ldarg.0
  ... truncated ...
```
