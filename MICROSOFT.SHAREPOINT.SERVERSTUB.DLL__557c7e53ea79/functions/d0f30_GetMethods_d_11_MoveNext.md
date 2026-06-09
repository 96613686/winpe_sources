# <GetMethods>d__11::MoveNext

- ea: `0xd0f30`
- end: `0xd1b94`
- name: `<GetMethods>d__11::MoveNext`
- size: `3172`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x11940`
- `0xd0f30`
- `0xd1bc0`
- `0xd1c20`

## string_xrefs

- `0xd1abe`: `Update`
- `0xd1af6`: `Update`
- `0xd13aa`: `DeleteObject`
- `0xd13e2`: `Delete`
- `0xd11d9`: `CreateInstance`
- `0xd1008`: `CreateCollectionInstance`
- `0xd1487`: `FromXml`
- `0xd14bf`: `FromXml`
- `0xd19e0`: `ToXml`
- `0xd1a18`: `ToXml`
- `0xd1040`: `CreateCollectionInstance_Client`
- `0xd1211`: `CreateInstance_Client`

## pseudocode

```c

```

## disassembly

```asm
0xd0f30  ldarg.0
0xd0f31  ldfld    int32 <GetMethods>d__11::<>1__state
0xd0f36  stloc.1
0xd0f37  ldloc.1
0xd0f38  switch   loc_D0F72, loc_D1B87, loc_D0FDC, loc_D11C0, loc_D1391, loc_D146E, loc_D15C5, loc_D1718, loc_D17F5, loc_D19C7, loc_D1AA5, loc_D1B80
0xd0f6d  br       loc_D1B87
0xd0f72  ldarg.0
0xd0f73  ldc.i4.m1
0xd0f74  stfld    int32 <GetMethods>d__11::<>1__state
0xd0f79  ldarg.0
0xd0f7a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__11::proxyContext
0xd0f7f  brtrue.s loc_D0F8C
0xd0f81  ldstr    aProxycontext// "proxyContext"
0xd0f86  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd0f8b  throw
0xd0f8c  ldarg.0
0xd0f8d  ldarg.0
0xd0f8e  ldfld    class Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub <GetMethods>d__11::<>4__this
0xd0f93  ldarg.0
0xd0f94  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__11::proxyContext
0xd0f99  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::<>n__FabricatedMethod16(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0xd0f9e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0xd0fa3  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__11::<>7__wrap14
0xd0fa8  ldarg.0
0xd0fa9  ldc.i4.1
0xd0faa  stfld    int32 <GetMethods>d__11::<>1__state
0xd0faf  br.s     loc_D0FE3
0xd0fb1  ldarg.0
0xd0fb2  ldarg.0
0xd0fb3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__11::<>7__wrap14
0xd0fb8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0xd0fbd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<itemBase>5__12
0xd0fc2  ldarg.0
0xd0fc3  ldarg.0
0xd0fc4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<itemBase>5__12
0xd0fc9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>2__current
0xd0fce  ldarg.0
0xd0fcf  ldc.i4.2
0xd0fd0  stfld    int32 <GetMethods>d__11::<>1__state
0xd0fd5  ldc.i4.1
0xd0fd6  stloc.0
0xd0fd7  leave    loc_D1B92
0xd0fdc  ldarg.0
0xd0fdd  ldc.i4.1
0xd0fde  stfld    int32 <GetMethods>d__11::<>1__state
0xd0fe3  ldarg.0
0xd0fe4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__11::<>7__wrap14
0xd0fe9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd0fee  brtrue.s loc_D0FB1
0xd0ff0  ldarg.0
0xd0ff1  call     instance void <GetMethods>d__11::<>m__Finally15()
0xd0ff6  ldarg.0
0xd0ff7  ldarg.0
0xd0ff8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xd0ffd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0xd1002  ldarg.0
0xd1003  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0xd1008  ldstr    aCreatecollecti// "CreateCollectionInstance"
0xd100d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xd1012  ldarg.0
0xd1013  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0xd1018  ldc.i4.0
0xd1019  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xd101e  ldarg.0
0xd101f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0xd1024  ldc.i4.0
0xd1025  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xd102a  ldarg.0
0xd102b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0xd1030  ldc.i4   0xFFFFFFF
0xd1035  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xd103a  ldarg.0
0xd103b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0xd1040  ldstr    aCreatecollecti_0// "CreateCollectionInstance_Client"
0xd1045  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xd104a  ldarg.0
0xd104b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0xd1050  ldc.i4.0
0xd1051  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xd1056  ldarg.0
0xd1057  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0xd105c  ldtoken  [mscorlib]System.Void
0xd1061  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd1066  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xd106b  ldarg.0
0xd106c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0xd1071  ldc.i4.0
0xd1072  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xd1077  ldarg.0
0xd1078  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0xd107d  ldc.i4.0
0xd107e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xd1083  ldarg.0
0xd1084  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0xd1089  ldc.i4.0
0xd108a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0xd108f  ldarg.0
0xd1090  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0xd1095  ldc.i4.0
0xd1096  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xd109b  ldarg.0
0xd109c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0xd10a1  ldc.i4.0
0xd10a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0xd10a7  ldarg.0
0xd10a8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal0
0xd10ad  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<item>5__13
0xd10b2  ldarg.0
0xd10b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<item>5__13
0xd10b8  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xd10bd  ldarg.0
0xd10be  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xd10c3  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal1
0xd10c8  ldarg.0
0xd10c9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal1
0xd10ce  ldstr    aFielddotnotati// "fieldDotNotation"
0xd10d3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xd10d8  ldarg.0
0xd10d9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal1
0xd10de  ldc.i4.0
0xd10df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xd10e4  ldarg.0
0xd10e5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal1
0xd10ea  ldtoken  [mscorlib]System.String
0xd10ef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd10f4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xd10f9  ldarg.0
0xd10fa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal1
0xd10ff  ldc.i4.1
0xd1100  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xd1105  ldarg.0
0xd1106  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal1
0xd110b  ldc.i4.0
0xd110c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0xd1111  ldarg.0
0xd1112  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal1
0xd1117  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd111c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0xd1121  ldarg.0
0xd1122  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal1
0xd1127  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0xd112c  ldarg.0
0xd112d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<item>5__13
0xd1132  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xd1137  ldarg.0
0xd1138  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xd113d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal2
0xd1142  ldarg.0
0xd1143  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal2
0xd1148  ldstr    aSize// "size"
0xd114d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xd1152  ldarg.0
0xd1153  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal2
0xd1158  ldc.i4.0
0xd1159  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xd115e  ldarg.0
0xd115f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal2
0xd1164  ldtoken  [mscorlib]System.Int32
0xd1169  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd116e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xd1173  ldarg.0
0xd1174  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal2
0xd1179  ldc.i4.1
0xd117a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xd117f  ldarg.0
0xd1180  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal2
0xd1185  ldc.i4.0
0xd1186  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0xd118b  ldarg.0
0xd118c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal2
0xd1191  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd1196  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0xd119b  ldarg.0
0xd119c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal2
0xd11a1  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0xd11a6  ldarg.0
0xd11a7  ldarg.0
0xd11a8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<item>5__13
0xd11ad  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>2__current
0xd11b2  ldarg.0
0xd11b3  ldc.i4.3
0xd11b4  stfld    int32 <GetMethods>d__11::<>1__state
0xd11b9  ldc.i4.1
0xd11ba  stloc.0
0xd11bb  leave    loc_D1B92
0xd11c0  ldarg.0
0xd11c1  ldc.i4.m1
0xd11c2  stfld    int32 <GetMethods>d__11::<>1__state
0xd11c7  ldarg.0
0xd11c8  ldarg.0
0xd11c9  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xd11ce  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0xd11d3  ldarg.0
0xd11d4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0xd11d9  ldstr    aCreateinstance// "CreateInstance"
0xd11de  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xd11e3  ldarg.0
0xd11e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0xd11e9  ldc.i4.0
0xd11ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xd11ef  ldarg.0
0xd11f0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0xd11f5  ldc.i4.0
0xd11f6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xd11fb  ldarg.0
0xd11fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0xd1201  ldc.i4   0xFFFFFFF
0xd1206  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xd120b  ldarg.0
0xd120c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0xd1211  ldstr    aCreateinstance_0// "CreateInstance_Client"
0xd1216  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xd121b  ldarg.0
0xd121c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0xd1221  ldc.i4.0
0xd1222  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xd1227  ldarg.0
0xd1228  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0xd122d  ldtoken  [mscorlib]System.Void
0xd1232  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd1237  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xd123c  ldarg.0
0xd123d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0xd1242  ldc.i4.0
0xd1243  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xd1248  ldarg.0
0xd1249  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0xd124e  ldc.i4.0
0xd124f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xd1254  ldarg.0
0xd1255  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0xd125a  ldc.i4.0
0xd125b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0xd1260  ldarg.0
0xd1261  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0xd1266  ldc.i4.0
0xd1267  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xd126c  ldarg.0
0xd126d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0xd1272  ldc.i4.0
0xd1273  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0xd1278  ldarg.0
0xd1279  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<>g__initLocal3
0xd127e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<item>5__13
0xd1283  ldarg.0
0xd1284  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<item>5__13
0xd1289  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xd128e  ldarg.0
0xd128f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xd1294  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal4
0xd1299  ldarg.0
0xd129a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal4
0xd129f  ldstr    aFieldinstanced// "fieldInstanceDotNotation"
0xd12a4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xd12a9  ldarg.0
0xd12aa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal4
0xd12af  ldc.i4.0
0xd12b0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xd12b5  ldarg.0
0xd12b6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal4
0xd12bb  ldtoken  [mscorlib]System.String
0xd12c0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd12c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xd12ca  ldarg.0
0xd12cb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal4
0xd12d0  ldc.i4.1
0xd12d1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xd12d6  ldarg.0
0xd12d7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal4
0xd12dc  ldc.i4.0
0xd12dd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0xd12e2  ldarg.0
0xd12e3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal4
0xd12e8  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd12ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0xd12f2  ldarg.0
0xd12f3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal4
0xd12f8  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0xd12fd  ldarg.0
0xd12fe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__11::<item>5__13
0xd1303  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xd1308  ldarg.0
0xd1309  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xd130e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal5
0xd1313  ldarg.0
0xd1314  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal5
0xd1319  ldstr    aFielddotnotati// "fieldDotNotation"
0xd131e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xd1323  ldarg.0
0xd1324  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal5
0xd1329  ldc.i4.0
0xd132a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xd132f  ldarg.0
0xd1330  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal5
0xd1335  ldtoken  [mscorlib]System.String
0xd133a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd133f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xd1344  ldarg.0
0xd1345  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__11::<>g__initLocal5
0xd134a  ldc.i4.1
  ... truncated ...
```
