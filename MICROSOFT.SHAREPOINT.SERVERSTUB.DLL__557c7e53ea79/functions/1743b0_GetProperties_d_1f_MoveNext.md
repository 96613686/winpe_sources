# <GetProperties>d__1f::MoveNext

- ea: `0x1743b0`
- end: `0x1756b5`
- name: `<GetProperties>d__1f::MoveNext`
- size: `4869`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x89ce0`
- `0x1743b0`
- `0x1756e0`
- `0x175740`

## string_xrefs

- `0x1744b8`: `ClientSideComponentId`
- `0x174532`: `ClientSideComponentId`
- `0x17459e`: `ClientSideComponentProperties`
- `0x17460b`: `ClientSideComponentProperties`
- `0x174677`: `CommandUIExtension`
- `0x1746e4`: `CommandUIExtension`

## pseudocode

```c

```

## disassembly

```asm
0x1743b0  ldarg.0
0x1743b1  ldfld    int32 <GetProperties>d__1f::<>1__state
0x1743b6  stloc.1
0x1743b7  ldloc.1
0x1743b8  switch   loc_174422, loc_1756A8, loc_17448C, loc_174585, loc_17465E, loc_174737, loc_174810, loc_1748E9, loc_1749C2, loc_174AA9, loc_174B83, loc_174C5D, loc_174D37, loc_174E11, loc_174EF0, loc_174FCA, loc_1750A9, loc_175183, loc_17525D, loc_17533C, loc_175416, loc_1754F0, loc_1755CA, loc_1756A1
0x17441d  br       loc_1756A8
0x174422  ldarg.0
0x174423  ldc.i4.m1
0x174424  stfld    int32 <GetProperties>d__1f::<>1__state
0x174429  ldarg.0
0x17442a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__1f::proxyContext
0x17442f  brtrue.s loc_17443C
0x174431  ldstr    aProxycontext// "proxyContext"
0x174436  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x17443b  throw
0x17443c  ldarg.0
0x17443d  ldarg.0
0x17443e  ldfld    class Microsoft.SharePoint.ServerStub.SPUserCustomActionServerStub <GetProperties>d__1f::<>4__this
0x174443  ldarg.0
0x174444  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__1f::proxyContext
0x174449  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPUserCustomActionServerStub::<>n__FabricatedMethod23(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x17444e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x174453  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1f::<>7__wrap21
0x174458  ldarg.0
0x174459  ldc.i4.1
0x17445a  stfld    int32 <GetProperties>d__1f::<>1__state
0x17445f  br.s     loc_174493
0x174461  ldarg.0
0x174462  ldarg.0
0x174463  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1f::<>7__wrap21
0x174468  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x17446d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<item>5__20
0x174472  ldarg.0
0x174473  ldarg.0
0x174474  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<item>5__20
0x174479  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>2__current
0x17447e  ldarg.0
0x17447f  ldc.i4.2
0x174480  stfld    int32 <GetProperties>d__1f::<>1__state
0x174485  ldc.i4.1
0x174486  stloc.0
0x174487  leave    loc_1756B3
0x17448c  ldarg.0
0x17448d  ldc.i4.1
0x17448e  stfld    int32 <GetProperties>d__1f::<>1__state
0x174493  ldarg.0
0x174494  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1f::<>7__wrap21
0x174499  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x17449e  brtrue.s loc_174461
0x1744a0  ldarg.0
0x1744a1  call     instance void <GetProperties>d__1f::<>m__Finally22()
0x1744a6  ldarg.0
0x1744a7  ldarg.0
0x1744a8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1744ad  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocala
0x1744b2  ldarg.0
0x1744b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocala
0x1744b8  ldstr    aClientsidecomp// "ClientSideComponentId"
0x1744bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1744c2  ldarg.0
0x1744c3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocala
0x1744c8  ldc.i4.0
0x1744c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1744ce  ldarg.0
0x1744cf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocala
0x1744d4  ldc.i4.1
0x1744d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1744da  ldarg.0
0x1744db  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocala
0x1744e0  ldc.i4.0
0x1744e1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1744e6  ldarg.0
0x1744e7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocala
0x1744ec  ldtoken  [mscorlib]System.Guid
0x1744f1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1744f6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1744fb  ldarg.0
0x1744fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocala
0x174501  ldc.i4.0
0x174502  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x174507  ldarg.0
0x174508  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocala
0x17450d  ldc.i4.1
0x17450e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x174513  ldarg.0
0x174514  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocala
0x174519  ldloca.s 2
0x17451b  initobj  [mscorlib]System.Guid
0x174521  ldloc.2
0x174522  box      [mscorlib]System.Guid
0x174527  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x17452c  ldarg.0
0x17452d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocala
0x174532  ldstr    aClientsidecomp// "ClientSideComponentId"
0x174537  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x17453c  ldarg.0
0x17453d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocala
0x174542  ldnull
0x174543  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x174548  ldarg.0
0x174549  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocala
0x17454e  ldc.i4.0
0x17454f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x174554  ldarg.0
0x174555  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocala
0x17455a  ldc.i4.1
0x17455b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x174560  ldarg.0
0x174561  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocala
0x174566  ldc.i4.0
0x174567  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x17456c  ldarg.0
0x17456d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocala
0x174572  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>2__current
0x174577  ldarg.0
0x174578  ldc.i4.3
0x174579  stfld    int32 <GetProperties>d__1f::<>1__state
0x17457e  ldc.i4.1
0x17457f  stloc.0
0x174580  leave    loc_1756B3
0x174585  ldarg.0
0x174586  ldc.i4.m1
0x174587  stfld    int32 <GetProperties>d__1f::<>1__state
0x17458c  ldarg.0
0x17458d  ldarg.0
0x17458e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x174593  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalb
0x174598  ldarg.0
0x174599  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalb
0x17459e  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x1745a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1745a8  ldarg.0
0x1745a9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalb
0x1745ae  ldc.i4.0
0x1745af  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1745b4  ldarg.0
0x1745b5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalb
0x1745ba  ldc.i4.1
0x1745bb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1745c0  ldarg.0
0x1745c1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalb
0x1745c6  ldc.i4.0
0x1745c7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1745cc  ldarg.0
0x1745cd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalb
0x1745d2  ldtoken  [mscorlib]System.String
0x1745d7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1745dc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1745e1  ldarg.0
0x1745e2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalb
0x1745e7  ldc.i4.0
0x1745e8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1745ed  ldarg.0
0x1745ee  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalb
0x1745f3  ldc.i4.1
0x1745f4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1745f9  ldarg.0
0x1745fa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalb
0x1745ff  ldnull
0x174600  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x174605  ldarg.0
0x174606  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalb
0x17460b  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x174610  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x174615  ldarg.0
0x174616  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalb
0x17461b  ldnull
0x17461c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x174621  ldarg.0
0x174622  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalb
0x174627  ldc.i4.0
0x174628  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x17462d  ldarg.0
0x17462e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalb
0x174633  ldc.i4.1
0x174634  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x174639  ldarg.0
0x17463a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalb
0x17463f  ldc.i4.0
0x174640  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x174645  ldarg.0
0x174646  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalb
0x17464b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>2__current
0x174650  ldarg.0
0x174651  ldc.i4.4
0x174652  stfld    int32 <GetProperties>d__1f::<>1__state
0x174657  ldc.i4.1
0x174658  stloc.0
0x174659  leave    loc_1756B3
0x17465e  ldarg.0
0x17465f  ldc.i4.m1
0x174660  stfld    int32 <GetProperties>d__1f::<>1__state
0x174665  ldarg.0
0x174666  ldarg.0
0x174667  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x17466c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalc
0x174671  ldarg.0
0x174672  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalc
0x174677  ldstr    aCommanduiexten// "CommandUIExtension"
0x17467c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x174681  ldarg.0
0x174682  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalc
0x174687  ldc.i4.0
0x174688  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x17468d  ldarg.0
0x17468e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalc
0x174693  ldc.i4.1
0x174694  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x174699  ldarg.0
0x17469a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalc
0x17469f  ldc.i4.0
0x1746a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1746a5  ldarg.0
0x1746a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalc
0x1746ab  ldtoken  [mscorlib]System.String
0x1746b0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1746b5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1746ba  ldarg.0
0x1746bb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalc
0x1746c0  ldc.i4.0
0x1746c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1746c6  ldarg.0
0x1746c7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalc
0x1746cc  ldc.i4.1
0x1746cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1746d2  ldarg.0
0x1746d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalc
0x1746d8  ldnull
0x1746d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1746de  ldarg.0
0x1746df  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalc
0x1746e4  ldstr    aCommanduiexten// "CommandUIExtension"
0x1746e9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1746ee  ldarg.0
0x1746ef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalc
0x1746f4  ldnull
0x1746f5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1746fa  ldarg.0
0x1746fb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalc
0x174700  ldc.i4.0
0x174701  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x174706  ldarg.0
0x174707  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalc
0x17470c  ldc.i4.0
0x17470d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x174712  ldarg.0
0x174713  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalc
0x174718  ldc.i4.0
0x174719  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x17471e  ldarg.0
0x17471f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocalc
0x174724  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>2__current
0x174729  ldarg.0
0x17472a  ldc.i4.5
0x17472b  stfld    int32 <GetProperties>d__1f::<>1__state
0x174730  ldc.i4.1
0x174731  stloc.0
0x174732  leave    loc_1756B3
0x174737  ldarg.0
0x174738  ldc.i4.m1
0x174739  stfld    int32 <GetProperties>d__1f::<>1__state
0x17473e  ldarg.0
0x17473f  ldarg.0
0x174740  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x174745  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocald
0x17474a  ldarg.0
0x17474b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocald
0x174750  ldstr    aDescription// "Description"
0x174755  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x17475a  ldarg.0
0x17475b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocald
0x174760  ldc.i4.0
0x174761  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x174766  ldarg.0
0x174767  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocald
0x17476c  ldc.i4.1
0x17476d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x174772  ldarg.0
0x174773  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocald
0x174778  ldc.i4.0
0x174779  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x17477e  ldarg.0
0x17477f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocald
0x174784  ldtoken  [mscorlib]System.String
0x174789  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17478e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x174793  ldarg.0
0x174794  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocald
0x174799  ldc.i4.0
0x17479a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x17479f  ldarg.0
0x1747a0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocald
0x1747a5  ldc.i4.1
0x1747a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1747ab  ldarg.0
0x1747ac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocald
0x1747b1  ldnull
0x1747b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1747b7  ldarg.0
0x1747b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1f::<>g__initLocald
  ... truncated ...
```
