# <GetMethods>d__b::MoveNext

- ea: `0xe8cb0`
- end: `0xe948c`
- name: `<GetMethods>d__b::MoveNext`
- size: `2012`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x22690`
- `0xe8cb0`
- `0xe94b0`
- `0xe9510`

## string_xrefs

- `0xe9341`: `GetServiceUrls`
- `0xe9375`: `GetServiceUrls`
- `0xe91ee`: `GetServiceInternalUrls`
- `0xe9222`: `GetServiceInternalUrls`
- `0xe8e4c`: `AddMicroserviceWorkItem`
- `0xe8e84`: `AddMicroserviceWorkItem`
- `0xe9097`: `DeleteMicroserviceWorkItem`
- `0xe90cf`: `DeleteMicroserviceWorkItem`
- `0xe92b0`: `service`
- `0xe9403`: `service`

## pseudocode

```c

```

## disassembly

```asm
0xe8cb0  ldarg.0
0xe8cb1  ldfld    int32 <GetMethods>d__b::<>1__state
0xe8cb6  stloc.1
0xe8cb7  ldloc.1
0xe8cb8  switch   loc_E8CE2, loc_E947F, loc_E8D4C, loc_E8E33, loc_E907E, loc_E91D5, loc_E9328, loc_E9478
0xe8cdd  br       loc_E947F
0xe8ce2  ldarg.0
0xe8ce3  ldc.i4.m1
0xe8ce4  stfld    int32 <GetMethods>d__b::<>1__state
0xe8ce9  ldarg.0
0xe8cea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__b::proxyContext
0xe8cef  brtrue.s loc_E8CFC
0xe8cf1  ldstr    aProxycontext// "proxyContext"
0xe8cf6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe8cfb  throw
0xe8cfc  ldarg.0
0xe8cfd  ldarg.0
0xe8cfe  ldfld    class Microsoft.SharePoint.MicroService.MicroServiceManagerServerStub <GetMethods>d__b::<>4__this
0xe8d03  ldarg.0
0xe8d04  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__b::proxyContext
0xe8d09  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.MicroService.MicroServiceManagerServerStub::<>n__FabricatedMethod10(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext name)
0xe8d0e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0xe8d13  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__b::<>7__wrape
0xe8d18  ldarg.0
0xe8d19  ldc.i4.1
0xe8d1a  stfld    int32 <GetMethods>d__b::<>1__state
0xe8d1f  br.s     loc_E8D53
0xe8d21  ldarg.0
0xe8d22  ldarg.0
0xe8d23  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__b::<>7__wrape
0xe8d28  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0xe8d2d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<itemBase>5__c
0xe8d32  ldarg.0
0xe8d33  ldarg.0
0xe8d34  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<itemBase>5__c
0xe8d39  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>2__current
0xe8d3e  ldarg.0
0xe8d3f  ldc.i4.2
0xe8d40  stfld    int32 <GetMethods>d__b::<>1__state
0xe8d45  ldc.i4.1
0xe8d46  stloc.0
0xe8d47  leave    loc_E948A
0xe8d4c  ldarg.0
0xe8d4d  ldc.i4.1
0xe8d4e  stfld    int32 <GetMethods>d__b::<>1__state
0xe8d53  ldarg.0
0xe8d54  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__b::<>7__wrape
0xe8d59  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe8d5e  brtrue.s loc_E8D21
0xe8d60  ldarg.0
0xe8d61  call     instance void <GetMethods>d__b::<>m__Finallyf()
0xe8d66  ldarg.0
0xe8d67  ldarg.0
0xe8d68  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xe8d6d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal0
0xe8d72  ldarg.0
0xe8d73  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal0
0xe8d78  ldstr    aCtor// ".ctor"
0xe8d7d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xe8d82  ldarg.0
0xe8d83  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal0
0xe8d88  ldc.i4.0
0xe8d89  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xe8d8e  ldarg.0
0xe8d8f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal0
0xe8d94  ldc.i4.0
0xe8d95  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xe8d9a  ldarg.0
0xe8d9b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal0
0xe8da0  ldc.i4   0xFFFFFFF
0xe8da5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xe8daa  ldarg.0
0xe8dab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal0
0xe8db0  ldstr    aCtor// ".ctor"
0xe8db5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xe8dba  ldarg.0
0xe8dbb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal0
0xe8dc0  ldc.i4.0
0xe8dc1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xe8dc6  ldarg.0
0xe8dc7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal0
0xe8dcc  ldnull
0xe8dcd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xe8dd2  ldarg.0
0xe8dd3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal0
0xe8dd8  ldc.i4.0
0xe8dd9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe8dde  ldarg.0
0xe8ddf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal0
0xe8de4  ldc.i4.0
0xe8de5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xe8dea  ldarg.0
0xe8deb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal0
0xe8df0  ldc.i4.0
0xe8df1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0xe8df6  ldarg.0
0xe8df7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal0
0xe8dfc  ldc.i4.0
0xe8dfd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xe8e02  ldarg.0
0xe8e03  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal0
0xe8e08  ldc.i4.0
0xe8e09  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0xe8e0e  ldarg.0
0xe8e0f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal0
0xe8e14  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<item>5__d
0xe8e19  ldarg.0
0xe8e1a  ldarg.0
0xe8e1b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<item>5__d
0xe8e20  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>2__current
0xe8e25  ldarg.0
0xe8e26  ldc.i4.3
0xe8e27  stfld    int32 <GetMethods>d__b::<>1__state
0xe8e2c  ldc.i4.1
0xe8e2d  stloc.0
0xe8e2e  leave    loc_E948A
0xe8e33  ldarg.0
0xe8e34  ldc.i4.m1
0xe8e35  stfld    int32 <GetMethods>d__b::<>1__state
0xe8e3a  ldarg.0
0xe8e3b  ldarg.0
0xe8e3c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xe8e41  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal1
0xe8e46  ldarg.0
0xe8e47  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal1
0xe8e4c  ldstr    aAddmicroservic// "AddMicroserviceWorkItem"
0xe8e51  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xe8e56  ldarg.0
0xe8e57  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal1
0xe8e5c  ldc.i4.0
0xe8e5d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xe8e62  ldarg.0
0xe8e63  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal1
0xe8e68  ldc.i4.0
0xe8e69  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xe8e6e  ldarg.0
0xe8e6f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal1
0xe8e74  ldc.i4   0xFFFFFFF
0xe8e79  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xe8e7e  ldarg.0
0xe8e7f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal1
0xe8e84  ldstr    aAddmicroservic// "AddMicroserviceWorkItem"
0xe8e89  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xe8e8e  ldarg.0
0xe8e8f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal1
0xe8e94  ldc.i4.0
0xe8e95  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xe8e9a  ldarg.0
0xe8e9b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal1
0xe8ea0  ldtoken  [mscorlib]System.Guid
0xe8ea5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe8eaa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xe8eaf  ldarg.0
0xe8eb0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal1
0xe8eb5  ldc.i4.1
0xe8eb6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe8ebb  ldarg.0
0xe8ebc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal1
0xe8ec1  ldc.i4.0
0xe8ec2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xe8ec7  ldarg.0
0xe8ec8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal1
0xe8ecd  ldc.i4.0
0xe8ece  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0xe8ed3  ldarg.0
0xe8ed4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal1
0xe8ed9  ldc.i4.0
0xe8eda  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xe8edf  ldarg.0
0xe8ee0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal1
0xe8ee5  ldc.i4.1
0xe8ee6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0xe8eeb  ldarg.0
0xe8eec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal1
0xe8ef1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<item>5__d
0xe8ef6  ldarg.0
0xe8ef7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<item>5__d
0xe8efc  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xe8f01  ldarg.0
0xe8f02  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xe8f07  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal2
0xe8f0c  ldarg.0
0xe8f0d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal2
0xe8f12  ldstr    aPayload// "payLoad"
0xe8f17  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xe8f1c  ldarg.0
0xe8f1d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal2
0xe8f22  ldc.i4.0
0xe8f23  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xe8f28  ldarg.0
0xe8f29  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal2
0xe8f2e  ldtoken  unsigned int8[]
0xe8f33  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe8f38  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xe8f3d  ldarg.0
0xe8f3e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal2
0xe8f43  ldc.i4.1
0xe8f44  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe8f49  ldarg.0
0xe8f4a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal2
0xe8f4f  ldc.i4.0
0xe8f50  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0xe8f55  ldarg.0
0xe8f56  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal2
0xe8f5b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xe8f60  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0xe8f65  ldarg.0
0xe8f66  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal2
0xe8f6b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0xe8f70  ldarg.0
0xe8f71  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<item>5__d
0xe8f76  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xe8f7b  ldarg.0
0xe8f7c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xe8f81  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal3
0xe8f86  ldarg.0
0xe8f87  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal3
0xe8f8c  ldstr    aMinutes// "minutes"
0xe8f91  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xe8f96  ldarg.0
0xe8f97  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal3
0xe8f9c  ldc.i4.0
0xe8f9d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xe8fa2  ldarg.0
0xe8fa3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal3
0xe8fa8  ldtoken  [mscorlib]System.Int32
0xe8fad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe8fb2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xe8fb7  ldarg.0
0xe8fb8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal3
0xe8fbd  ldc.i4.1
0xe8fbe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe8fc3  ldarg.0
0xe8fc4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal3
0xe8fc9  ldc.i4.0
0xe8fca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0xe8fcf  ldarg.0
0xe8fd0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal3
0xe8fd5  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xe8fda  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0xe8fdf  ldarg.0
0xe8fe0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal3
0xe8fe5  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0xe8fea  ldarg.0
0xe8feb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<item>5__d
0xe8ff0  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xe8ff5  ldarg.0
0xe8ff6  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xe8ffb  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal4
0xe9000  ldarg.0
0xe9001  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal4
0xe9006  ldstr    aProperties_0// "properties"
0xe900b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xe9010  ldarg.0
0xe9011  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal4
0xe9016  ldc.i4.0
0xe9017  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xe901c  ldarg.0
0xe901d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal4
0xe9022  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.MicroService.MicroServiceWorkItemProperties
0xe9027  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe902c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xe9031  ldarg.0
0xe9032  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal4
0xe9037  ldc.i4.2
0xe9038  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xe903d  ldarg.0
0xe903e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal4
0xe9043  ldc.i4.0
0xe9044  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0xe9049  ldarg.0
0xe904a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal4
0xe904f  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xe9054  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0xe9059  ldarg.0
0xe905a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__b::<>g__initLocal4
0xe905f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0xe9064  ldarg.0
0xe9065  ldarg.0
0xe9066  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<item>5__d
0xe906b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>2__current
0xe9070  ldarg.0
0xe9071  ldc.i4.4
0xe9072  stfld    int32 <GetMethods>d__b::<>1__state
0xe9077  ldc.i4.1
0xe9078  stloc.0
0xe9079  leave    loc_E948A
0xe907e  ldarg.0
0xe907f  ldc.i4.m1
0xe9080  stfld    int32 <GetMethods>d__b::<>1__state
0xe9085  ldarg.0
0xe9086  ldarg.0
0xe9087  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xe908c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal5
0xe9091  ldarg.0
0xe9092  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal5
0xe9097  ldstr    aDeletemicroser// "DeleteMicroserviceWorkItem"
0xe909c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xe90a1  ldarg.0
0xe90a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__b::<>g__initLocal5
  ... truncated ...
```
