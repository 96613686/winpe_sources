# <GetMethods>d__10::MoveNext_4

- ea: `0x178580`
- end: `0x1790e6`
- name: `<GetMethods>d__10::MoveNext_4`
- size: `2918`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x8c480`
- `0x178580`
- `0x179110`
- `0x179170`

## string_xrefs

- `0x178cc8`: `Delete`
- `0x178e1b`: `DeleteAll`
- `0x178c94`: `Remove`
- `0x178de7`: `RemoveAll`
- `0x1788fa`: `MoveFieldTo`
- `0x17892e`: `MoveFieldTo`
- `0x178ac7`: `MoveViewFieldTo`
- `0x178f9a`: `RemoveViewField`
- `0x178fce`: `RemoveViewField`
- `0x178ec0`: `RemoveAllViewFields`
- `0x178afb`: `MoveFieldTo_Client`
- `0x178ef4`: `DeleteAll_Client`

## pseudocode

```c

```

## disassembly

```asm
0x178580  ldarg.0
0x178581  ldfld    int32 <GetMethods>d__10::<>1__state
0x178586  stloc.1
0x178587  ldloc.1
0x178588  switch   loc_1785BE, loc_1790D9, loc_178628, loc_17878E, loc_1788E1, loc_178AAE, loc_178C7B, loc_178DCE, loc_178EA7, loc_178F81, loc_1790D2
0x1785b9  br       loc_1790D9
0x1785be  ldarg.0
0x1785bf  ldc.i4.m1
0x1785c0  stfld    int32 <GetMethods>d__10::<>1__state
0x1785c5  ldarg.0
0x1785c6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__10::proxyContext
0x1785cb  brtrue.s loc_1785D8
0x1785cd  ldstr    aProxycontext// "proxyContext"
0x1785d2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1785d7  throw
0x1785d8  ldarg.0
0x1785d9  ldarg.0
0x1785da  ldfld    class Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub <GetMethods>d__10::<>4__this
0x1785df  ldarg.0
0x1785e0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__10::proxyContext
0x1785e5  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::<>n__FabricatedMethod15(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x1785ea  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x1785ef  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__10::<>7__wrap13
0x1785f4  ldarg.0
0x1785f5  ldc.i4.1
0x1785f6  stfld    int32 <GetMethods>d__10::<>1__state
0x1785fb  br.s     loc_17862F
0x1785fd  ldarg.0
0x1785fe  ldarg.0
0x1785ff  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__10::<>7__wrap13
0x178604  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x178609  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<itemBase>5__11
0x17860e  ldarg.0
0x17860f  ldarg.0
0x178610  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<itemBase>5__11
0x178615  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>2__current
0x17861a  ldarg.0
0x17861b  ldc.i4.2
0x17861c  stfld    int32 <GetMethods>d__10::<>1__state
0x178621  ldc.i4.1
0x178622  stloc.0
0x178623  leave    loc_1790E4
0x178628  ldarg.0
0x178629  ldc.i4.1
0x17862a  stfld    int32 <GetMethods>d__10::<>1__state
0x17862f  ldarg.0
0x178630  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__10::<>7__wrap13
0x178635  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x17863a  brtrue.s loc_1785FD
0x17863c  ldarg.0
0x17863d  call     instance void <GetMethods>d__10::<>m__Finally14()
0x178642  ldarg.0
0x178643  ldarg.0
0x178644  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x178649  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x17864e  ldarg.0
0x17864f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x178654  ldstr    aAdd// "Add"
0x178659  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x17865e  ldarg.0
0x17865f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x178664  ldc.i4.0
0x178665  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x17866a  ldarg.0
0x17866b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x178670  ldc.i4.0
0x178671  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x178676  ldarg.0
0x178677  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x17867c  ldc.i4.7
0x17867d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x178682  ldarg.0
0x178683  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x178688  ldstr    aAdd// "Add"
0x17868d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x178692  ldarg.0
0x178693  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x178698  ldc.i4.0
0x178699  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x17869e  ldarg.0
0x17869f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x1786a4  ldtoken  [mscorlib]System.Void
0x1786a9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1786ae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1786b3  ldarg.0
0x1786b4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x1786b9  ldc.i4.0
0x1786ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1786bf  ldarg.0
0x1786c0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x1786c5  ldc.i4.0
0x1786c6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1786cb  ldarg.0
0x1786cc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x1786d1  ldc.i4.0
0x1786d2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1786d7  ldarg.0
0x1786d8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x1786dd  ldc.i4.0
0x1786de  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1786e3  ldarg.0
0x1786e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x1786e9  ldc.i4.0
0x1786ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1786ef  ldarg.0
0x1786f0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0x1786f5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x1786fa  ldarg.0
0x1786fb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x178700  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x178705  ldarg.0
0x178706  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x17870b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0x178710  ldarg.0
0x178711  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0x178716  ldstr    aStrfield// "strField"
0x17871b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x178720  ldarg.0
0x178721  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0x178726  ldc.i4.0
0x178727  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x17872c  ldarg.0
0x17872d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0x178732  ldtoken  [mscorlib]System.String
0x178737  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17873c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x178741  ldarg.0
0x178742  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0x178747  ldc.i4.1
0x178748  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x17874d  ldarg.0
0x17874e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0x178753  ldc.i4.0
0x178754  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x178759  ldarg.0
0x17875a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0x17875f  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x178764  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x178769  ldarg.0
0x17876a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0x17876f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x178774  ldarg.0
0x178775  ldarg.0
0x178776  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x17877b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>2__current
0x178780  ldarg.0
0x178781  ldc.i4.3
0x178782  stfld    int32 <GetMethods>d__10::<>1__state
0x178787  ldc.i4.1
0x178788  stloc.0
0x178789  leave    loc_1790E4
0x17878e  ldarg.0
0x17878f  ldc.i4.m1
0x178790  stfld    int32 <GetMethods>d__10::<>1__state
0x178795  ldarg.0
0x178796  ldarg.0
0x178797  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x17879c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal2
0x1787a1  ldarg.0
0x1787a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal2
0x1787a7  ldstr    aAddviewfield// "AddViewField"
0x1787ac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1787b1  ldarg.0
0x1787b2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal2
0x1787b7  ldc.i4.0
0x1787b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1787bd  ldarg.0
0x1787be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal2
0x1787c3  ldc.i4.0
0x1787c4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1787c9  ldarg.0
0x1787ca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal2
0x1787cf  ldc.i4.8
0x1787d0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1787d5  ldarg.0
0x1787d6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal2
0x1787db  ldstr    aAddClient// "Add_Client"
0x1787e0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1787e5  ldarg.0
0x1787e6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal2
0x1787eb  ldc.i4.0
0x1787ec  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1787f1  ldarg.0
0x1787f2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal2
0x1787f7  ldtoken  [mscorlib]System.Void
0x1787fc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x178801  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x178806  ldarg.0
0x178807  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal2
0x17880c  ldc.i4.0
0x17880d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x178812  ldarg.0
0x178813  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal2
0x178818  ldc.i4.0
0x178819  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x17881e  ldarg.0
0x17881f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal2
0x178824  ldc.i4.0
0x178825  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x17882a  ldarg.0
0x17882b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal2
0x178830  ldc.i4.0
0x178831  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x178836  ldarg.0
0x178837  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal2
0x17883c  ldc.i4.0
0x17883d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x178842  ldarg.0
0x178843  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal2
0x178848  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x17884d  ldarg.0
0x17884e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x178853  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x178858  ldarg.0
0x178859  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x17885e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal3
0x178863  ldarg.0
0x178864  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal3
0x178869  ldstr    aStrfield// "strField"
0x17886e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x178873  ldarg.0
0x178874  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal3
0x178879  ldc.i4.0
0x17887a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x17887f  ldarg.0
0x178880  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal3
0x178885  ldtoken  [mscorlib]System.String
0x17888a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17888f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x178894  ldarg.0
0x178895  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal3
0x17889a  ldc.i4.1
0x17889b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1788a0  ldarg.0
0x1788a1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal3
0x1788a6  ldc.i4.0
0x1788a7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1788ac  ldarg.0
0x1788ad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal3
0x1788b2  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1788b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1788bc  ldarg.0
0x1788bd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal3
0x1788c2  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1788c7  ldarg.0
0x1788c8  ldarg.0
0x1788c9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0x1788ce  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>2__current
0x1788d3  ldarg.0
0x1788d4  ldc.i4.4
0x1788d5  stfld    int32 <GetMethods>d__10::<>1__state
0x1788da  ldc.i4.1
0x1788db  stloc.0
0x1788dc  leave    loc_1790E4
0x1788e1  ldarg.0
0x1788e2  ldc.i4.m1
0x1788e3  stfld    int32 <GetMethods>d__10::<>1__state
0x1788e8  ldarg.0
0x1788e9  ldarg.0
0x1788ea  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1788ef  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x1788f4  ldarg.0
0x1788f5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x1788fa  ldstr    aMovefieldto// "MoveFieldTo"
0x1788ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x178904  ldarg.0
0x178905  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x17890a  ldc.i4.0
0x17890b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x178910  ldarg.0
0x178911  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x178916  ldc.i4.0
0x178917  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x17891c  ldarg.0
0x17891d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x178922  ldc.i4.7
0x178923  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x178928  ldarg.0
0x178929  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x17892e  ldstr    aMovefieldto// "MoveFieldTo"
0x178933  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x178938  ldarg.0
0x178939  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x17893e  ldc.i4.0
0x17893f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x178944  ldarg.0
0x178945  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x17894a  ldtoken  [mscorlib]System.Void
0x17894f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x178954  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x178959  ldarg.0
0x17895a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x17895f  ldc.i4.0
0x178960  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x178965  ldarg.0
0x178966  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
0x17896b  ldc.i4.0
0x17896c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x178971  ldarg.0
0x178972  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal4
  ... truncated ...
```
