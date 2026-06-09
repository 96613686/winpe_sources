# <GetMethods>d__10::MoveNext

- ea: `0xd1cc0`
- end: `0xd27da`
- name: `<GetMethods>d__10::MoveNext`
- size: `2842`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x11ff0`
- `0xd1cc0`
- `0xd2800`
- `0xd2860`

## string_xrefs

- `0xd1f61`: `CreateInstance`
- `0xd1d90`: `CreateCollectionInstance`
- `0xd2132`: `FromXml`
- `0xd2704`: `ToXml`
- `0xd1dc8`: `CreateCollectionInstance_Client`
- `0xd1f99`: `CreateInstance_Client`
- `0xd216a`: `FromXml_Client`
- `0xd273c`: `ToXml_Client`

## pseudocode

```c

```

## disassembly

```asm
0xd1cc0  ldarg.0
0xd1cc1  ldfld    int32 <GetMethods>d__10::<>1__state
0xd1cc6  stloc.1
0xd1cc7  ldloc.1
0xd1cc8  switch   loc_D1CFA, loc_D27CD, loc_D1D64, loc_D1F48, loc_D2119, loc_D2270, loc_D23C7, loc_D251A, loc_D26EB, loc_D27C6
0xd1cf5  br       loc_D27CD
0xd1cfa  ldarg.0
0xd1cfb  ldc.i4.m1
0xd1cfc  stfld    int32 <GetMethods>d__10::<>1__state
0xd1d01  ldarg.0
0xd1d02  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__10::proxyContext
0xd1d07  brtrue.s loc_D1D14
0xd1d09  ldstr    aProxycontext// "proxyContext"
0xd1d0e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd1d13  throw
0xd1d14  ldarg.0
0xd1d15  ldarg.0
0xd1d16  ldfld    class Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub <GetMethods>d__10::<>4__this
0xd1d1b  ldarg.0
0xd1d1c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__10::proxyContext
0xd1d21  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::<>n__FabricatedMethod15(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0xd1d26  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0xd1d2b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__10::<>7__wrap13
0xd1d30  ldarg.0
0xd1d31  ldc.i4.1
0xd1d32  stfld    int32 <GetMethods>d__10::<>1__state
0xd1d37  br.s     loc_D1D6B
0xd1d39  ldarg.0
0xd1d3a  ldarg.0
0xd1d3b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__10::<>7__wrap13
0xd1d40  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0xd1d45  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<itemBase>5__11
0xd1d4a  ldarg.0
0xd1d4b  ldarg.0
0xd1d4c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<itemBase>5__11
0xd1d51  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>2__current
0xd1d56  ldarg.0
0xd1d57  ldc.i4.2
0xd1d58  stfld    int32 <GetMethods>d__10::<>1__state
0xd1d5d  ldc.i4.1
0xd1d5e  stloc.0
0xd1d5f  leave    loc_D27D8
0xd1d64  ldarg.0
0xd1d65  ldc.i4.1
0xd1d66  stfld    int32 <GetMethods>d__10::<>1__state
0xd1d6b  ldarg.0
0xd1d6c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__10::<>7__wrap13
0xd1d71  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd1d76  brtrue.s loc_D1D39
0xd1d78  ldarg.0
0xd1d79  call     instance void <GetMethods>d__10::<>m__Finally14()
0xd1d7e  ldarg.0
0xd1d7f  ldarg.0
0xd1d80  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xd1d85  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0xd1d8a  ldarg.0
0xd1d8b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0xd1d90  ldstr    aCreatecollecti// "CreateCollectionInstance"
0xd1d95  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xd1d9a  ldarg.0
0xd1d9b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0xd1da0  ldc.i4.0
0xd1da1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xd1da6  ldarg.0
0xd1da7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0xd1dac  ldc.i4.0
0xd1dad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xd1db2  ldarg.0
0xd1db3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0xd1db8  ldc.i4   0xFFFFFFF
0xd1dbd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xd1dc2  ldarg.0
0xd1dc3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0xd1dc8  ldstr    aCreatecollecti_0// "CreateCollectionInstance_Client"
0xd1dcd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xd1dd2  ldarg.0
0xd1dd3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0xd1dd8  ldc.i4.0
0xd1dd9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xd1dde  ldarg.0
0xd1ddf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0xd1de4  ldtoken  [mscorlib]System.Void
0xd1de9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd1dee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xd1df3  ldarg.0
0xd1df4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0xd1df9  ldc.i4.0
0xd1dfa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xd1dff  ldarg.0
0xd1e00  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0xd1e05  ldc.i4.0
0xd1e06  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xd1e0b  ldarg.0
0xd1e0c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0xd1e11  ldc.i4.0
0xd1e12  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0xd1e17  ldarg.0
0xd1e18  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0xd1e1d  ldc.i4.0
0xd1e1e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xd1e23  ldarg.0
0xd1e24  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0xd1e29  ldc.i4.0
0xd1e2a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0xd1e2f  ldarg.0
0xd1e30  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal0
0xd1e35  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0xd1e3a  ldarg.0
0xd1e3b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0xd1e40  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xd1e45  ldarg.0
0xd1e46  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xd1e4b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0xd1e50  ldarg.0
0xd1e51  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0xd1e56  ldstr    aFielddotnotati// "fieldDotNotation"
0xd1e5b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xd1e60  ldarg.0
0xd1e61  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0xd1e66  ldc.i4.0
0xd1e67  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xd1e6c  ldarg.0
0xd1e6d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0xd1e72  ldtoken  [mscorlib]System.String
0xd1e77  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd1e7c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xd1e81  ldarg.0
0xd1e82  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0xd1e87  ldc.i4.1
0xd1e88  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xd1e8d  ldarg.0
0xd1e8e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0xd1e93  ldc.i4.0
0xd1e94  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0xd1e99  ldarg.0
0xd1e9a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0xd1e9f  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd1ea4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0xd1ea9  ldarg.0
0xd1eaa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal1
0xd1eaf  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0xd1eb4  ldarg.0
0xd1eb5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0xd1eba  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xd1ebf  ldarg.0
0xd1ec0  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xd1ec5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0xd1eca  ldarg.0
0xd1ecb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0xd1ed0  ldstr    aSize// "size"
0xd1ed5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xd1eda  ldarg.0
0xd1edb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0xd1ee0  ldc.i4.0
0xd1ee1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xd1ee6  ldarg.0
0xd1ee7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0xd1eec  ldtoken  [mscorlib]System.Int32
0xd1ef1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd1ef6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xd1efb  ldarg.0
0xd1efc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0xd1f01  ldc.i4.1
0xd1f02  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xd1f07  ldarg.0
0xd1f08  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0xd1f0d  ldc.i4.0
0xd1f0e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0xd1f13  ldarg.0
0xd1f14  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0xd1f19  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd1f1e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0xd1f23  ldarg.0
0xd1f24  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal2
0xd1f29  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0xd1f2e  ldarg.0
0xd1f2f  ldarg.0
0xd1f30  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0xd1f35  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>2__current
0xd1f3a  ldarg.0
0xd1f3b  ldc.i4.3
0xd1f3c  stfld    int32 <GetMethods>d__10::<>1__state
0xd1f41  ldc.i4.1
0xd1f42  stloc.0
0xd1f43  leave    loc_D27D8
0xd1f48  ldarg.0
0xd1f49  ldc.i4.m1
0xd1f4a  stfld    int32 <GetMethods>d__10::<>1__state
0xd1f4f  ldarg.0
0xd1f50  ldarg.0
0xd1f51  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xd1f56  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0xd1f5b  ldarg.0
0xd1f5c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0xd1f61  ldstr    aCreateinstance// "CreateInstance"
0xd1f66  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xd1f6b  ldarg.0
0xd1f6c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0xd1f71  ldc.i4.0
0xd1f72  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xd1f77  ldarg.0
0xd1f78  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0xd1f7d  ldc.i4.0
0xd1f7e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xd1f83  ldarg.0
0xd1f84  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0xd1f89  ldc.i4   0xFFFFFFF
0xd1f8e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xd1f93  ldarg.0
0xd1f94  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0xd1f99  ldstr    aCreateinstance_0// "CreateInstance_Client"
0xd1f9e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xd1fa3  ldarg.0
0xd1fa4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0xd1fa9  ldc.i4.0
0xd1faa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xd1faf  ldarg.0
0xd1fb0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0xd1fb5  ldtoken  [mscorlib]System.Void
0xd1fba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd1fbf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xd1fc4  ldarg.0
0xd1fc5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0xd1fca  ldc.i4.0
0xd1fcb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xd1fd0  ldarg.0
0xd1fd1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0xd1fd6  ldc.i4.0
0xd1fd7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xd1fdc  ldarg.0
0xd1fdd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0xd1fe2  ldc.i4.0
0xd1fe3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0xd1fe8  ldarg.0
0xd1fe9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0xd1fee  ldc.i4.0
0xd1fef  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xd1ff4  ldarg.0
0xd1ff5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0xd1ffa  ldc.i4.0
0xd1ffb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0xd2000  ldarg.0
0xd2001  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<>g__initLocal3
0xd2006  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0xd200b  ldarg.0
0xd200c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0xd2011  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xd2016  ldarg.0
0xd2017  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xd201c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal4
0xd2021  ldarg.0
0xd2022  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal4
0xd2027  ldstr    aFieldinstanced// "fieldInstanceDotNotation"
0xd202c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xd2031  ldarg.0
0xd2032  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal4
0xd2037  ldc.i4.0
0xd2038  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xd203d  ldarg.0
0xd203e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal4
0xd2043  ldtoken  [mscorlib]System.String
0xd2048  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd204d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xd2052  ldarg.0
0xd2053  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal4
0xd2058  ldc.i4.1
0xd2059  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xd205e  ldarg.0
0xd205f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal4
0xd2064  ldc.i4.0
0xd2065  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0xd206a  ldarg.0
0xd206b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal4
0xd2070  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd2075  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0xd207a  ldarg.0
0xd207b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal4
0xd2080  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0xd2085  ldarg.0
0xd2086  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__10::<item>5__12
0xd208b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xd2090  ldarg.0
0xd2091  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xd2096  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal5
0xd209b  ldarg.0
0xd209c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal5
0xd20a1  ldstr    aFielddotnotati// "fieldDotNotation"
0xd20a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xd20ab  ldarg.0
0xd20ac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal5
0xd20b1  ldc.i4.0
0xd20b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xd20b7  ldarg.0
0xd20b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal5
0xd20bd  ldtoken  [mscorlib]System.String
0xd20c2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd20c7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xd20cc  ldarg.0
0xd20cd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__10::<>g__initLocal5
0xd20d2  ldc.i4.1
  ... truncated ...
```
