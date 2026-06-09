# <GetMethods>d__1a::MoveNext

- ea: `0x125d70`
- end: `0x126e6f`
- name: `<GetMethods>d__1a::MoveNext`
- size: `4351`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x4fa90`
- `0x125d70`
- `0x126e90`
- `0x126ef0`

## string_xrefs

- `0x1267c7`: `Create`
- `0x126580`: `AddFieldAsXml`
- `0x12691b`: `CreateFieldAsXml`
- `0x1265b4`: `AddFieldAsXml_Client`
- `0x126642`: `schemaXml`
- `0x1267fc`: `Create_Rest`
- `0x12694f`: `AddFieldAsXml_Rest`

## pseudocode

```c

```

## disassembly

```asm
0x125d70  ldarg.0
0x125d71  ldfld    int32 <GetMethods>d__1a::<>1__state
0x125d76  stloc.1
0x125d77  ldloc.1
0x125d78  switch   loc_125DB6, loc_126E62, loc_125E20, loc_125F86, loc_1261CD, loc_126414, loc_126567, loc_1267AE, loc_126902, loc_126A56, loc_126BAE, loc_126D06, loc_126E5B
0x125db1  br       loc_126E62
0x125db6  ldarg.0
0x125db7  ldc.i4.m1
0x125db8  stfld    int32 <GetMethods>d__1a::<>1__state
0x125dbd  ldarg.0
0x125dbe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__1a::proxyContext
0x125dc3  brtrue.s loc_125DD0
0x125dc5  ldstr    aProxycontext// "proxyContext"
0x125dca  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x125dcf  throw
0x125dd0  ldarg.0
0x125dd1  ldarg.0
0x125dd2  ldfld    class Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub <GetMethods>d__1a::<>4__this
0x125dd7  ldarg.0
0x125dd8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__1a::proxyContext
0x125ddd  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::<>n__FabricatedMethod1f(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x125de2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x125de7  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__1a::<>7__wrap1d
0x125dec  ldarg.0
0x125ded  ldc.i4.1
0x125dee  stfld    int32 <GetMethods>d__1a::<>1__state
0x125df3  br.s     loc_125E27
0x125df5  ldarg.0
0x125df6  ldarg.0
0x125df7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__1a::<>7__wrap1d
0x125dfc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x125e01  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<itemBase>5__1b
0x125e06  ldarg.0
0x125e07  ldarg.0
0x125e08  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<itemBase>5__1b
0x125e0d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>2__current
0x125e12  ldarg.0
0x125e13  ldc.i4.2
0x125e14  stfld    int32 <GetMethods>d__1a::<>1__state
0x125e19  ldc.i4.1
0x125e1a  stloc.0
0x125e1b  leave    loc_126E6D
0x125e20  ldarg.0
0x125e21  ldc.i4.1
0x125e22  stfld    int32 <GetMethods>d__1a::<>1__state
0x125e27  ldarg.0
0x125e28  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__1a::<>7__wrap1d
0x125e2d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x125e32  brtrue.s loc_125DF5
0x125e34  ldarg.0
0x125e35  call     instance void <GetMethods>d__1a::<>m__Finally1e()
0x125e3a  ldarg.0
0x125e3b  ldarg.0
0x125e3c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x125e41  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal0
0x125e46  ldarg.0
0x125e47  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal0
0x125e4c  ldstr    aAdd// "Add"
0x125e51  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x125e56  ldarg.0
0x125e57  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal0
0x125e5c  ldc.i4.0
0x125e5d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x125e62  ldarg.0
0x125e63  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal0
0x125e68  ldc.i4.0
0x125e69  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x125e6e  ldarg.0
0x125e6f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal0
0x125e74  ldc.i4.7
0x125e75  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x125e7a  ldarg.0
0x125e7b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal0
0x125e80  ldstr    aAddClient// "Add_Client"
0x125e85  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x125e8a  ldarg.0
0x125e8b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal0
0x125e90  ldc.i4.0
0x125e91  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x125e96  ldarg.0
0x125e97  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal0
0x125e9c  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPField
0x125ea1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x125ea6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x125eab  ldarg.0
0x125eac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal0
0x125eb1  ldc.i4.4
0x125eb2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x125eb7  ldarg.0
0x125eb8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal0
0x125ebd  ldc.i4.0
0x125ebe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x125ec3  ldarg.0
0x125ec4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal0
0x125ec9  ldc.i4.0
0x125eca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x125ecf  ldarg.0
0x125ed0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal0
0x125ed5  ldc.i4.0
0x125ed6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x125edb  ldarg.0
0x125edc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal0
0x125ee1  ldc.i4.0
0x125ee2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x125ee7  ldarg.0
0x125ee8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal0
0x125eed  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<item>5__1c
0x125ef2  ldarg.0
0x125ef3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<item>5__1c
0x125ef8  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x125efd  ldarg.0
0x125efe  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x125f03  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal1
0x125f08  ldarg.0
0x125f09  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal1
0x125f0e  ldstr    aField_0// "field"
0x125f13  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x125f18  ldarg.0
0x125f19  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal1
0x125f1e  ldc.i4.0
0x125f1f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x125f24  ldarg.0
0x125f25  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal1
0x125f2a  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPField
0x125f2f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x125f34  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x125f39  ldarg.0
0x125f3a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal1
0x125f3f  ldc.i4.0
0x125f40  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x125f45  ldarg.0
0x125f46  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal1
0x125f4b  ldc.i4.0
0x125f4c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x125f51  ldarg.0
0x125f52  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal1
0x125f57  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x125f5c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x125f61  ldarg.0
0x125f62  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal1
0x125f67  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x125f6c  ldarg.0
0x125f6d  ldarg.0
0x125f6e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<item>5__1c
0x125f73  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>2__current
0x125f78  ldarg.0
0x125f79  ldc.i4.3
0x125f7a  stfld    int32 <GetMethods>d__1a::<>1__state
0x125f7f  ldc.i4.1
0x125f80  stloc.0
0x125f81  leave    loc_126E6D
0x125f86  ldarg.0
0x125f87  ldc.i4.m1
0x125f88  stfld    int32 <GetMethods>d__1a::<>1__state
0x125f8d  ldarg.0
0x125f8e  ldarg.0
0x125f8f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x125f94  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal2
0x125f99  ldarg.0
0x125f9a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal2
0x125f9f  ldstr    aAdddependentlo// "AddDependentLookup"
0x125fa4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x125fa9  ldarg.0
0x125faa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal2
0x125faf  ldc.i4.0
0x125fb0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x125fb5  ldarg.0
0x125fb6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal2
0x125fbb  ldc.i4.0
0x125fbc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x125fc1  ldarg.0
0x125fc2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal2
0x125fc7  ldc.i4.7
0x125fc8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x125fcd  ldarg.0
0x125fce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal2
0x125fd3  ldstr    aAdddependentlo_1// "AddDependentLookup_Client"
0x125fd8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x125fdd  ldarg.0
0x125fde  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal2
0x125fe3  ldc.i4.0
0x125fe4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x125fe9  ldarg.0
0x125fea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal2
0x125fef  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPField
0x125ff4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x125ff9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x125ffe  ldarg.0
0x125fff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal2
0x126004  ldc.i4.4
0x126005  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x12600a  ldarg.0
0x12600b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal2
0x126010  ldc.i4.0
0x126011  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x126016  ldarg.0
0x126017  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal2
0x12601c  ldc.i4.0
0x12601d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x126022  ldarg.0
0x126023  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal2
0x126028  ldc.i4.0
0x126029  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x12602e  ldarg.0
0x12602f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal2
0x126034  ldc.i4.0
0x126035  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x12603a  ldarg.0
0x12603b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<>g__initLocal2
0x126040  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<item>5__1c
0x126045  ldarg.0
0x126046  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<item>5__1c
0x12604b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x126050  ldarg.0
0x126051  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x126056  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal3
0x12605b  ldarg.0
0x12605c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal3
0x126061  ldstr    aDisplayname_0// "displayName"
0x126066  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x12606b  ldarg.0
0x12606c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal3
0x126071  ldc.i4.0
0x126072  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x126077  ldarg.0
0x126078  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal3
0x12607d  ldtoken  [mscorlib]System.String
0x126082  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x126087  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x12608c  ldarg.0
0x12608d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal3
0x126092  ldc.i4.1
0x126093  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x126098  ldarg.0
0x126099  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal3
0x12609e  ldc.i4.0
0x12609f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1260a4  ldarg.0
0x1260a5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal3
0x1260aa  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1260af  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1260b4  ldarg.0
0x1260b5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal3
0x1260ba  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1260bf  ldarg.0
0x1260c0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<item>5__1c
0x1260c5  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1260ca  ldarg.0
0x1260cb  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1260d0  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal4
0x1260d5  ldarg.0
0x1260d6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal4
0x1260db  ldstr    aPrimarylookupf// "primaryLookupField"
0x1260e0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1260e5  ldarg.0
0x1260e6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal4
0x1260eb  ldc.i4.0
0x1260ec  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1260f1  ldarg.0
0x1260f2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal4
0x1260f7  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPField
0x1260fc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x126101  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x126106  ldarg.0
0x126107  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal4
0x12610c  ldc.i4.0
0x12610d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x126112  ldarg.0
0x126113  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal4
0x126118  ldc.i4.0
0x126119  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x12611e  ldarg.0
0x12611f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal4
0x126124  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x126129  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x12612e  ldarg.0
0x12612f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal4
0x126134  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x126139  ldarg.0
0x12613a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1a::<item>5__1c
0x12613f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x126144  ldarg.0
0x126145  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x12614a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal5
0x12614f  ldarg.0
0x126150  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal5
0x126155  ldstr    aLookupfield// "lookupField"
0x12615a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x12615f  ldarg.0
0x126160  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal5
0x126165  ldc.i4.0
0x126166  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x12616b  ldarg.0
0x12616c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal5
0x126171  ldtoken  [mscorlib]System.String
0x126176  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12617b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x126180  ldarg.0
0x126181  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__1a::<>g__initLocal5
0x126186  ldc.i4.1
  ... truncated ...
```
