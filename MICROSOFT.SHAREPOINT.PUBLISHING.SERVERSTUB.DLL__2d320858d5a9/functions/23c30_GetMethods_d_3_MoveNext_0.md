# <GetMethods>d__3::MoveNext_0

- ea: `0x23c30`
- end: `0x23f10`
- name: `<GetMethods>d__3::MoveNext_0`
- size: `736`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xd100`
- `0x23c30`
- `0x23f30`
- `0x23f90`

## pseudocode

```c

```

## disassembly

```asm
0x23c30  ldarg.0
0x23c31  ldfld    int32 <GetMethods>d__3::<>1__state
0x23c36  stloc.1
0x23c37  ldloc.1
0x23c38  switch   loc_23C56, loc_23F03, loc_23CC0, loc_23DAC, loc_23EFC
0x23c51  br       loc_23F03
0x23c56  ldarg.0
0x23c57  ldc.i4.m1
0x23c58  stfld    int32 <GetMethods>d__3::<>1__state
0x23c5d  ldarg.0
0x23c5e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__3::proxyContext
0x23c63  brtrue.s loc_23C70
0x23c65  ldstr    aProxycontext// "proxyContext"
0x23c6a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x23c6f  throw
0x23c70  ldarg.0
0x23c71  ldarg.0
0x23c72  ldfld    class Microsoft.SharePoint.Publishing.SiteImageRenditionsServerStub <GetMethods>d__3::<>4__this
0x23c77  ldarg.0
0x23c78  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__3::proxyContext
0x23c7d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Publishing.SiteImageRenditionsServerStub::<>n__FabricatedMethod8(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x23c82  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x23c87  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__3::<>7__wrap6
0x23c8c  ldarg.0
0x23c8d  ldc.i4.1
0x23c8e  stfld    int32 <GetMethods>d__3::<>1__state
0x23c93  br.s     loc_23CC7
0x23c95  ldarg.0
0x23c96  ldarg.0
0x23c97  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__3::<>7__wrap6
0x23c9c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x23ca1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<itemBase>5__4
0x23ca6  ldarg.0
0x23ca7  ldarg.0
0x23ca8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<itemBase>5__4
0x23cad  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>2__current
0x23cb2  ldarg.0
0x23cb3  ldc.i4.2
0x23cb4  stfld    int32 <GetMethods>d__3::<>1__state
0x23cb9  ldc.i4.1
0x23cba  stloc.0
0x23cbb  leave    loc_23F0E
0x23cc0  ldarg.0
0x23cc1  ldc.i4.1
0x23cc2  stfld    int32 <GetMethods>d__3::<>1__state
0x23cc7  ldarg.0
0x23cc8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__3::<>7__wrap6
0x23ccd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x23cd2  brtrue.s loc_23C95
0x23cd4  ldarg.0
0x23cd5  call     instance void <GetMethods>d__3::<>m__Finally7()
0x23cda  ldarg.0
0x23cdb  ldarg.0
0x23cdc  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x23ce1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23ce6  ldarg.0
0x23ce7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23cec  ldstr    aGetrenditions// "GetRenditions"
0x23cf1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x23cf6  ldarg.0
0x23cf7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23cfc  ldc.i4.1
0x23cfd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x23d02  ldarg.0
0x23d03  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23d08  ldc.i4.0
0x23d09  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x23d0e  ldarg.0
0x23d0f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23d14  ldc.i4.7
0x23d15  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x23d1a  ldarg.0
0x23d1b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23d20  ldstr    aGetrenditionsc// "GetRenditionsCsom"
0x23d25  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x23d2a  ldarg.0
0x23d2b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23d30  ldc.i4.0
0x23d31  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x23d36  ldarg.0
0x23d37  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23d3c  ldtoken  class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ImageRendition>
0x23d41  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23d46  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x23d4b  ldarg.0
0x23d4c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23d51  ldc.i4.3
0x23d52  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x23d57  ldarg.0
0x23d58  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23d5d  ldc.i4.0
0x23d5e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x23d63  ldarg.0
0x23d64  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23d69  ldc.i4.0
0x23d6a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x23d6f  ldarg.0
0x23d70  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23d75  ldc.i4.0
0x23d76  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x23d7b  ldarg.0
0x23d7c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23d81  ldc.i4.0
0x23d82  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x23d87  ldarg.0
0x23d88  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x23d8d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x23d92  ldarg.0
0x23d93  ldarg.0
0x23d94  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x23d99  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>2__current
0x23d9e  ldarg.0
0x23d9f  ldc.i4.3
0x23da0  stfld    int32 <GetMethods>d__3::<>1__state
0x23da5  ldc.i4.1
0x23da6  stloc.0
0x23da7  leave    loc_23F0E
0x23dac  ldarg.0
0x23dad  ldc.i4.m1
0x23dae  stfld    int32 <GetMethods>d__3::<>1__state
0x23db3  ldarg.0
0x23db4  ldarg.0
0x23db5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x23dba  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23dbf  ldarg.0
0x23dc0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23dc5  ldstr    aSetrenditions// "SetRenditions"
0x23dca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x23dcf  ldarg.0
0x23dd0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23dd5  ldc.i4.1
0x23dd6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x23ddb  ldarg.0
0x23ddc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23de1  ldc.i4.0
0x23de2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x23de7  ldarg.0
0x23de8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23ded  ldc.i4.7
0x23dee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x23df3  ldarg.0
0x23df4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23df9  ldstr    aSetrenditionsc// "SetRenditionsCsom"
0x23dfe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x23e03  ldarg.0
0x23e04  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23e09  ldc.i4.0
0x23e0a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x23e0f  ldarg.0
0x23e10  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23e15  ldtoken  [mscorlib]System.Void
0x23e1a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23e1f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x23e24  ldarg.0
0x23e25  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23e2a  ldc.i4.0
0x23e2b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x23e30  ldarg.0
0x23e31  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23e36  ldc.i4.0
0x23e37  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x23e3c  ldarg.0
0x23e3d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23e42  ldc.i4.0
0x23e43  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x23e48  ldarg.0
0x23e49  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23e4e  ldc.i4.0
0x23e4f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x23e54  ldarg.0
0x23e55  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23e5a  ldc.i4.0
0x23e5b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x23e60  ldarg.0
0x23e61  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x23e66  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x23e6b  ldarg.0
0x23e6c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x23e71  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x23e76  ldarg.0
0x23e77  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x23e7c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x23e81  ldarg.0
0x23e82  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x23e87  ldstr    aRenditions// "renditions"
0x23e8c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x23e91  ldarg.0
0x23e92  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x23e97  ldc.i4.0
0x23e98  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x23e9d  ldarg.0
0x23e9e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x23ea3  ldtoken  class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ImageRendition>
0x23ea8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23ead  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x23eb2  ldarg.0
0x23eb3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x23eb8  ldc.i4.3
0x23eb9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x23ebe  ldarg.0
0x23ebf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x23ec4  ldc.i4.0
0x23ec5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x23eca  ldarg.0
0x23ecb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x23ed0  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x23ed5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x23eda  ldarg.0
0x23edb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x23ee0  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x23ee5  ldarg.0
0x23ee6  ldarg.0
0x23ee7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x23eec  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>2__current
0x23ef1  ldarg.0
0x23ef2  ldc.i4.4
0x23ef3  stfld    int32 <GetMethods>d__3::<>1__state
0x23ef8  ldc.i4.1
0x23ef9  stloc.0
0x23efa  leave.s  loc_23F0E
0x23efc  ldarg.0
0x23efd  ldc.i4.m1
0x23efe  stfld    int32 <GetMethods>d__3::<>1__state
0x23f03  ldc.i4.0
0x23f04  stloc.0
0x23f05  leave.s  loc_23F0E
0x23f07  ldarg.0
0x23f08  call     instance void <GetMethods>d__3::System.IDisposable.Dispose()
0x23f0d  endfinally
0x23f0e  ldloc.0
0x23f0f  ret
```
