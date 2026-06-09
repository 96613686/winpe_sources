# <GetMethods>d__2::MoveNext_0

- ea: `0x216d0`
- end: `0x218d3`
- name: `<GetMethods>d__2::MoveNext_0`
- size: `515`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xbb10`
- `0x216d0`
- `0x21900`
- `0x21960`

## string_xrefs

- `0x2184a`: `approvalComment`

## pseudocode

```c

```

## disassembly

```asm
0x216d0  ldarg.0
0x216d1  ldfld    int32 <GetMethods>d__2::<>1__state
0x216d6  stloc.1
0x216d7  ldloc.1
0x216d8  switch   loc_216F2, loc_218C6, loc_2175C, loc_218BF
0x216ed  br       loc_218C6
0x216f2  ldarg.0
0x216f3  ldc.i4.m1
0x216f4  stfld    int32 <GetMethods>d__2::<>1__state
0x216f9  ldarg.0
0x216fa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__2::proxyContext
0x216ff  brtrue.s loc_2170C
0x21701  ldstr    aProxycontext// "proxyContext"
0x21706  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2170b  throw
0x2170c  ldarg.0
0x2170d  ldarg.0
0x2170e  ldfld    class Microsoft.SharePoint.Publishing.ScheduledItemServerStub <GetMethods>d__2::<>4__this
0x21713  ldarg.0
0x21714  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__2::proxyContext
0x21719  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Publishing.ScheduledItemServerStub::<>n__FabricatedMethod7(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x2171e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x21723  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__2::<>7__wrap5
0x21728  ldarg.0
0x21729  ldc.i4.1
0x2172a  stfld    int32 <GetMethods>d__2::<>1__state
0x2172f  br.s     loc_21763
0x21731  ldarg.0
0x21732  ldarg.0
0x21733  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__2::<>7__wrap5
0x21738  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x2173d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<itemBase>5__3
0x21742  ldarg.0
0x21743  ldarg.0
0x21744  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<itemBase>5__3
0x21749  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>2__current
0x2174e  ldarg.0
0x2174f  ldc.i4.2
0x21750  stfld    int32 <GetMethods>d__2::<>1__state
0x21755  ldc.i4.1
0x21756  stloc.0
0x21757  leave    loc_218D1
0x2175c  ldarg.0
0x2175d  ldc.i4.1
0x2175e  stfld    int32 <GetMethods>d__2::<>1__state
0x21763  ldarg.0
0x21764  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__2::<>7__wrap5
0x21769  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2176e  brtrue.s loc_21731
0x21770  ldarg.0
0x21771  call     instance void <GetMethods>d__2::<>m__Finally6()
0x21776  ldarg.0
0x21777  ldarg.0
0x21778  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x2177d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x21782  ldarg.0
0x21783  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x21788  ldstr    aSchedule// "Schedule"
0x2178d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x21792  ldarg.0
0x21793  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x21798  ldc.i4.0
0x21799  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x2179e  ldarg.0
0x2179f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x217a4  ldc.i4.0
0x217a5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x217aa  ldarg.0
0x217ab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x217b0  ldc.i4.7
0x217b1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x217b6  ldarg.0
0x217b7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x217bc  ldstr    aSchedule// "Schedule"
0x217c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x217c6  ldarg.0
0x217c7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x217cc  ldc.i4.0
0x217cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x217d2  ldarg.0
0x217d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x217d8  ldtoken  [mscorlib]System.Void
0x217dd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x217e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x217e7  ldarg.0
0x217e8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x217ed  ldc.i4.0
0x217ee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x217f3  ldarg.0
0x217f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x217f9  ldc.i4.0
0x217fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x217ff  ldarg.0
0x21800  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x21805  ldc.i4.0
0x21806  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x2180b  ldarg.0
0x2180c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x21811  ldc.i4.0
0x21812  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x21817  ldarg.0
0x21818  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x2181d  ldc.i4.0
0x2181e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x21823  ldarg.0
0x21824  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>g__initLocal0
0x21829  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<item>5__4
0x2182e  ldarg.0
0x2182f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<item>5__4
0x21834  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x21839  ldarg.0
0x2183a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x2183f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x21844  ldarg.0
0x21845  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x2184a  ldstr    aApprovalcommen// "approvalComment"
0x2184f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x21854  ldarg.0
0x21855  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x2185a  ldc.i4.0
0x2185b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x21860  ldarg.0
0x21861  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x21866  ldtoken  [mscorlib]System.String
0x2186b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21870  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x21875  ldarg.0
0x21876  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x2187b  ldc.i4.1
0x2187c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x21881  ldarg.0
0x21882  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x21887  ldc.i4.0
0x21888  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x2188d  ldarg.0
0x2188e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x21893  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x21898  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x2189d  ldarg.0
0x2189e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__2::<>g__initLocal1
0x218a3  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x218a8  ldarg.0
0x218a9  ldarg.0
0x218aa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<item>5__4
0x218af  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__2::<>2__current
0x218b4  ldarg.0
0x218b5  ldc.i4.3
0x218b6  stfld    int32 <GetMethods>d__2::<>1__state
0x218bb  ldc.i4.1
0x218bc  stloc.0
0x218bd  leave.s  loc_218D1
0x218bf  ldarg.0
0x218c0  ldc.i4.m1
0x218c1  stfld    int32 <GetMethods>d__2::<>1__state
0x218c6  ldc.i4.0
0x218c7  stloc.0
0x218c8  leave.s  loc_218D1
0x218ca  ldarg.0
0x218cb  call     instance void <GetMethods>d__2::System.IDisposable.Dispose()
0x218d0  endfinally
0x218d1  ldloc.0
0x218d2  ret
```
