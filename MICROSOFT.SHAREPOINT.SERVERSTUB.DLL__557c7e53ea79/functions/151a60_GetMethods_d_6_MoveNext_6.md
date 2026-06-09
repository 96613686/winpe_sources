# <GetMethods>d__6::MoveNext_6

- ea: `0x151a60`
- end: `0x151feb`
- name: `<GetMethods>d__6::MoveNext_6`
- size: `1419`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x71bf0`
- `0x151a60`
- `0x152010`
- `0x152070`

## string_xrefs

- `0x151b28`: `DeleteAll`
- `0x151b60`: `DeleteAll`
- `0x151e39`: `MoveAllToSecondStage`
- `0x151c05`: `DeleteAllSecondStageItems`
- `0x151c3d`: `DeleteAllSecondStageItems`
- `0x151e71`: `MoveAllToSecondStage_Client`

## pseudocode

```c

```

## disassembly

```asm
0x151a60  ldarg.0
0x151a61  ldfld    int32 <GetMethods>d__6::<>1__state
0x151a66  stloc.1
0x151a67  ldloc.1
0x151a68  switch   loc_151A92, loc_151FDE, loc_151AFC, loc_151BEC, loc_151CC9, loc_151E20, loc_151EFD, loc_151FD7
0x151a8d  br       loc_151FDE
0x151a92  ldarg.0
0x151a93  ldc.i4.m1
0x151a94  stfld    int32 <GetMethods>d__6::<>1__state
0x151a99  ldarg.0
0x151a9a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__6::proxyContext
0x151a9f  brtrue.s loc_151AAC
0x151aa1  ldstr    aProxycontext// "proxyContext"
0x151aa6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x151aab  throw
0x151aac  ldarg.0
0x151aad  ldarg.0
0x151aae  ldfld    class Microsoft.SharePoint.ServerStub.SPRecycleBinItemCollectionServerStub <GetMethods>d__6::<>4__this
0x151ab3  ldarg.0
0x151ab4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__6::proxyContext
0x151ab9  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPRecycleBinItemCollectionServerStub::<>n__FabricatedMethodb(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x151abe  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x151ac3  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__6::<>7__wrap9
0x151ac8  ldarg.0
0x151ac9  ldc.i4.1
0x151aca  stfld    int32 <GetMethods>d__6::<>1__state
0x151acf  br.s     loc_151B03
0x151ad1  ldarg.0
0x151ad2  ldarg.0
0x151ad3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__6::<>7__wrap9
0x151ad8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x151add  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<itemBase>5__7
0x151ae2  ldarg.0
0x151ae3  ldarg.0
0x151ae4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<itemBase>5__7
0x151ae9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>2__current
0x151aee  ldarg.0
0x151aef  ldc.i4.2
0x151af0  stfld    int32 <GetMethods>d__6::<>1__state
0x151af5  ldc.i4.1
0x151af6  stloc.0
0x151af7  leave    loc_151FE9
0x151afc  ldarg.0
0x151afd  ldc.i4.1
0x151afe  stfld    int32 <GetMethods>d__6::<>1__state
0x151b03  ldarg.0
0x151b04  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__6::<>7__wrap9
0x151b09  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x151b0e  brtrue.s loc_151AD1
0x151b10  ldarg.0
0x151b11  call     instance void <GetMethods>d__6::<>m__Finallya()
0x151b16  ldarg.0
0x151b17  ldarg.0
0x151b18  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x151b1d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal0
0x151b22  ldarg.0
0x151b23  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal0
0x151b28  ldstr    aDeleteall// "DeleteAll"
0x151b2d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x151b32  ldarg.0
0x151b33  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal0
0x151b38  ldc.i4.0
0x151b39  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x151b3e  ldarg.0
0x151b3f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal0
0x151b44  ldc.i4.0
0x151b45  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x151b4a  ldarg.0
0x151b4b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal0
0x151b50  ldc.i4   0xFFFFFFF
0x151b55  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x151b5a  ldarg.0
0x151b5b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal0
0x151b60  ldstr    aDeleteall// "DeleteAll"
0x151b65  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x151b6a  ldarg.0
0x151b6b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal0
0x151b70  ldc.i4.0
0x151b71  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x151b76  ldarg.0
0x151b77  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal0
0x151b7c  ldtoken  [mscorlib]System.Void
0x151b81  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x151b86  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x151b8b  ldarg.0
0x151b8c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal0
0x151b91  ldc.i4.0
0x151b92  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x151b97  ldarg.0
0x151b98  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal0
0x151b9d  ldc.i4.0
0x151b9e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x151ba3  ldarg.0
0x151ba4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal0
0x151ba9  ldc.i4.0
0x151baa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x151baf  ldarg.0
0x151bb0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal0
0x151bb5  ldc.i4.0
0x151bb6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x151bbb  ldarg.0
0x151bbc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal0
0x151bc1  ldc.i4.0
0x151bc2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x151bc7  ldarg.0
0x151bc8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal0
0x151bcd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<item>5__8
0x151bd2  ldarg.0
0x151bd3  ldarg.0
0x151bd4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<item>5__8
0x151bd9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>2__current
0x151bde  ldarg.0
0x151bdf  ldc.i4.3
0x151be0  stfld    int32 <GetMethods>d__6::<>1__state
0x151be5  ldc.i4.1
0x151be6  stloc.0
0x151be7  leave    loc_151FE9
0x151bec  ldarg.0
0x151bed  ldc.i4.m1
0x151bee  stfld    int32 <GetMethods>d__6::<>1__state
0x151bf3  ldarg.0
0x151bf4  ldarg.0
0x151bf5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x151bfa  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal1
0x151bff  ldarg.0
0x151c00  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal1
0x151c05  ldstr    aDeleteallsecon// "DeleteAllSecondStageItems"
0x151c0a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x151c0f  ldarg.0
0x151c10  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal1
0x151c15  ldc.i4.0
0x151c16  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x151c1b  ldarg.0
0x151c1c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal1
0x151c21  ldc.i4.0
0x151c22  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x151c27  ldarg.0
0x151c28  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal1
0x151c2d  ldc.i4   0xFFFFFFF
0x151c32  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x151c37  ldarg.0
0x151c38  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal1
0x151c3d  ldstr    aDeleteallsecon// "DeleteAllSecondStageItems"
0x151c42  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x151c47  ldarg.0
0x151c48  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal1
0x151c4d  ldc.i4.0
0x151c4e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x151c53  ldarg.0
0x151c54  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal1
0x151c59  ldtoken  [mscorlib]System.Void
0x151c5e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x151c63  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x151c68  ldarg.0
0x151c69  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal1
0x151c6e  ldc.i4.0
0x151c6f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x151c74  ldarg.0
0x151c75  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal1
0x151c7a  ldc.i4.0
0x151c7b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x151c80  ldarg.0
0x151c81  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal1
0x151c86  ldc.i4.0
0x151c87  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x151c8c  ldarg.0
0x151c8d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal1
0x151c92  ldc.i4.0
0x151c93  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x151c98  ldarg.0
0x151c99  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal1
0x151c9e  ldc.i4.0
0x151c9f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x151ca4  ldarg.0
0x151ca5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal1
0x151caa  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<item>5__8
0x151caf  ldarg.0
0x151cb0  ldarg.0
0x151cb1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<item>5__8
0x151cb6  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>2__current
0x151cbb  ldarg.0
0x151cbc  ldc.i4.4
0x151cbd  stfld    int32 <GetMethods>d__6::<>1__state
0x151cc2  ldc.i4.1
0x151cc3  stloc.0
0x151cc4  leave    loc_151FE9
0x151cc9  ldarg.0
0x151cca  ldc.i4.m1
0x151ccb  stfld    int32 <GetMethods>d__6::<>1__state
0x151cd0  ldarg.0
0x151cd1  ldarg.0
0x151cd2  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x151cd7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal2
0x151cdc  ldarg.0
0x151cdd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal2
0x151ce2  ldstr    aGetbyid// "GetById"
0x151ce7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x151cec  ldarg.0
0x151ced  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal2
0x151cf2  ldc.i4.0
0x151cf3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x151cf8  ldarg.0
0x151cf9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal2
0x151cfe  ldc.i4.1
0x151cff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x151d04  ldarg.0
0x151d05  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal2
0x151d0a  ldc.i4   0xFFFFFFF
0x151d0f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x151d14  ldarg.0
0x151d15  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal2
0x151d1a  ldstr    aGetitembyid// "GetItemById"
0x151d1f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x151d24  ldarg.0
0x151d25  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal2
0x151d2a  ldc.i4.0
0x151d2b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x151d30  ldarg.0
0x151d31  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal2
0x151d36  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem
0x151d3b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x151d40  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x151d45  ldarg.0
0x151d46  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal2
0x151d4b  ldc.i4.4
0x151d4c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x151d51  ldarg.0
0x151d52  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal2
0x151d57  ldc.i4.0
0x151d58  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x151d5d  ldarg.0
0x151d5e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal2
0x151d63  ldc.i4.0
0x151d64  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x151d69  ldarg.0
0x151d6a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal2
0x151d6f  ldc.i4.0
0x151d70  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x151d75  ldarg.0
0x151d76  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal2
0x151d7b  ldc.i4.0
0x151d7c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x151d81  ldarg.0
0x151d82  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal2
0x151d87  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<item>5__8
0x151d8c  ldarg.0
0x151d8d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<item>5__8
0x151d92  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x151d97  ldarg.0
0x151d98  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x151d9d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__6::<>g__initLocal3
0x151da2  ldarg.0
0x151da3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__6::<>g__initLocal3
0x151da8  ldstr    aId// "id"
0x151dad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x151db2  ldarg.0
0x151db3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__6::<>g__initLocal3
0x151db8  ldc.i4.0
0x151db9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x151dbe  ldarg.0
0x151dbf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__6::<>g__initLocal3
0x151dc4  ldtoken  [mscorlib]System.Guid
0x151dc9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x151dce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x151dd3  ldarg.0
0x151dd4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__6::<>g__initLocal3
0x151dd9  ldc.i4.1
0x151dda  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x151ddf  ldarg.0
0x151de0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__6::<>g__initLocal3
0x151de5  ldc.i4.0
0x151de6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x151deb  ldarg.0
0x151dec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__6::<>g__initLocal3
0x151df1  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x151df6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x151dfb  ldarg.0
0x151dfc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__6::<>g__initLocal3
0x151e01  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x151e06  ldarg.0
0x151e07  ldarg.0
0x151e08  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<item>5__8
0x151e0d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>2__current
0x151e12  ldarg.0
0x151e13  ldc.i4.5
0x151e14  stfld    int32 <GetMethods>d__6::<>1__state
0x151e19  ldc.i4.1
0x151e1a  stloc.0
0x151e1b  leave    loc_151FE9
0x151e20  ldarg.0
0x151e21  ldc.i4.m1
0x151e22  stfld    int32 <GetMethods>d__6::<>1__state
0x151e27  ldarg.0
0x151e28  ldarg.0
0x151e29  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x151e2e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal4
0x151e33  ldarg.0
0x151e34  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__6::<>g__initLocal4
0x151e39  ldstr    aMovealltosecon// "MoveAllToSecondStage"
0x151e3e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
  ... truncated ...
```
