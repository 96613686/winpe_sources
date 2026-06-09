# <GetMethods>d__13::MoveNext

- ea: `0x1ac1f0`
- end: `0x1ace15`
- name: `<GetMethods>d__13::MoveNext`
- size: `3109`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callees

- `0xb0c00`
- `0x1ac1f0`
- `0x1ace40`
- `0x1acea0`

## string_xrefs

- `0x1acd8b`: `propagateAcl`
- `0x1ac96f`: `UpdateDocumentSharingInfo`
- `0x1ac9a7`: `UpdateDocumentSharingInfo`
- `0x1ac6c1`: `RemoveItemsFromSharedWithMeView`
- `0x1ac6f9`: `RemoveItemsFromSharedWithMeView`
- `0x1ac818`: `RemoveItemsFromSharedWithMeViewByPath`
- `0x1ac850`: `RemoveItemsFromSharedWithMeViewByPath`
- `0x1ac8de`: `itemPaths`
- `0x1acd11`: `includeAnonymousLinksInNotification`

## pseudocode

```c

```

## disassembly

```asm
0x1ac1f0  ldarg.0
0x1ac1f1  ldfld    int32 <GetMethods>d__13::<>1__state
0x1ac1f6  stloc.1
0x1ac1f7  ldloc.1
0x1ac1f8  switch   loc_1AC226, loc_1ACE08, loc_1AC290, loc_1AC3FA, loc_1AC551, loc_1AC6A8, loc_1AC7FF, loc_1AC956, loc_1ACE01
0x1ac221  br       loc_1ACE08
0x1ac226  ldarg.0
0x1ac227  ldc.i4.m1
0x1ac228  stfld    int32 <GetMethods>d__13::<>1__state
0x1ac22d  ldarg.0
0x1ac22e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__13::proxyContext
0x1ac233  brtrue.s loc_1AC240
0x1ac235  ldstr    aProxycontext// "proxyContext"
0x1ac23a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1ac23f  throw
0x1ac240  ldarg.0
0x1ac241  ldarg.0
0x1ac242  ldfld    class Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub <GetMethods>d__13::<>4__this
0x1ac247  ldarg.0
0x1ac248  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__13::proxyContext
0x1ac24d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub::<>n__FabricatedMethod18(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext xmlargs)
0x1ac252  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x1ac257  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__13::<>7__wrap16
0x1ac25c  ldarg.0
0x1ac25d  ldc.i4.1
0x1ac25e  stfld    int32 <GetMethods>d__13::<>1__state
0x1ac263  br.s     loc_1AC297
0x1ac265  ldarg.0
0x1ac266  ldarg.0
0x1ac267  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__13::<>7__wrap16
0x1ac26c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x1ac271  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<itemBase>5__14
0x1ac276  ldarg.0
0x1ac277  ldarg.0
0x1ac278  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<itemBase>5__14
0x1ac27d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>2__current
0x1ac282  ldarg.0
0x1ac283  ldc.i4.2
0x1ac284  stfld    int32 <GetMethods>d__13::<>1__state
0x1ac289  ldc.i4.1
0x1ac28a  stloc.0
0x1ac28b  leave    loc_1ACE13
0x1ac290  ldarg.0
0x1ac291  ldc.i4.1
0x1ac292  stfld    int32 <GetMethods>d__13::<>1__state
0x1ac297  ldarg.0
0x1ac298  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__13::<>7__wrap16
0x1ac29d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1ac2a2  brtrue.s loc_1AC265
0x1ac2a4  ldarg.0
0x1ac2a5  call     instance void <GetMethods>d__13::<>m__Finally17()
0x1ac2aa  ldarg.0
0x1ac2ab  ldarg.0
0x1ac2ac  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1ac2b1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal0
0x1ac2b6  ldarg.0
0x1ac2b7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal0
0x1ac2bc  ldstr    aCanmembershare// "CanMemberShare"
0x1ac2c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1ac2c6  ldarg.0
0x1ac2c7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal0
0x1ac2cc  ldc.i4.1
0x1ac2cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1ac2d2  ldarg.0
0x1ac2d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal0
0x1ac2d8  ldc.i4.0
0x1ac2d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1ac2de  ldarg.0
0x1ac2df  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal0
0x1ac2e4  ldc.i4   0xFFFFFFF
0x1ac2e9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1ac2ee  ldarg.0
0x1ac2ef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal0
0x1ac2f4  ldstr    aCanmembershare// "CanMemberShare"
0x1ac2f9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1ac2fe  ldarg.0
0x1ac2ff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal0
0x1ac304  ldc.i4.0
0x1ac305  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1ac30a  ldarg.0
0x1ac30b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal0
0x1ac310  ldtoken  [mscorlib]System.Boolean
0x1ac315  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ac31a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1ac31f  ldarg.0
0x1ac320  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal0
0x1ac325  ldc.i4.1
0x1ac326  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ac32b  ldarg.0
0x1ac32c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal0
0x1ac331  ldc.i4.0
0x1ac332  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1ac337  ldarg.0
0x1ac338  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal0
0x1ac33d  ldc.i4.0
0x1ac33e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1ac343  ldarg.0
0x1ac344  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal0
0x1ac349  ldc.i4.0
0x1ac34a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1ac34f  ldarg.0
0x1ac350  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal0
0x1ac355  ldc.i4.0
0x1ac356  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1ac35b  ldarg.0
0x1ac35c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal0
0x1ac361  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<item>5__15
0x1ac366  ldarg.0
0x1ac367  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<item>5__15
0x1ac36c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1ac371  ldarg.0
0x1ac372  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1ac377  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__13::<>g__initLocal1
0x1ac37c  ldarg.0
0x1ac37d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__13::<>g__initLocal1
0x1ac382  ldstr    aList_0// "list"
0x1ac387  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1ac38c  ldarg.0
0x1ac38d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__13::<>g__initLocal1
0x1ac392  ldc.i4.0
0x1ac393  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1ac398  ldarg.0
0x1ac399  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__13::<>g__initLocal1
0x1ac39e  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPList
0x1ac3a3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ac3a8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1ac3ad  ldarg.0
0x1ac3ae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__13::<>g__initLocal1
0x1ac3b3  ldc.i4.0
0x1ac3b4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ac3b9  ldarg.0
0x1ac3ba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__13::<>g__initLocal1
0x1ac3bf  ldc.i4.0
0x1ac3c0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1ac3c5  ldarg.0
0x1ac3c6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__13::<>g__initLocal1
0x1ac3cb  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1ac3d0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1ac3d5  ldarg.0
0x1ac3d6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__13::<>g__initLocal1
0x1ac3db  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1ac3e0  ldarg.0
0x1ac3e1  ldarg.0
0x1ac3e2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<item>5__15
0x1ac3e7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>2__current
0x1ac3ec  ldarg.0
0x1ac3ed  ldc.i4.3
0x1ac3ee  stfld    int32 <GetMethods>d__13::<>1__state
0x1ac3f3  ldc.i4.1
0x1ac3f4  stloc.0
0x1ac3f5  leave    loc_1ACE13
0x1ac3fa  ldarg.0
0x1ac3fb  ldc.i4.m1
0x1ac3fc  stfld    int32 <GetMethods>d__13::<>1__state
0x1ac401  ldarg.0
0x1ac402  ldarg.0
0x1ac403  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1ac408  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal2
0x1ac40d  ldarg.0
0x1ac40e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal2
0x1ac413  ldstr    aGetroledefinit// "GetRoleDefinition"
0x1ac418  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1ac41d  ldarg.0
0x1ac41e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal2
0x1ac423  ldc.i4.1
0x1ac424  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1ac429  ldarg.0
0x1ac42a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal2
0x1ac42f  ldc.i4.0
0x1ac430  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1ac435  ldarg.0
0x1ac436  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal2
0x1ac43b  ldc.i4   0xFFFFFFF
0x1ac440  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1ac445  ldarg.0
0x1ac446  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal2
0x1ac44b  ldstr    aGetroledefinit_0// "GetRoleDefinition_Client"
0x1ac450  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1ac455  ldarg.0
0x1ac456  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal2
0x1ac45b  ldc.i4.0
0x1ac45c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1ac461  ldarg.0
0x1ac462  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal2
0x1ac467  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinition
0x1ac46c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ac471  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1ac476  ldarg.0
0x1ac477  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal2
0x1ac47c  ldc.i4.4
0x1ac47d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ac482  ldarg.0
0x1ac483  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal2
0x1ac488  ldc.i4.0
0x1ac489  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1ac48e  ldarg.0
0x1ac48f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal2
0x1ac494  ldc.i4.0
0x1ac495  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1ac49a  ldarg.0
0x1ac49b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal2
0x1ac4a0  ldc.i4.0
0x1ac4a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1ac4a6  ldarg.0
0x1ac4a7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal2
0x1ac4ac  ldc.i4.0
0x1ac4ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1ac4b2  ldarg.0
0x1ac4b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal2
0x1ac4b8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<item>5__15
0x1ac4bd  ldarg.0
0x1ac4be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<item>5__15
0x1ac4c3  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1ac4c8  ldarg.0
0x1ac4c9  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1ac4ce  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__13::<>g__initLocal3
0x1ac4d3  ldarg.0
0x1ac4d4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__13::<>g__initLocal3
0x1ac4d9  ldstr    aRole// "role"
0x1ac4de  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1ac4e3  ldarg.0
0x1ac4e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__13::<>g__initLocal3
0x1ac4e9  ldc.i4.0
0x1ac4ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1ac4ef  ldarg.0
0x1ac4f0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__13::<>g__initLocal3
0x1ac4f5  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Role
0x1ac4fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ac4ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1ac504  ldarg.0
0x1ac505  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__13::<>g__initLocal3
0x1ac50a  ldc.i4.1
0x1ac50b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ac510  ldarg.0
0x1ac511  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__13::<>g__initLocal3
0x1ac516  ldc.i4.0
0x1ac517  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1ac51c  ldarg.0
0x1ac51d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__13::<>g__initLocal3
0x1ac522  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1ac527  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1ac52c  ldarg.0
0x1ac52d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__13::<>g__initLocal3
0x1ac532  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1ac537  ldarg.0
0x1ac538  ldarg.0
0x1ac539  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<item>5__15
0x1ac53e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>2__current
0x1ac543  ldarg.0
0x1ac544  ldc.i4.4
0x1ac545  stfld    int32 <GetMethods>d__13::<>1__state
0x1ac54a  ldc.i4.1
0x1ac54b  stloc.0
0x1ac54c  leave    loc_1ACE13
0x1ac551  ldarg.0
0x1ac552  ldc.i4.m1
0x1ac553  stfld    int32 <GetMethods>d__13::<>1__state
0x1ac558  ldarg.0
0x1ac559  ldarg.0
0x1ac55a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1ac55f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal4
0x1ac564  ldarg.0
0x1ac565  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal4
0x1ac56a  ldstr    aIsdocumentshar// "IsDocumentSharingEnabled"
0x1ac56f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1ac574  ldarg.0
0x1ac575  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal4
0x1ac57a  ldc.i4.1
0x1ac57b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1ac580  ldarg.0
0x1ac581  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal4
0x1ac586  ldc.i4.0
0x1ac587  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1ac58c  ldarg.0
0x1ac58d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal4
0x1ac592  ldc.i4   0xFFFFFFF
0x1ac597  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1ac59c  ldarg.0
0x1ac59d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal4
0x1ac5a2  ldstr    aIsdocumentshar// "IsDocumentSharingEnabled"
0x1ac5a7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1ac5ac  ldarg.0
0x1ac5ad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal4
0x1ac5b2  ldc.i4.0
0x1ac5b3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1ac5b8  ldarg.0
0x1ac5b9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal4
0x1ac5be  ldtoken  [mscorlib]System.Boolean
0x1ac5c3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ac5c8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1ac5cd  ldarg.0
0x1ac5ce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal4
0x1ac5d3  ldc.i4.1
0x1ac5d4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ac5d9  ldarg.0
0x1ac5da  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal4
0x1ac5df  ldc.i4.0
0x1ac5e0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1ac5e5  ldarg.0
0x1ac5e6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__13::<>g__initLocal4
  ... truncated ...
```
