# <GetMethods>d__14::MoveNext_0

- ea: `0x12e070`
- end: `0x12edce`
- name: `<GetMethods>d__14::MoveNext_0`
- size: `3422`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x57800`
- `0x12e070`
- `0x12edf0`
- `0x12ee50`

## string_xrefs

- `0x12e78c`: `AddUsingPath`
- `0x12e7c4`: `AddUsingPath`
- `0x12e9d7`: `GetByPathOrAddStub`
- `0x12ea0b`: `GetByPathOrAddStub`
- `0x12e3ee`: `AddStubUsingPath`
- `0x12e422`: `AddStubUsingPath`
- `0x12e5bb`: `AddTemplateFile`
- `0x12e4b0`: `pathOfFile`
- `0x12ea99`: `pathOfFile`
- `0x12e6fb`: `templateFileType`

## pseudocode

```c

```

## disassembly

```asm
0x12e070  ldarg.0
0x12e071  ldfld    int32 <GetMethods>d__14::<>1__state
0x12e076  stloc.1
0x12e077  ldloc.1
0x12e078  switch   loc_12E0AE, loc_12EDC1, loc_12E118, loc_12E282, loc_12E3D5, loc_12E5A2, loc_12E773, loc_12E9BE, loc_12EB11, loc_12EC69, loc_12EDBA
0x12e0a9  br       loc_12EDC1
0x12e0ae  ldarg.0
0x12e0af  ldc.i4.m1
0x12e0b0  stfld    int32 <GetMethods>d__14::<>1__state
0x12e0b5  ldarg.0
0x12e0b6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__14::proxyContext
0x12e0bb  brtrue.s loc_12E0C8
0x12e0bd  ldstr    aProxycontext// "proxyContext"
0x12e0c2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x12e0c7  throw
0x12e0c8  ldarg.0
0x12e0c9  ldarg.0
0x12e0ca  ldfld    class Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub <GetMethods>d__14::<>4__this
0x12e0cf  ldarg.0
0x12e0d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__14::proxyContext
0x12e0d5  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::<>n__FabricatedMethod19(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x12e0da  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x12e0df  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__14::<>7__wrap17
0x12e0e4  ldarg.0
0x12e0e5  ldc.i4.1
0x12e0e6  stfld    int32 <GetMethods>d__14::<>1__state
0x12e0eb  br.s     loc_12E11F
0x12e0ed  ldarg.0
0x12e0ee  ldarg.0
0x12e0ef  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__14::<>7__wrap17
0x12e0f4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x12e0f9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<itemBase>5__15
0x12e0fe  ldarg.0
0x12e0ff  ldarg.0
0x12e100  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<itemBase>5__15
0x12e105  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>2__current
0x12e10a  ldarg.0
0x12e10b  ldc.i4.2
0x12e10c  stfld    int32 <GetMethods>d__14::<>1__state
0x12e111  ldc.i4.1
0x12e112  stloc.0
0x12e113  leave    loc_12EDCC
0x12e118  ldarg.0
0x12e119  ldc.i4.1
0x12e11a  stfld    int32 <GetMethods>d__14::<>1__state
0x12e11f  ldarg.0
0x12e120  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__14::<>7__wrap17
0x12e125  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x12e12a  brtrue.s loc_12E0ED
0x12e12c  ldarg.0
0x12e12d  call     instance void <GetMethods>d__14::<>m__Finally18()
0x12e132  ldarg.0
0x12e133  ldarg.0
0x12e134  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x12e139  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x12e13e  ldarg.0
0x12e13f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x12e144  ldstr    aAdd// "Add"
0x12e149  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x12e14e  ldarg.0
0x12e14f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x12e154  ldc.i4.0
0x12e155  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x12e15a  ldarg.0
0x12e15b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x12e160  ldc.i4.0
0x12e161  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x12e166  ldarg.0
0x12e167  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x12e16c  ldc.i4   0xFFFFFFF
0x12e171  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x12e176  ldarg.0
0x12e177  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x12e17c  ldstr    aAdd// "Add"
0x12e181  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x12e186  ldarg.0
0x12e187  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x12e18c  ldc.i4.0
0x12e18d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x12e192  ldarg.0
0x12e193  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x12e198  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPFile
0x12e19d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12e1a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x12e1a7  ldarg.0
0x12e1a8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x12e1ad  ldc.i4.4
0x12e1ae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x12e1b3  ldarg.0
0x12e1b4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x12e1b9  ldc.i4.0
0x12e1ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x12e1bf  ldarg.0
0x12e1c0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x12e1c5  ldc.i4.1
0x12e1c6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x12e1cb  ldarg.0
0x12e1cc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x12e1d1  ldc.i4.0
0x12e1d2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x12e1d7  ldarg.0
0x12e1d8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x12e1dd  ldc.i4.0
0x12e1de  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x12e1e3  ldarg.0
0x12e1e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal0
0x12e1e9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<item>5__16
0x12e1ee  ldarg.0
0x12e1ef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<item>5__16
0x12e1f4  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x12e1f9  ldarg.0
0x12e1fa  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x12e1ff  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal1
0x12e204  ldarg.0
0x12e205  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal1
0x12e20a  ldstr    aParameters// "parameters"
0x12e20f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x12e214  ldarg.0
0x12e215  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal1
0x12e21a  ldc.i4.1
0x12e21b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x12e220  ldarg.0
0x12e221  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal1
0x12e226  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCreationInformation
0x12e22b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12e230  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x12e235  ldarg.0
0x12e236  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal1
0x12e23b  ldc.i4.2
0x12e23c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x12e241  ldarg.0
0x12e242  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal1
0x12e247  ldc.i4.0
0x12e248  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x12e24d  ldarg.0
0x12e24e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal1
0x12e253  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x12e258  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x12e25d  ldarg.0
0x12e25e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal1
0x12e263  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x12e268  ldarg.0
0x12e269  ldarg.0
0x12e26a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<item>5__16
0x12e26f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>2__current
0x12e274  ldarg.0
0x12e275  ldc.i4.3
0x12e276  stfld    int32 <GetMethods>d__14::<>1__state
0x12e27b  ldc.i4.1
0x12e27c  stloc.0
0x12e27d  leave    loc_12EDCC
0x12e282  ldarg.0
0x12e283  ldc.i4.m1
0x12e284  stfld    int32 <GetMethods>d__14::<>1__state
0x12e289  ldarg.0
0x12e28a  ldarg.0
0x12e28b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x12e290  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal2
0x12e295  ldarg.0
0x12e296  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal2
0x12e29b  ldstr    aAddstub// "AddStub"
0x12e2a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x12e2a5  ldarg.0
0x12e2a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal2
0x12e2ab  ldc.i4.0
0x12e2ac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x12e2b1  ldarg.0
0x12e2b2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal2
0x12e2b7  ldc.i4.0
0x12e2b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x12e2bd  ldarg.0
0x12e2be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal2
0x12e2c3  ldc.i4.8
0x12e2c4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x12e2c9  ldarg.0
0x12e2ca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal2
0x12e2cf  ldstr    aAddstub// "AddStub"
0x12e2d4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x12e2d9  ldarg.0
0x12e2da  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal2
0x12e2df  ldc.i4.0
0x12e2e0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x12e2e5  ldarg.0
0x12e2e6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal2
0x12e2eb  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPFile
0x12e2f0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12e2f5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x12e2fa  ldarg.0
0x12e2fb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal2
0x12e300  ldc.i4.4
0x12e301  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x12e306  ldarg.0
0x12e307  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal2
0x12e30c  ldc.i4.0
0x12e30d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x12e312  ldarg.0
0x12e313  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal2
0x12e318  ldc.i4.0
0x12e319  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x12e31e  ldarg.0
0x12e31f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal2
0x12e324  ldc.i4.0
0x12e325  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x12e32a  ldarg.0
0x12e32b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal2
0x12e330  ldc.i4.0
0x12e331  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x12e336  ldarg.0
0x12e337  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal2
0x12e33c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<item>5__16
0x12e341  ldarg.0
0x12e342  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<item>5__16
0x12e347  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x12e34c  ldarg.0
0x12e34d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x12e352  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal3
0x12e357  ldarg.0
0x12e358  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal3
0x12e35d  ldstr    aUrloffile// "urlOfFile"
0x12e362  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x12e367  ldarg.0
0x12e368  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal3
0x12e36d  ldc.i4.0
0x12e36e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x12e373  ldarg.0
0x12e374  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal3
0x12e379  ldtoken  [mscorlib]System.String
0x12e37e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12e383  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x12e388  ldarg.0
0x12e389  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal3
0x12e38e  ldc.i4.1
0x12e38f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x12e394  ldarg.0
0x12e395  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal3
0x12e39a  ldc.i4.0
0x12e39b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x12e3a0  ldarg.0
0x12e3a1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal3
0x12e3a6  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x12e3ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x12e3b0  ldarg.0
0x12e3b1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__14::<>g__initLocal3
0x12e3b6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x12e3bb  ldarg.0
0x12e3bc  ldarg.0
0x12e3bd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<item>5__16
0x12e3c2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>2__current
0x12e3c7  ldarg.0
0x12e3c8  ldc.i4.4
0x12e3c9  stfld    int32 <GetMethods>d__14::<>1__state
0x12e3ce  ldc.i4.1
0x12e3cf  stloc.0
0x12e3d0  leave    loc_12EDCC
0x12e3d5  ldarg.0
0x12e3d6  ldc.i4.m1
0x12e3d7  stfld    int32 <GetMethods>d__14::<>1__state
0x12e3dc  ldarg.0
0x12e3dd  ldarg.0
0x12e3de  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x12e3e3  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal4
0x12e3e8  ldarg.0
0x12e3e9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal4
0x12e3ee  ldstr    aAddstubusingpa// "AddStubUsingPath"
0x12e3f3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x12e3f8  ldarg.0
0x12e3f9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal4
0x12e3fe  ldc.i4.0
0x12e3ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x12e404  ldarg.0
0x12e405  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal4
0x12e40a  ldc.i4.0
0x12e40b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x12e410  ldarg.0
0x12e411  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal4
0x12e416  ldc.i4.8
0x12e417  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x12e41c  ldarg.0
0x12e41d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal4
0x12e422  ldstr    aAddstubusingpa// "AddStubUsingPath"
0x12e427  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x12e42c  ldarg.0
0x12e42d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal4
0x12e432  ldc.i4.0
0x12e433  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x12e438  ldarg.0
0x12e439  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal4
0x12e43e  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPFile
0x12e443  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12e448  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x12e44d  ldarg.0
0x12e44e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal4
0x12e453  ldc.i4.4
0x12e454  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x12e459  ldarg.0
0x12e45a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal4
0x12e45f  ldc.i4.0
0x12e460  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x12e465  ldarg.0
0x12e466  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__14::<>g__initLocal4
  ... truncated ...
```
