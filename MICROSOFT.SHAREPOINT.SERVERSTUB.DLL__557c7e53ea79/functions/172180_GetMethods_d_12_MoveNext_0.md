# <GetMethods>d__12::MoveNext_0

- ea: `0x172180`
- end: `0x172e53`
- name: `<GetMethods>d__12::MoveNext_0`
- size: `3283`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x877e0`
- `0x172180`
- `0x172e80`
- `0x172ee0`

## string_xrefs

- `0x1724fe`: `Create`
- `0x172a57`: `Remove`
- `0x172a8b`: `Remove`
- `0x172d3b`: `Remove`
- `0x172bab`: `RemoveById`
- `0x172d03`: `RemoveByLoginName`
- `0x172be3`: `RemoveByID`
- `0x172533`: `CreateUser_Client`

## pseudocode

```c

```

## disassembly

```asm
0x172180  ldarg.0
0x172181  ldfld    int32 <GetMethods>d__12::<>1__state
0x172186  stloc.1
0x172187  ldloc.1
0x172188  switch   loc_1721C2, loc_172E46, loc_17222C, loc_172392, loc_1724E5, loc_172639, loc_172790, loc_1728E7, loc_172A3E, loc_172B92, loc_172CEA, loc_172E3F
0x1721bd  br       loc_172E46
0x1721c2  ldarg.0
0x1721c3  ldc.i4.m1
0x1721c4  stfld    int32 <GetMethods>d__12::<>1__state
0x1721c9  ldarg.0
0x1721ca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__12::proxyContext
0x1721cf  brtrue.s loc_1721DC
0x1721d1  ldstr    aProxycontext// "proxyContext"
0x1721d6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1721db  throw
0x1721dc  ldarg.0
0x1721dd  ldarg.0
0x1721de  ldfld    class Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub <GetMethods>d__12::<>4__this
0x1721e3  ldarg.0
0x1721e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__12::proxyContext
0x1721e9  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::<>n__FabricatedMethod17(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x1721ee  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x1721f3  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__12::<>7__wrap15
0x1721f8  ldarg.0
0x1721f9  ldc.i4.1
0x1721fa  stfld    int32 <GetMethods>d__12::<>1__state
0x1721ff  br.s     loc_172233
0x172201  ldarg.0
0x172202  ldarg.0
0x172203  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__12::<>7__wrap15
0x172208  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x17220d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<itemBase>5__13
0x172212  ldarg.0
0x172213  ldarg.0
0x172214  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<itemBase>5__13
0x172219  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>2__current
0x17221e  ldarg.0
0x17221f  ldc.i4.2
0x172220  stfld    int32 <GetMethods>d__12::<>1__state
0x172225  ldc.i4.1
0x172226  stloc.0
0x172227  leave    loc_172E51
0x17222c  ldarg.0
0x17222d  ldc.i4.1
0x17222e  stfld    int32 <GetMethods>d__12::<>1__state
0x172233  ldarg.0
0x172234  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__12::<>7__wrap15
0x172239  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x17223e  brtrue.s loc_172201
0x172240  ldarg.0
0x172241  call     instance void <GetMethods>d__12::<>m__Finally16()
0x172246  ldarg.0
0x172247  ldarg.0
0x172248  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x17224d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x172252  ldarg.0
0x172253  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x172258  ldstr    aAdd// "Add"
0x17225d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x172262  ldarg.0
0x172263  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x172268  ldc.i4.0
0x172269  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x17226e  ldarg.0
0x17226f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x172274  ldc.i4.0
0x172275  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x17227a  ldarg.0
0x17227b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x172280  ldc.i4.7
0x172281  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x172286  ldarg.0
0x172287  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x17228c  ldstr    aAdd// "Add"
0x172291  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x172296  ldarg.0
0x172297  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x17229c  ldc.i4.0
0x17229d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1722a2  ldarg.0
0x1722a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x1722a8  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPUser
0x1722ad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1722b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1722b7  ldarg.0
0x1722b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x1722bd  ldc.i4.4
0x1722be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1722c3  ldarg.0
0x1722c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x1722c9  ldc.i4.0
0x1722ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1722cf  ldarg.0
0x1722d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x1722d5  ldc.i4.0
0x1722d6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1722db  ldarg.0
0x1722dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x1722e1  ldc.i4.0
0x1722e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1722e7  ldarg.0
0x1722e8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x1722ed  ldc.i4.0
0x1722ee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1722f3  ldarg.0
0x1722f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x1722f9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<item>5__14
0x1722fe  ldarg.0
0x1722ff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<item>5__14
0x172304  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x172309  ldarg.0
0x17230a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x17230f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal1
0x172314  ldarg.0
0x172315  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal1
0x17231a  ldstr    aParameters// "parameters"
0x17231f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x172324  ldarg.0
0x172325  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal1
0x17232a  ldc.i4.0
0x17232b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x172330  ldarg.0
0x172331  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal1
0x172336  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCreationInformation
0x17233b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x172340  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x172345  ldarg.0
0x172346  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal1
0x17234b  ldc.i4.2
0x17234c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x172351  ldarg.0
0x172352  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal1
0x172357  ldc.i4.0
0x172358  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x17235d  ldarg.0
0x17235e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal1
0x172363  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x172368  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x17236d  ldarg.0
0x17236e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal1
0x172373  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x172378  ldarg.0
0x172379  ldarg.0
0x17237a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<item>5__14
0x17237f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>2__current
0x172384  ldarg.0
0x172385  ldc.i4.3
0x172386  stfld    int32 <GetMethods>d__12::<>1__state
0x17238b  ldc.i4.1
0x17238c  stloc.0
0x17238d  leave    loc_172E51
0x172392  ldarg.0
0x172393  ldc.i4.m1
0x172394  stfld    int32 <GetMethods>d__12::<>1__state
0x172399  ldarg.0
0x17239a  ldarg.0
0x17239b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1723a0  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal2
0x1723a5  ldarg.0
0x1723a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal2
0x1723ab  ldstr    aAdduser// "AddUser"
0x1723b0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1723b5  ldarg.0
0x1723b6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal2
0x1723bb  ldc.i4.0
0x1723bc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1723c1  ldarg.0
0x1723c2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal2
0x1723c7  ldc.i4.0
0x1723c8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1723cd  ldarg.0
0x1723ce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal2
0x1723d3  ldc.i4.7
0x1723d4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1723d9  ldarg.0
0x1723da  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal2
0x1723df  ldstr    aAdduserClient// "AddUser_Client"
0x1723e4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1723e9  ldarg.0
0x1723ea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal2
0x1723ef  ldc.i4.0
0x1723f0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1723f5  ldarg.0
0x1723f6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal2
0x1723fb  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPUser
0x172400  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x172405  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x17240a  ldarg.0
0x17240b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal2
0x172410  ldc.i4.4
0x172411  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x172416  ldarg.0
0x172417  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal2
0x17241c  ldc.i4.0
0x17241d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x172422  ldarg.0
0x172423  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal2
0x172428  ldc.i4.0
0x172429  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x17242e  ldarg.0
0x17242f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal2
0x172434  ldc.i4.0
0x172435  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x17243a  ldarg.0
0x17243b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal2
0x172440  ldc.i4.0
0x172441  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x172446  ldarg.0
0x172447  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal2
0x17244c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<item>5__14
0x172451  ldarg.0
0x172452  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<item>5__14
0x172457  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x17245c  ldarg.0
0x17245d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x172462  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal3
0x172467  ldarg.0
0x172468  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal3
0x17246d  ldstr    aUser_0// "user"
0x172472  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x172477  ldarg.0
0x172478  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal3
0x17247d  ldc.i4.0
0x17247e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x172483  ldarg.0
0x172484  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal3
0x172489  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPUser
0x17248e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x172493  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x172498  ldarg.0
0x172499  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal3
0x17249e  ldc.i4.0
0x17249f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1724a4  ldarg.0
0x1724a5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal3
0x1724aa  ldc.i4.0
0x1724ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1724b0  ldarg.0
0x1724b1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal3
0x1724b6  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1724bb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1724c0  ldarg.0
0x1724c1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal3
0x1724c6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1724cb  ldarg.0
0x1724cc  ldarg.0
0x1724cd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<item>5__14
0x1724d2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>2__current
0x1724d7  ldarg.0
0x1724d8  ldc.i4.4
0x1724d9  stfld    int32 <GetMethods>d__12::<>1__state
0x1724de  ldc.i4.1
0x1724df  stloc.0
0x1724e0  leave    loc_172E51
0x1724e5  ldarg.0
0x1724e6  ldc.i4.m1
0x1724e7  stfld    int32 <GetMethods>d__12::<>1__state
0x1724ec  ldarg.0
0x1724ed  ldarg.0
0x1724ee  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1724f3  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal4
0x1724f8  ldarg.0
0x1724f9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal4
0x1724fe  ldstr    aCreate// "Create"
0x172503  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x172508  ldarg.0
0x172509  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal4
0x17250e  ldc.i4.0
0x17250f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x172514  ldarg.0
0x172515  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal4
0x17251a  ldc.i4.0
0x17251b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x172520  ldarg.0
0x172521  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal4
0x172526  ldc.i4.s 0x10
0x172528  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x17252d  ldarg.0
0x17252e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal4
0x172533  ldstr    aCreateuserClie// "CreateUser_Client"
0x172538  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x17253d  ldarg.0
0x17253e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal4
0x172543  ldc.i4.0
0x172544  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x172549  ldarg.0
0x17254a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal4
0x17254f  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPUser
0x172554  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x172559  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x17255e  ldarg.0
0x17255f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal4
0x172564  ldc.i4.4
0x172565  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x17256a  ldarg.0
0x17256b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal4
0x172570  ldc.i4.0
0x172571  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x172576  ldarg.0
0x172577  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal4
  ... truncated ...
```
