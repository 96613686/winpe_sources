# <GetMethods>d__e::MoveNext_1

- ea: `0x13b2a0`
- end: `0x13bcbf`
- name: `<GetMethods>d__e::MoveNext_1`
- size: `2591`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x604e0`
- `0x13b2a0`
- `0x13bce0`
- `0x13bd40`

## string_xrefs

- `0x13b4c3`: `Create`
- `0x13b4f8`: `Create_Client`
- `0x13b8c5`: `Remove`
- `0x13bba7`: `Remove`
- `0x13ba18`: `RemoveById`
- `0x13bb6f`: `RemoveByLoginName`
- `0x13b8f9`: `Remove_Client`
- `0x13ba50`: `RemoveByID`

## pseudocode

```c

```

## disassembly

```asm
0x13b2a0  ldarg.0
0x13b2a1  ldfld    int32 <GetMethods>d__e::<>1__state
0x13b2a6  stloc.1
0x13b2a7  ldloc.1
0x13b2a8  switch   loc_13B2DA, loc_13BCB2, loc_13B344, loc_13B4AA, loc_13B5FE, loc_13B755, loc_13B8AC, loc_13B9FF, loc_13BB56, loc_13BCAB
0x13b2d5  br       loc_13BCB2
0x13b2da  ldarg.0
0x13b2db  ldc.i4.m1
0x13b2dc  stfld    int32 <GetMethods>d__e::<>1__state
0x13b2e1  ldarg.0
0x13b2e2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__e::proxyContext
0x13b2e7  brtrue.s loc_13B2F4
0x13b2e9  ldstr    aProxycontext// "proxyContext"
0x13b2ee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13b2f3  throw
0x13b2f4  ldarg.0
0x13b2f5  ldarg.0
0x13b2f6  ldfld    class Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub <GetMethods>d__e::<>4__this
0x13b2fb  ldarg.0
0x13b2fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__e::proxyContext
0x13b301  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::<>n__FabricatedMethod13(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x13b306  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x13b30b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__e::<>7__wrap11
0x13b310  ldarg.0
0x13b311  ldc.i4.1
0x13b312  stfld    int32 <GetMethods>d__e::<>1__state
0x13b317  br.s     loc_13B34B
0x13b319  ldarg.0
0x13b31a  ldarg.0
0x13b31b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__e::<>7__wrap11
0x13b320  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x13b325  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<itemBase>5__f
0x13b32a  ldarg.0
0x13b32b  ldarg.0
0x13b32c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<itemBase>5__f
0x13b331  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>2__current
0x13b336  ldarg.0
0x13b337  ldc.i4.2
0x13b338  stfld    int32 <GetMethods>d__e::<>1__state
0x13b33d  ldc.i4.1
0x13b33e  stloc.0
0x13b33f  leave    loc_13BCBD
0x13b344  ldarg.0
0x13b345  ldc.i4.1
0x13b346  stfld    int32 <GetMethods>d__e::<>1__state
0x13b34b  ldarg.0
0x13b34c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__e::<>7__wrap11
0x13b351  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13b356  brtrue.s loc_13B319
0x13b358  ldarg.0
0x13b359  call     instance void <GetMethods>d__e::<>m__Finally12()
0x13b35e  ldarg.0
0x13b35f  ldarg.0
0x13b360  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x13b365  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x13b36a  ldarg.0
0x13b36b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x13b370  ldstr    aAdd// "Add"
0x13b375  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x13b37a  ldarg.0
0x13b37b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x13b380  ldc.i4.0
0x13b381  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x13b386  ldarg.0
0x13b387  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x13b38c  ldc.i4.0
0x13b38d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x13b392  ldarg.0
0x13b393  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x13b398  ldc.i4.7
0x13b399  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x13b39e  ldarg.0
0x13b39f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x13b3a4  ldstr    aAddClient// "Add_Client"
0x13b3a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x13b3ae  ldarg.0
0x13b3af  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x13b3b4  ldc.i4.0
0x13b3b5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x13b3ba  ldarg.0
0x13b3bb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x13b3c0  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPGroup
0x13b3c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13b3ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x13b3cf  ldarg.0
0x13b3d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x13b3d5  ldc.i4.4
0x13b3d6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13b3db  ldarg.0
0x13b3dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x13b3e1  ldc.i4.0
0x13b3e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x13b3e7  ldarg.0
0x13b3e8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x13b3ed  ldc.i4.0
0x13b3ee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x13b3f3  ldarg.0
0x13b3f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x13b3f9  ldc.i4.0
0x13b3fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x13b3ff  ldarg.0
0x13b400  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x13b405  ldc.i4.0
0x13b406  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x13b40b  ldarg.0
0x13b40c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal0
0x13b411  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<item>5__10
0x13b416  ldarg.0
0x13b417  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<item>5__10
0x13b41c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x13b421  ldarg.0
0x13b422  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x13b427  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal1
0x13b42c  ldarg.0
0x13b42d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal1
0x13b432  ldstr    aParameters// "parameters"
0x13b437  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x13b43c  ldarg.0
0x13b43d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal1
0x13b442  ldc.i4.0
0x13b443  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x13b448  ldarg.0
0x13b449  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal1
0x13b44e  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupCreationInformation
0x13b453  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13b458  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x13b45d  ldarg.0
0x13b45e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal1
0x13b463  ldc.i4.2
0x13b464  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13b469  ldarg.0
0x13b46a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal1
0x13b46f  ldc.i4.0
0x13b470  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x13b475  ldarg.0
0x13b476  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal1
0x13b47b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x13b480  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x13b485  ldarg.0
0x13b486  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal1
0x13b48b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x13b490  ldarg.0
0x13b491  ldarg.0
0x13b492  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<item>5__10
0x13b497  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>2__current
0x13b49c  ldarg.0
0x13b49d  ldc.i4.3
0x13b49e  stfld    int32 <GetMethods>d__e::<>1__state
0x13b4a3  ldc.i4.1
0x13b4a4  stloc.0
0x13b4a5  leave    loc_13BCBD
0x13b4aa  ldarg.0
0x13b4ab  ldc.i4.m1
0x13b4ac  stfld    int32 <GetMethods>d__e::<>1__state
0x13b4b1  ldarg.0
0x13b4b2  ldarg.0
0x13b4b3  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x13b4b8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13b4bd  ldarg.0
0x13b4be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13b4c3  ldstr    aCreate// "Create"
0x13b4c8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x13b4cd  ldarg.0
0x13b4ce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13b4d3  ldc.i4.0
0x13b4d4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x13b4d9  ldarg.0
0x13b4da  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13b4df  ldc.i4.0
0x13b4e0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x13b4e5  ldarg.0
0x13b4e6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13b4eb  ldc.i4.s 0x10
0x13b4ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x13b4f2  ldarg.0
0x13b4f3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13b4f8  ldstr    aCreateClient// "Create_Client"
0x13b4fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x13b502  ldarg.0
0x13b503  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13b508  ldc.i4.0
0x13b509  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x13b50e  ldarg.0
0x13b50f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13b514  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPGroup
0x13b519  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13b51e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x13b523  ldarg.0
0x13b524  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13b529  ldc.i4.4
0x13b52a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13b52f  ldarg.0
0x13b530  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13b535  ldc.i4.0
0x13b536  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x13b53b  ldarg.0
0x13b53c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13b541  ldc.i4.0
0x13b542  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x13b547  ldarg.0
0x13b548  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13b54d  ldc.i4.0
0x13b54e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x13b553  ldarg.0
0x13b554  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13b559  ldc.i4.0
0x13b55a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x13b55f  ldarg.0
0x13b560  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal2
0x13b565  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<item>5__10
0x13b56a  ldarg.0
0x13b56b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<item>5__10
0x13b570  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x13b575  ldarg.0
0x13b576  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x13b57b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal3
0x13b580  ldarg.0
0x13b581  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal3
0x13b586  ldstr    aParameters// "parameters"
0x13b58b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x13b590  ldarg.0
0x13b591  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal3
0x13b596  ldc.i4.0
0x13b597  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x13b59c  ldarg.0
0x13b59d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal3
0x13b5a2  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupEntityData
0x13b5a7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13b5ac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x13b5b1  ldarg.0
0x13b5b2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal3
0x13b5b7  ldc.i4.2
0x13b5b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13b5bd  ldarg.0
0x13b5be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal3
0x13b5c3  ldc.i4.0
0x13b5c4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x13b5c9  ldarg.0
0x13b5ca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal3
0x13b5cf  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x13b5d4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x13b5d9  ldarg.0
0x13b5da  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__e::<>g__initLocal3
0x13b5df  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x13b5e4  ldarg.0
0x13b5e5  ldarg.0
0x13b5e6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<item>5__10
0x13b5eb  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>2__current
0x13b5f0  ldarg.0
0x13b5f1  ldc.i4.4
0x13b5f2  stfld    int32 <GetMethods>d__e::<>1__state
0x13b5f7  ldc.i4.1
0x13b5f8  stloc.0
0x13b5f9  leave    loc_13BCBD
0x13b5fe  ldarg.0
0x13b5ff  ldc.i4.m1
0x13b600  stfld    int32 <GetMethods>d__e::<>1__state
0x13b605  ldarg.0
0x13b606  ldarg.0
0x13b607  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x13b60c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal4
0x13b611  ldarg.0
0x13b612  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal4
0x13b617  ldstr    aGetbyid// "GetById"
0x13b61c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x13b621  ldarg.0
0x13b622  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal4
0x13b627  ldc.i4.0
0x13b628  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x13b62d  ldarg.0
0x13b62e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal4
0x13b633  ldc.i4.1
0x13b634  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x13b639  ldarg.0
0x13b63a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal4
0x13b63f  ldc.i4   0xFFFFFFF
0x13b644  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x13b649  ldarg.0
0x13b64a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal4
0x13b64f  ldstr    aGetbyid_0// "GetByID"
0x13b654  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x13b659  ldarg.0
0x13b65a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal4
0x13b65f  ldc.i4.0
0x13b660  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x13b665  ldarg.0
0x13b666  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal4
0x13b66b  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPGroup
0x13b670  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13b675  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x13b67a  ldarg.0
0x13b67b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal4
0x13b680  ldc.i4.4
0x13b681  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13b686  ldarg.0
0x13b687  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal4
0x13b68c  ldc.i4.0
0x13b68d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x13b692  ldarg.0
0x13b693  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__e::<>g__initLocal4
  ... truncated ...
```
