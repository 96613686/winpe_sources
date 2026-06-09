# <GetMethods>d__58::MoveNext

- ea: `0x196d40`
- end: `0x19a2a4`
- name: `<GetMethods>d__58::MoveNext`
- size: `13668`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xa2140`
- `0x196d40`
- `0x19a2d0`
- `0x19a330`

## string_xrefs

- `0x1974a4`: `CreateWikiPageInContextWeb`
- `0x1974dc`: `CreateWikiPageInContextWeb`
- `0x196fb7`: `CreateNewDiscussion`
- `0x196feb`: `CreateNewDiscussion`
- `0x197184`: `CreateNewDiscussionItem`
- `0x197351`: `CreateNewDiscussionReply`
- `0x197385`: `CreateNewDiscussionReply`
- `0x196e60`: `CreateEmailBodyForInvitation`
- `0x196e98`: `CreateEmailBodyForInvitation`
- `0x1971b8`: `CreateNewDiscussion_Client`
- `0x1984b4`: `licenseTokenToImport`

## pseudocode

```c

```

## disassembly

```asm
0x196d40  ldarg.0
0x196d41  ldfld    int32 <GetMethods>d__58::<>1__state
0x196d46  stloc.1
0x196d47  ldloc.1
0x196d48  switch   loc_196DCA, loc_19A297, loc_196E34, loc_196F9E, loc_19716B, loc_197338, loc_19748B, loc_1975E2, loc_1977AF, loc_1979F7, loc_197AD5, loc_197C2D, loc_197D0B, loc_197F57, loc_198129, loc_1982F7, loc_1983D5, loc_198809, loc_198961, loc_198AB9, loc_198C11, loc_198D69, loc_198F3B, loc_19910D, loc_1994C3, loc_19987A, loc_199C30, loc_199F6C, loc_19A0C1, loc_19A290
0x196dc5  br       loc_19A297
0x196dca  ldarg.0
0x196dcb  ldc.i4.m1
0x196dcc  stfld    int32 <GetMethods>d__58::<>1__state
0x196dd1  ldarg.0
0x196dd2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__58::proxyContext
0x196dd7  brtrue.s loc_196DE4
0x196dd9  ldstr    aProxycontext// "proxyContext"
0x196dde  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x196de3  throw
0x196de4  ldarg.0
0x196de5  ldarg.0
0x196de6  ldfld    class Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub <GetMethods>d__58::<>4__this
0x196deb  ldarg.0
0x196dec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__58::proxyContext
0x196df1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::<>n__FabricatedMethod5d(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x196df6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x196dfb  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__58::<>7__wrap5b
0x196e00  ldarg.0
0x196e01  ldc.i4.1
0x196e02  stfld    int32 <GetMethods>d__58::<>1__state
0x196e07  br.s     loc_196E3B
0x196e09  ldarg.0
0x196e0a  ldarg.0
0x196e0b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__58::<>7__wrap5b
0x196e10  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x196e15  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<itemBase>5__59
0x196e1a  ldarg.0
0x196e1b  ldarg.0
0x196e1c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<itemBase>5__59
0x196e21  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>2__current
0x196e26  ldarg.0
0x196e27  ldc.i4.2
0x196e28  stfld    int32 <GetMethods>d__58::<>1__state
0x196e2d  ldc.i4.1
0x196e2e  stloc.0
0x196e2f  leave    loc_19A2A2
0x196e34  ldarg.0
0x196e35  ldc.i4.1
0x196e36  stfld    int32 <GetMethods>d__58::<>1__state
0x196e3b  ldarg.0
0x196e3c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__58::<>7__wrap5b
0x196e41  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x196e46  brtrue.s loc_196E09
0x196e48  ldarg.0
0x196e49  call     instance void <GetMethods>d__58::<>m__Finally5c()
0x196e4e  ldarg.0
0x196e4f  ldarg.0
0x196e50  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x196e55  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal0
0x196e5a  ldarg.0
0x196e5b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal0
0x196e60  ldstr    aCreateemailbod// "CreateEmailBodyForInvitation"
0x196e65  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x196e6a  ldarg.0
0x196e6b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal0
0x196e70  ldc.i4.1
0x196e71  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x196e76  ldarg.0
0x196e77  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal0
0x196e7c  ldc.i4.0
0x196e7d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x196e82  ldarg.0
0x196e83  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal0
0x196e88  ldc.i4   0xFFFFFFF
0x196e8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x196e92  ldarg.0
0x196e93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal0
0x196e98  ldstr    aCreateemailbod// "CreateEmailBodyForInvitation"
0x196e9d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x196ea2  ldarg.0
0x196ea3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal0
0x196ea8  ldc.i4.0
0x196ea9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x196eae  ldarg.0
0x196eaf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal0
0x196eb4  ldtoken  [mscorlib]System.String
0x196eb9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x196ebe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x196ec3  ldarg.0
0x196ec4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal0
0x196ec9  ldc.i4.1
0x196eca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x196ecf  ldarg.0
0x196ed0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal0
0x196ed5  ldc.i4.0
0x196ed6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x196edb  ldarg.0
0x196edc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal0
0x196ee1  ldc.i4.0
0x196ee2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x196ee7  ldarg.0
0x196ee8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal0
0x196eed  ldc.i4.0
0x196eee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x196ef3  ldarg.0
0x196ef4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal0
0x196ef9  ldc.i4.0
0x196efa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x196eff  ldarg.0
0x196f00  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal0
0x196f05  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<item>5__5a
0x196f0a  ldarg.0
0x196f0b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<item>5__5a
0x196f10  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x196f15  ldarg.0
0x196f16  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x196f1b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal1
0x196f20  ldarg.0
0x196f21  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal1
0x196f26  ldstr    aPageaddress// "pageAddress"
0x196f2b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x196f30  ldarg.0
0x196f31  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal1
0x196f36  ldc.i4.0
0x196f37  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x196f3c  ldarg.0
0x196f3d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal1
0x196f42  ldtoken  [mscorlib]System.String
0x196f47  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x196f4c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x196f51  ldarg.0
0x196f52  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal1
0x196f57  ldc.i4.1
0x196f58  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x196f5d  ldarg.0
0x196f5e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal1
0x196f63  ldc.i4.0
0x196f64  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x196f69  ldarg.0
0x196f6a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal1
0x196f6f  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x196f74  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x196f79  ldarg.0
0x196f7a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal1
0x196f7f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x196f84  ldarg.0
0x196f85  ldarg.0
0x196f86  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<item>5__5a
0x196f8b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>2__current
0x196f90  ldarg.0
0x196f91  ldc.i4.3
0x196f92  stfld    int32 <GetMethods>d__58::<>1__state
0x196f97  ldc.i4.1
0x196f98  stloc.0
0x196f99  leave    loc_19A2A2
0x196f9e  ldarg.0
0x196f9f  ldc.i4.m1
0x196fa0  stfld    int32 <GetMethods>d__58::<>1__state
0x196fa5  ldarg.0
0x196fa6  ldarg.0
0x196fa7  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x196fac  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal2
0x196fb1  ldarg.0
0x196fb2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal2
0x196fb7  ldstr    aCreatenewdiscu// "CreateNewDiscussion"
0x196fbc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x196fc1  ldarg.0
0x196fc2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal2
0x196fc7  ldc.i4.1
0x196fc8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x196fcd  ldarg.0
0x196fce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal2
0x196fd3  ldc.i4.0
0x196fd4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x196fd9  ldarg.0
0x196fda  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal2
0x196fdf  ldc.i4.7
0x196fe0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x196fe5  ldarg.0
0x196fe6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal2
0x196feb  ldstr    aCreatenewdiscu// "CreateNewDiscussion"
0x196ff0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x196ff5  ldarg.0
0x196ff6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal2
0x196ffb  ldc.i4.0
0x196ffc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x197001  ldarg.0
0x197002  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal2
0x197007  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem
0x19700c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x197011  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x197016  ldarg.0
0x197017  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal2
0x19701c  ldc.i4.4
0x19701d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x197022  ldarg.0
0x197023  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal2
0x197028  ldc.i4.0
0x197029  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x19702e  ldarg.0
0x19702f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal2
0x197034  ldc.i4.0
0x197035  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x19703a  ldarg.0
0x19703b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal2
0x197040  ldc.i4.0
0x197041  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x197046  ldarg.0
0x197047  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal2
0x19704c  ldc.i4.0
0x19704d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x197052  ldarg.0
0x197053  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal2
0x197058  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<item>5__5a
0x19705d  ldarg.0
0x19705e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<item>5__5a
0x197063  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x197068  ldarg.0
0x197069  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x19706e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal3
0x197073  ldarg.0
0x197074  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal3
0x197079  ldstr    aList_0// "list"
0x19707e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x197083  ldarg.0
0x197084  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal3
0x197089  ldc.i4.0
0x19708a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x19708f  ldarg.0
0x197090  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal3
0x197095  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPList
0x19709a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19709f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1970a4  ldarg.0
0x1970a5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal3
0x1970aa  ldc.i4.0
0x1970ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1970b0  ldarg.0
0x1970b1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal3
0x1970b6  ldc.i4.0
0x1970b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1970bc  ldarg.0
0x1970bd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal3
0x1970c2  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1970c7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1970cc  ldarg.0
0x1970cd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal3
0x1970d2  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1970d7  ldarg.0
0x1970d8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<item>5__5a
0x1970dd  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1970e2  ldarg.0
0x1970e3  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1970e8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal4
0x1970ed  ldarg.0
0x1970ee  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal4
0x1970f3  ldstr    aTitle_0// "title"
0x1970f8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1970fd  ldarg.0
0x1970fe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal4
0x197103  ldc.i4.0
0x197104  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x197109  ldarg.0
0x19710a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal4
0x19710f  ldtoken  [mscorlib]System.String
0x197114  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x197119  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x19711e  ldarg.0
0x19711f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal4
0x197124  ldc.i4.1
0x197125  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x19712a  ldarg.0
0x19712b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal4
0x197130  ldc.i4.0
0x197131  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x197136  ldarg.0
0x197137  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal4
0x19713c  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x197141  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x197146  ldarg.0
0x197147  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__58::<>g__initLocal4
0x19714c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x197151  ldarg.0
0x197152  ldarg.0
0x197153  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<item>5__5a
0x197158  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>2__current
0x19715d  ldarg.0
0x19715e  ldc.i4.4
0x19715f  stfld    int32 <GetMethods>d__58::<>1__state
0x197164  ldc.i4.1
0x197165  stloc.0
0x197166  leave    loc_19A2A2
0x19716b  ldarg.0
0x19716c  ldc.i4.m1
0x19716d  stfld    int32 <GetMethods>d__58::<>1__state
0x197172  ldarg.0
0x197173  ldarg.0
0x197174  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x197179  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal5
0x19717e  ldarg.0
0x19717f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__58::<>g__initLocal5
0x197184  ldstr    aCreatenewdiscu_0// "CreateNewDiscussionItem"
0x197189  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x19718e  ldarg.0
  ... truncated ...
```
