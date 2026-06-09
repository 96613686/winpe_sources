# <GetMethods>d__4::MoveNext_4

- ea: `0x116e90`
- end: `0x117256`
- name: `<GetMethods>d__4::MoveNext_4`
- size: `966`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callees

- `0x44950`
- `0x116e90`
- `0x117280`
- `0x1172e0`

## string_xrefs

- `0x117062`: `Update`
- `0x117107`: `Update`
- `0x11713f`: `Update`
- `0x116f50`: `DeleteObject`
- `0x116f88`: `Delete`
- `0x11702d`: `RestUpdate`
- `0x1171cd`: `updateChildren`

## pseudocode

```c

```

## disassembly

```asm
0x116e90  ldarg.0
0x116e91  ldfld    int32 <GetMethods>d__4::<>1__state
0x116e96  stloc.1
0x116e97  ldloc.1
0x116e98  switch   loc_116EBA, loc_117249, loc_116F24, loc_117014, loc_1170EE, loc_117242
0x116eb5  br       loc_117249
0x116eba  ldarg.0
0x116ebb  ldc.i4.m1
0x116ebc  stfld    int32 <GetMethods>d__4::<>1__state
0x116ec1  ldarg.0
0x116ec2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__4::proxyContext
0x116ec7  brtrue.s loc_116ED4
0x116ec9  ldstr    aProxycontext// "proxyContext"
0x116ece  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x116ed3  throw
0x116ed4  ldarg.0
0x116ed5  ldarg.0
0x116ed6  ldfld    class Microsoft.SharePoint.ServerStub.SPContentTypeServerStub <GetMethods>d__4::<>4__this
0x116edb  ldarg.0
0x116edc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__4::proxyContext
0x116ee1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::<>n__FabricatedMethod9(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x116ee6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x116eeb  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__4::<>7__wrap7
0x116ef0  ldarg.0
0x116ef1  ldc.i4.1
0x116ef2  stfld    int32 <GetMethods>d__4::<>1__state
0x116ef7  br.s     loc_116F2B
0x116ef9  ldarg.0
0x116efa  ldarg.0
0x116efb  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__4::<>7__wrap7
0x116f00  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x116f05  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<itemBase>5__5
0x116f0a  ldarg.0
0x116f0b  ldarg.0
0x116f0c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<itemBase>5__5
0x116f11  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>2__current
0x116f16  ldarg.0
0x116f17  ldc.i4.2
0x116f18  stfld    int32 <GetMethods>d__4::<>1__state
0x116f1d  ldc.i4.1
0x116f1e  stloc.0
0x116f1f  leave    loc_117254
0x116f24  ldarg.0
0x116f25  ldc.i4.1
0x116f26  stfld    int32 <GetMethods>d__4::<>1__state
0x116f2b  ldarg.0
0x116f2c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__4::<>7__wrap7
0x116f31  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x116f36  brtrue.s loc_116EF9
0x116f38  ldarg.0
0x116f39  call     instance void <GetMethods>d__4::<>m__Finally8()
0x116f3e  ldarg.0
0x116f3f  ldarg.0
0x116f40  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x116f45  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x116f4a  ldarg.0
0x116f4b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x116f50  ldstr    aDeleteobject// "DeleteObject"
0x116f55  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x116f5a  ldarg.0
0x116f5b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x116f60  ldc.i4.0
0x116f61  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x116f66  ldarg.0
0x116f67  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x116f6c  ldc.i4.0
0x116f6d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x116f72  ldarg.0
0x116f73  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x116f78  ldc.i4   0xFFFFFFF
0x116f7d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x116f82  ldarg.0
0x116f83  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x116f88  ldstr    aDelete// "Delete"
0x116f8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x116f92  ldarg.0
0x116f93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x116f98  ldc.i4.0
0x116f99  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x116f9e  ldarg.0
0x116f9f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x116fa4  ldtoken  [mscorlib]System.Void
0x116fa9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x116fae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x116fb3  ldarg.0
0x116fb4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x116fb9  ldc.i4.0
0x116fba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x116fbf  ldarg.0
0x116fc0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x116fc5  ldc.i4.0
0x116fc6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x116fcb  ldarg.0
0x116fcc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x116fd1  ldc.i4.0
0x116fd2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x116fd7  ldarg.0
0x116fd8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x116fdd  ldc.i4.0
0x116fde  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x116fe3  ldarg.0
0x116fe4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x116fe9  ldc.i4.0
0x116fea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x116fef  ldarg.0
0x116ff0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal0
0x116ff5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x116ffa  ldarg.0
0x116ffb  ldarg.0
0x116ffc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x117001  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>2__current
0x117006  ldarg.0
0x117007  ldc.i4.3
0x117008  stfld    int32 <GetMethods>d__4::<>1__state
0x11700d  ldc.i4.1
0x11700e  stloc.0
0x11700f  leave    loc_117254
0x117014  ldarg.0
0x117015  ldc.i4.m1
0x117016  stfld    int32 <GetMethods>d__4::<>1__state
0x11701b  ldarg.0
0x11701c  ldarg.0
0x11701d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x117022  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x117027  ldarg.0
0x117028  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x11702d  ldstr    aRestupdate// "RestUpdate"
0x117032  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x117037  ldarg.0
0x117038  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x11703d  ldc.i4.0
0x11703e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x117043  ldarg.0
0x117044  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x117049  ldc.i4.0
0x11704a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x11704f  ldarg.0
0x117050  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x117055  ldc.i4.s 0x10
0x117057  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x11705c  ldarg.0
0x11705d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x117062  ldstr    aUpdate// "Update"
0x117067  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x11706c  ldarg.0
0x11706d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x117072  ldc.i4.0
0x117073  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x117078  ldarg.0
0x117079  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x11707e  ldtoken  [mscorlib]System.Void
0x117083  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x117088  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x11708d  ldarg.0
0x11708e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x117093  ldc.i4.0
0x117094  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x117099  ldarg.0
0x11709a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x11709f  ldc.i4.0
0x1170a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1170a5  ldarg.0
0x1170a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x1170ab  ldc.i4.1
0x1170ac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1170b1  ldarg.0
0x1170b2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x1170b7  ldc.i4.0
0x1170b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1170bd  ldarg.0
0x1170be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x1170c3  ldc.i4.0
0x1170c4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1170c9  ldarg.0
0x1170ca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal1
0x1170cf  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x1170d4  ldarg.0
0x1170d5  ldarg.0
0x1170d6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x1170db  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>2__current
0x1170e0  ldarg.0
0x1170e1  ldc.i4.4
0x1170e2  stfld    int32 <GetMethods>d__4::<>1__state
0x1170e7  ldc.i4.1
0x1170e8  stloc.0
0x1170e9  leave    loc_117254
0x1170ee  ldarg.0
0x1170ef  ldc.i4.m1
0x1170f0  stfld    int32 <GetMethods>d__4::<>1__state
0x1170f5  ldarg.0
0x1170f6  ldarg.0
0x1170f7  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1170fc  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x117101  ldarg.0
0x117102  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x117107  ldstr    aUpdate// "Update"
0x11710c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x117111  ldarg.0
0x117112  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x117117  ldc.i4.0
0x117118  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x11711d  ldarg.0
0x11711e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x117123  ldc.i4.0
0x117124  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x117129  ldarg.0
0x11712a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x11712f  ldc.i4   0xFFFFFFF
0x117134  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x117139  ldarg.0
0x11713a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x11713f  ldstr    aUpdate// "Update"
0x117144  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x117149  ldarg.0
0x11714a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x11714f  ldc.i4.0
0x117150  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x117155  ldarg.0
0x117156  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x11715b  ldtoken  [mscorlib]System.Void
0x117160  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x117165  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x11716a  ldarg.0
0x11716b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x117170  ldc.i4.0
0x117171  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x117176  ldarg.0
0x117177  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x11717c  ldc.i4.0
0x11717d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x117182  ldarg.0
0x117183  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x117188  ldc.i4.1
0x117189  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x11718e  ldarg.0
0x11718f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x117194  ldc.i4.0
0x117195  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x11719a  ldarg.0
0x11719b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x1171a0  ldc.i4.0
0x1171a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1171a6  ldarg.0
0x1171a7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>g__initLocal2
0x1171ac  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x1171b1  ldarg.0
0x1171b2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x1171b7  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1171bc  ldarg.0
0x1171bd  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1171c2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x1171c7  ldarg.0
0x1171c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x1171cd  ldstr    aUpdatechildren// "updateChildren"
0x1171d2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1171d7  ldarg.0
0x1171d8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x1171dd  ldc.i4.0
0x1171de  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1171e3  ldarg.0
0x1171e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x1171e9  ldtoken  [mscorlib]System.Boolean
0x1171ee  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1171f3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1171f8  ldarg.0
0x1171f9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x1171fe  ldc.i4.1
0x1171ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x117204  ldarg.0
0x117205  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x11720a  ldc.i4.0
0x11720b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x117210  ldarg.0
0x117211  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x117216  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x11721b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x117220  ldarg.0
0x117221  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__4::<>g__initLocal3
0x117226  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x11722b  ldarg.0
0x11722c  ldarg.0
0x11722d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<item>5__6
0x117232  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__4::<>2__current
0x117237  ldarg.0
0x117238  ldc.i4.5
0x117239  stfld    int32 <GetMethods>d__4::<>1__state
0x11723e  ldc.i4.1
0x11723f  stloc.0
0x117240  leave.s  loc_117254
0x117242  ldarg.0
0x117243  ldc.i4.m1
0x117244  stfld    int32 <GetMethods>d__4::<>1__state
0x117249  ldc.i4.0
0x11724a  stloc.0
0x11724b  leave.s  loc_117254
0x11724d  ldarg.0
0x11724e  call     instance void <GetMethods>d__4::System.IDisposable.Dispose()
0x117253  endfinally
0x117254  ldloc.0
0x117255  ret
  ... truncated ...
```
