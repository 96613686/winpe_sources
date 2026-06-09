# <GetMethods>d__3::MoveNext_5

- ea: `0x13f390`
- end: `0x13f6d8`
- name: `<GetMethods>d__3::MoveNext_5`
- size: `840`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callees

- `0x63ff0`
- `0x13f390`
- `0x13f700`
- `0x13f760`

## string_xrefs

- `0x13f52d`: `Update`
- `0x13f561`: `Update`
- `0x13f450`: `Delete`
- `0x13f488`: `Delete`
- `0x13f606`: `UpdateWithFieldValues`
- `0x13f63b`: `UpdateWithFieldValues`

## pseudocode

```c

```

## disassembly

```asm
0x13f390  ldarg.0
0x13f391  ldfld    int32 <GetMethods>d__3::<>1__state
0x13f396  stloc.1
0x13f397  ldloc.1
0x13f398  switch   loc_13F3BA, loc_13F6CB, loc_13F424, loc_13F514, loc_13F5ED, loc_13F6C4
0x13f3b5  br       loc_13F6CB
0x13f3ba  ldarg.0
0x13f3bb  ldc.i4.m1
0x13f3bc  stfld    int32 <GetMethods>d__3::<>1__state
0x13f3c1  ldarg.0
0x13f3c2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__3::proxyContext
0x13f3c7  brtrue.s loc_13F3D4
0x13f3c9  ldstr    aProxycontext// "proxyContext"
0x13f3ce  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13f3d3  throw
0x13f3d4  ldarg.0
0x13f3d5  ldarg.0
0x13f3d6  ldfld    class Microsoft.SharePoint.ServerStub.SPHubSiteServerStub <GetMethods>d__3::<>4__this
0x13f3db  ldarg.0
0x13f3dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__3::proxyContext
0x13f3e1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPHubSiteServerStub::<>n__FabricatedMethod8(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x13f3e6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x13f3eb  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__3::<>7__wrap6
0x13f3f0  ldarg.0
0x13f3f1  ldc.i4.1
0x13f3f2  stfld    int32 <GetMethods>d__3::<>1__state
0x13f3f7  br.s     loc_13F42B
0x13f3f9  ldarg.0
0x13f3fa  ldarg.0
0x13f3fb  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__3::<>7__wrap6
0x13f400  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x13f405  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<itemBase>5__4
0x13f40a  ldarg.0
0x13f40b  ldarg.0
0x13f40c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<itemBase>5__4
0x13f411  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>2__current
0x13f416  ldarg.0
0x13f417  ldc.i4.2
0x13f418  stfld    int32 <GetMethods>d__3::<>1__state
0x13f41d  ldc.i4.1
0x13f41e  stloc.0
0x13f41f  leave    loc_13F6D6
0x13f424  ldarg.0
0x13f425  ldc.i4.1
0x13f426  stfld    int32 <GetMethods>d__3::<>1__state
0x13f42b  ldarg.0
0x13f42c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__3::<>7__wrap6
0x13f431  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13f436  brtrue.s loc_13F3F9
0x13f438  ldarg.0
0x13f439  call     instance void <GetMethods>d__3::<>m__Finally7()
0x13f43e  ldarg.0
0x13f43f  ldarg.0
0x13f440  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x13f445  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x13f44a  ldarg.0
0x13f44b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x13f450  ldstr    aDelete// "Delete"
0x13f455  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x13f45a  ldarg.0
0x13f45b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x13f460  ldc.i4.0
0x13f461  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x13f466  ldarg.0
0x13f467  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x13f46c  ldc.i4.0
0x13f46d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x13f472  ldarg.0
0x13f473  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x13f478  ldc.i4   0xFFFFFFF
0x13f47d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x13f482  ldarg.0
0x13f483  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x13f488  ldstr    aDelete// "Delete"
0x13f48d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x13f492  ldarg.0
0x13f493  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x13f498  ldc.i4.0
0x13f499  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x13f49e  ldarg.0
0x13f49f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x13f4a4  ldtoken  [mscorlib]System.Void
0x13f4a9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13f4ae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x13f4b3  ldarg.0
0x13f4b4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x13f4b9  ldc.i4.0
0x13f4ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13f4bf  ldarg.0
0x13f4c0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x13f4c5  ldc.i4.0
0x13f4c6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x13f4cb  ldarg.0
0x13f4cc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x13f4d1  ldc.i4.0
0x13f4d2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x13f4d7  ldarg.0
0x13f4d8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x13f4dd  ldc.i4.0
0x13f4de  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x13f4e3  ldarg.0
0x13f4e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x13f4e9  ldc.i4.0
0x13f4ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x13f4ef  ldarg.0
0x13f4f0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal0
0x13f4f5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x13f4fa  ldarg.0
0x13f4fb  ldarg.0
0x13f4fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x13f501  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>2__current
0x13f506  ldarg.0
0x13f507  ldc.i4.3
0x13f508  stfld    int32 <GetMethods>d__3::<>1__state
0x13f50d  ldc.i4.1
0x13f50e  stloc.0
0x13f50f  leave    loc_13F6D6
0x13f514  ldarg.0
0x13f515  ldc.i4.m1
0x13f516  stfld    int32 <GetMethods>d__3::<>1__state
0x13f51b  ldarg.0
0x13f51c  ldarg.0
0x13f51d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x13f522  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x13f527  ldarg.0
0x13f528  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x13f52d  ldstr    aUpdate// "Update"
0x13f532  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x13f537  ldarg.0
0x13f538  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x13f53d  ldc.i4.0
0x13f53e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x13f543  ldarg.0
0x13f544  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x13f549  ldc.i4.0
0x13f54a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x13f54f  ldarg.0
0x13f550  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x13f555  ldc.i4.7
0x13f556  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x13f55b  ldarg.0
0x13f55c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x13f561  ldstr    aUpdate// "Update"
0x13f566  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x13f56b  ldarg.0
0x13f56c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x13f571  ldc.i4.0
0x13f572  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x13f577  ldarg.0
0x13f578  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x13f57d  ldtoken  [mscorlib]System.Void
0x13f582  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13f587  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x13f58c  ldarg.0
0x13f58d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x13f592  ldc.i4.0
0x13f593  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13f598  ldarg.0
0x13f599  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x13f59e  ldc.i4.0
0x13f59f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x13f5a4  ldarg.0
0x13f5a5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x13f5aa  ldc.i4.0
0x13f5ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x13f5b0  ldarg.0
0x13f5b1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x13f5b6  ldc.i4.0
0x13f5b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x13f5bc  ldarg.0
0x13f5bd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x13f5c2  ldc.i4.1
0x13f5c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x13f5c8  ldarg.0
0x13f5c9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal1
0x13f5ce  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x13f5d3  ldarg.0
0x13f5d4  ldarg.0
0x13f5d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x13f5da  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>2__current
0x13f5df  ldarg.0
0x13f5e0  ldc.i4.4
0x13f5e1  stfld    int32 <GetMethods>d__3::<>1__state
0x13f5e6  ldc.i4.1
0x13f5e7  stloc.0
0x13f5e8  leave    loc_13F6D6
0x13f5ed  ldarg.0
0x13f5ee  ldc.i4.m1
0x13f5ef  stfld    int32 <GetMethods>d__3::<>1__state
0x13f5f4  ldarg.0
0x13f5f5  ldarg.0
0x13f5f6  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x13f5fb  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal2
0x13f600  ldarg.0
0x13f601  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal2
0x13f606  ldstr    aUpdatewithfiel// "UpdateWithFieldValues"
0x13f60b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x13f610  ldarg.0
0x13f611  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal2
0x13f616  ldc.i4.0
0x13f617  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x13f61c  ldarg.0
0x13f61d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal2
0x13f622  ldc.i4.0
0x13f623  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x13f628  ldarg.0
0x13f629  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal2
0x13f62e  ldc.i4.s 0x10
0x13f630  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x13f635  ldarg.0
0x13f636  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal2
0x13f63b  ldstr    aUpdatewithfiel// "UpdateWithFieldValues"
0x13f640  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x13f645  ldarg.0
0x13f646  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal2
0x13f64b  ldc.i4.0
0x13f64c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x13f651  ldarg.0
0x13f652  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal2
0x13f657  ldtoken  [mscorlib]System.Void
0x13f65c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13f661  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x13f666  ldarg.0
0x13f667  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal2
0x13f66c  ldc.i4.0
0x13f66d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13f672  ldarg.0
0x13f673  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal2
0x13f678  ldc.i4.0
0x13f679  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x13f67e  ldarg.0
0x13f67f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal2
0x13f684  ldc.i4.0
0x13f685  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x13f68a  ldarg.0
0x13f68b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal2
0x13f690  ldc.i4.0
0x13f691  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x13f696  ldarg.0
0x13f697  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal2
0x13f69c  ldc.i4.0
0x13f69d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x13f6a2  ldarg.0
0x13f6a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>g__initLocal2
0x13f6a8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x13f6ad  ldarg.0
0x13f6ae  ldarg.0
0x13f6af  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<item>5__5
0x13f6b4  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__3::<>2__current
0x13f6b9  ldarg.0
0x13f6ba  ldc.i4.5
0x13f6bb  stfld    int32 <GetMethods>d__3::<>1__state
0x13f6c0  ldc.i4.1
0x13f6c1  stloc.0
0x13f6c2  leave.s  loc_13F6D6
0x13f6c4  ldarg.0
0x13f6c5  ldc.i4.m1
0x13f6c6  stfld    int32 <GetMethods>d__3::<>1__state
0x13f6cb  ldc.i4.0
0x13f6cc  stloc.0
0x13f6cd  leave.s  loc_13F6D6
0x13f6cf  ldarg.0
0x13f6d0  call     instance void <GetMethods>d__3::System.IDisposable.Dispose()
0x13f6d5  endfinally
0x13f6d6  ldloc.0
0x13f6d7  ret
```
