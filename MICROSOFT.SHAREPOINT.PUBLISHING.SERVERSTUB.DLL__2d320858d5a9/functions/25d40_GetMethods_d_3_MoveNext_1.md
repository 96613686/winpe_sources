# <GetMethods>d__3::MoveNext_1

- ea: `0x25d40`
- end: `0x2601b`
- name: `<GetMethods>d__3::MoveNext_1`
- size: `731`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xe680`
- `0x25d40`
- `0x26040`
- `0x260a0`

## pseudocode

```c

```

## disassembly

```asm
0x25d40  ldarg.0
0x25d41  ldfld    int32 <GetMethods>d__3::<>1__state
0x25d46  stloc.1
0x25d47  ldloc.1
0x25d48  switch   loc_25D66, loc_2600E, loc_25DD0, loc_25EB7, loc_26007
0x25d61  br       loc_2600E
0x25d66  ldarg.0
0x25d67  ldc.i4.m1
0x25d68  stfld    int32 <GetMethods>d__3::<>1__state
0x25d6d  ldarg.0
0x25d6e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__3::proxyContext
0x25d73  brtrue.s loc_25D80
0x25d75  ldstr    aProxycontext// "proxyContext"
0x25d7a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x25d7f  throw
0x25d80  ldarg.0
0x25d81  ldarg.0
0x25d82  ldfld    class Microsoft.SharePoint.Publishing.SitePageMetadataCollectionServerStub <GetMethods>d__3::<>4__this
0x25d87  ldarg.0
0x25d88  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__3::proxyContext
0x25d8d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Publishing.SitePageMetadataCollectionServerStub::<>n__FabricatedMethod8(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x25d92  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x25d97  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__3::<>7__wrap6
0x25d9c  ldarg.0
0x25d9d  ldc.i4.1
0x25d9e  stfld    int32 <GetMethods>d__3::<>1__state
0x25da3  br.s     loc_25DD7
0x25da5  ldarg.0
0x25da6  ldarg.0
0x25da7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__3::<>7__wrap6
0x25dac  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x25db1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<itemBase>5__4
0x25db6  ldarg.0
0x25db7  ldarg.0
0x25db8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<itemBase>5__4
0x25dbd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>2__current
0x25dc2  ldarg.0
0x25dc3  ldc.i4.2
0x25dc4  stfld    int32 <GetMethods>d__3::<>1__state
0x25dc9  ldc.i4.1
0x25dca  stloc.0
0x25dcb  leave    loc_26019
0x25dd0  ldarg.0
0x25dd1  ldc.i4.1
0x25dd2  stfld    int32 <GetMethods>d__3::<>1__state
0x25dd7  ldarg.0
0x25dd8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__3::<>7__wrap6
0x25ddd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x25de2  brtrue.s loc_25DA5
0x25de4  ldarg.0
0x25de5  call     instance void <GetMethods>d__3::<>m__Finally7()
0x25dea  ldarg.0
0x25deb  ldarg.0
0x25dec  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x25df1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x25df6  ldarg.0
0x25df7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x25dfc  ldstr    aCtor// ".ctor"
0x25e01  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x25e06  ldarg.0
0x25e07  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x25e0c  ldc.i4.0
0x25e0d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x25e12  ldarg.0
0x25e13  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x25e18  ldc.i4.0
0x25e19  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x25e1e  ldarg.0
0x25e1f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x25e24  ldc.i4   0xFFFFFFF
0x25e29  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x25e2e  ldarg.0
0x25e2f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x25e34  ldstr    aCtor// ".ctor"
0x25e39  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x25e3e  ldarg.0
0x25e3f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x25e44  ldc.i4.0
0x25e45  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x25e4a  ldarg.0
0x25e4b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x25e50  ldnull
0x25e51  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x25e56  ldarg.0
0x25e57  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x25e5c  ldc.i4.0
0x25e5d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x25e62  ldarg.0
0x25e63  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x25e68  ldc.i4.0
0x25e69  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x25e6e  ldarg.0
0x25e6f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x25e74  ldc.i4.0
0x25e75  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x25e7a  ldarg.0
0x25e7b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x25e80  ldc.i4.0
0x25e81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x25e86  ldarg.0
0x25e87  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x25e8c  ldc.i4.1
0x25e8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x25e92  ldarg.0
0x25e93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x25e98  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x25e9d  ldarg.0
0x25e9e  ldarg.0
0x25e9f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x25ea4  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>2__current
0x25ea9  ldarg.0
0x25eaa  ldc.i4.3
0x25eab  stfld    int32 <GetMethods>d__3::<>1__state
0x25eb0  ldc.i4.1
0x25eb1  stloc.0
0x25eb2  leave    loc_26019
0x25eb7  ldarg.0
0x25eb8  ldc.i4.m1
0x25eb9  stfld    int32 <GetMethods>d__3::<>1__state
0x25ebe  ldarg.0
0x25ebf  ldarg.0
0x25ec0  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x25ec5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x25eca  ldarg.0
0x25ecb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x25ed0  ldstr    aGetbyid// "GetById"
0x25ed5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x25eda  ldarg.0
0x25edb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x25ee0  ldc.i4.0
0x25ee1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x25ee6  ldarg.0
0x25ee7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x25eec  ldc.i4.1
0x25eed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x25ef2  ldarg.0
0x25ef3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x25ef8  ldc.i4.8
0x25ef9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x25efe  ldarg.0
0x25eff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x25f04  ldstr    aGetbyid// "GetById"
0x25f09  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x25f0e  ldarg.0
0x25f0f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x25f14  ldc.i4.0
0x25f15  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x25f1a  ldarg.0
0x25f1b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x25f20  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata
0x25f25  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25f2a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x25f2f  ldarg.0
0x25f30  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x25f35  ldc.i4.4
0x25f36  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x25f3b  ldarg.0
0x25f3c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x25f41  ldc.i4.0
0x25f42  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x25f47  ldarg.0
0x25f48  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x25f4d  ldc.i4.0
0x25f4e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x25f53  ldarg.0
0x25f54  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x25f59  ldc.i4.0
0x25f5a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x25f5f  ldarg.0
0x25f60  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x25f65  ldc.i4.1
0x25f66  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x25f6b  ldarg.0
0x25f6c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x25f71  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x25f76  ldarg.0
0x25f77  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x25f7c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x25f81  ldarg.0
0x25f82  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x25f87  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x25f8c  ldarg.0
0x25f8d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x25f92  ldstr    aId_0// "id"
0x25f97  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x25f9c  ldarg.0
0x25f9d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x25fa2  ldc.i4.0
0x25fa3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x25fa8  ldarg.0
0x25fa9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x25fae  ldtoken  [mscorlib]System.Int32
0x25fb3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25fb8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x25fbd  ldarg.0
0x25fbe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x25fc3  ldc.i4.1
0x25fc4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x25fc9  ldarg.0
0x25fca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x25fcf  ldc.i4.0
0x25fd0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x25fd5  ldarg.0
0x25fd6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x25fdb  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x25fe0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x25fe5  ldarg.0
0x25fe6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__3::<>g__initLocal2
0x25feb  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x25ff0  ldarg.0
0x25ff1  ldarg.0
0x25ff2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x25ff7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>2__current
0x25ffc  ldarg.0
0x25ffd  ldc.i4.4
0x25ffe  stfld    int32 <GetMethods>d__3::<>1__state
0x26003  ldc.i4.1
0x26004  stloc.0
0x26005  leave.s  loc_26019
0x26007  ldarg.0
0x26008  ldc.i4.m1
0x26009  stfld    int32 <GetMethods>d__3::<>1__state
0x2600e  ldc.i4.0
0x2600f  stloc.0
0x26010  leave.s  loc_26019
0x26012  ldarg.0
0x26013  call     instance void <GetMethods>d__3::System.IDisposable.Dispose()
0x26018  endfinally
0x26019  ldloc.0
0x2601a  ret
```
