# <GetMethods>d__12::MoveNext_1

- ea: `0x195c70`
- end: `0x19692e`
- name: `<GetMethods>d__12::MoveNext_1`
- size: `3262`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0xa0b50`
- `0x195c70`
- `0x196950`
- `0x1969b0`

## string_xrefs

- `0x195e84`: `themeJson`
- `0x196051`: `themeJson`
- `0x1968a4`: `themeJson`
- `0x196768`: `UpdateTenantTheme`
- `0x19679c`: `UpdateTenantTheme`
- `0x1960e2`: `DeleteTenantTheme`
- `0x196116`: `DeleteTenantTheme`

## pseudocode

```c

```

## disassembly

```asm
0x195c70  ldarg.0
0x195c71  ldfld    int32 <GetMethods>d__12::<>1__state
0x195c76  stloc.1
0x195c77  ldloc.1
0x195c78  switch   loc_195CB2, loc_196921, loc_195D1C, loc_195EFC, loc_1960C9, loc_19621C, loc_1962F5, loc_1963CE, loc_196521, loc_1965FB, loc_19674F, loc_19691A
0x195cad  br       loc_196921
0x195cb2  ldarg.0
0x195cb3  ldc.i4.m1
0x195cb4  stfld    int32 <GetMethods>d__12::<>1__state
0x195cb9  ldarg.0
0x195cba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__12::proxyContext
0x195cbf  brtrue.s loc_195CCC
0x195cc1  ldstr    aProxycontext// "proxyContext"
0x195cc6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x195ccb  throw
0x195ccc  ldarg.0
0x195ccd  ldarg.0
0x195cce  ldfld    class Microsoft.SharePoint.ServerStub.Utilities.SPThemeManagerServerStub <GetMethods>d__12::<>4__this
0x195cd3  ldarg.0
0x195cd4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__12::proxyContext
0x195cd9  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.Utilities.SPThemeManagerServerStub::<>n__FabricatedMethod17(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext xmlargs)
0x195cde  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x195ce3  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__12::<>7__wrap15
0x195ce8  ldarg.0
0x195ce9  ldc.i4.1
0x195cea  stfld    int32 <GetMethods>d__12::<>1__state
0x195cef  br.s     loc_195D23
0x195cf1  ldarg.0
0x195cf2  ldarg.0
0x195cf3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__12::<>7__wrap15
0x195cf8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x195cfd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<itemBase>5__13
0x195d02  ldarg.0
0x195d03  ldarg.0
0x195d04  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<itemBase>5__13
0x195d09  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>2__current
0x195d0e  ldarg.0
0x195d0f  ldc.i4.2
0x195d10  stfld    int32 <GetMethods>d__12::<>1__state
0x195d15  ldc.i4.1
0x195d16  stloc.0
0x195d17  leave    loc_19692C
0x195d1c  ldarg.0
0x195d1d  ldc.i4.1
0x195d1e  stfld    int32 <GetMethods>d__12::<>1__state
0x195d23  ldarg.0
0x195d24  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__12::<>7__wrap15
0x195d29  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x195d2e  brtrue.s loc_195CF1
0x195d30  ldarg.0
0x195d31  call     instance void <GetMethods>d__12::<>m__Finally16()
0x195d36  ldarg.0
0x195d37  ldarg.0
0x195d38  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x195d3d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x195d42  ldarg.0
0x195d43  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x195d48  ldstr    aAddtenanttheme// "AddTenantTheme"
0x195d4d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x195d52  ldarg.0
0x195d53  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x195d58  ldc.i4.0
0x195d59  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x195d5e  ldarg.0
0x195d5f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x195d64  ldc.i4.0
0x195d65  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x195d6a  ldarg.0
0x195d6b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x195d70  ldc.i4.8
0x195d71  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x195d76  ldarg.0
0x195d77  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x195d7c  ldstr    aAddtenanttheme// "AddTenantTheme"
0x195d81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x195d86  ldarg.0
0x195d87  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x195d8c  ldc.i4.0
0x195d8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x195d92  ldarg.0
0x195d93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x195d98  ldtoken  [mscorlib]System.Boolean
0x195d9d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x195da2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x195da7  ldarg.0
0x195da8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x195dad  ldc.i4.1
0x195dae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x195db3  ldarg.0
0x195db4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x195db9  ldc.i4.0
0x195dba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x195dbf  ldarg.0
0x195dc0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x195dc5  ldc.i4.0
0x195dc6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x195dcb  ldarg.0
0x195dcc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x195dd1  ldc.i4.0
0x195dd2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x195dd7  ldarg.0
0x195dd8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x195ddd  ldc.i4.1
0x195dde  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x195de3  ldarg.0
0x195de4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal0
0x195de9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<item>5__14
0x195dee  ldarg.0
0x195def  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<item>5__14
0x195df4  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x195df9  ldarg.0
0x195dfa  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x195dff  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal1
0x195e04  ldarg.0
0x195e05  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal1
0x195e0a  ldstr    aName_0// "name"
0x195e0f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x195e14  ldarg.0
0x195e15  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal1
0x195e1a  ldc.i4.0
0x195e1b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x195e20  ldarg.0
0x195e21  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal1
0x195e26  ldtoken  [mscorlib]System.String
0x195e2b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x195e30  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x195e35  ldarg.0
0x195e36  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal1
0x195e3b  ldc.i4.1
0x195e3c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x195e41  ldarg.0
0x195e42  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal1
0x195e47  ldc.i4.0
0x195e48  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x195e4d  ldarg.0
0x195e4e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal1
0x195e53  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x195e58  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x195e5d  ldarg.0
0x195e5e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal1
0x195e63  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x195e68  ldarg.0
0x195e69  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<item>5__14
0x195e6e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x195e73  ldarg.0
0x195e74  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x195e79  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal2
0x195e7e  ldarg.0
0x195e7f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal2
0x195e84  ldstr    aThemejson// "themeJson"
0x195e89  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x195e8e  ldarg.0
0x195e8f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal2
0x195e94  ldc.i4.0
0x195e95  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x195e9a  ldarg.0
0x195e9b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal2
0x195ea0  ldtoken  [mscorlib]System.String
0x195ea5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x195eaa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x195eaf  ldarg.0
0x195eb0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal2
0x195eb5  ldc.i4.1
0x195eb6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x195ebb  ldarg.0
0x195ebc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal2
0x195ec1  ldc.i4.0
0x195ec2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x195ec7  ldarg.0
0x195ec8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal2
0x195ecd  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x195ed2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x195ed7  ldarg.0
0x195ed8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal2
0x195edd  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x195ee2  ldarg.0
0x195ee3  ldarg.0
0x195ee4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<item>5__14
0x195ee9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>2__current
0x195eee  ldarg.0
0x195eef  ldc.i4.3
0x195ef0  stfld    int32 <GetMethods>d__12::<>1__state
0x195ef5  ldc.i4.1
0x195ef6  stloc.0
0x195ef7  leave    loc_19692C
0x195efc  ldarg.0
0x195efd  ldc.i4.m1
0x195efe  stfld    int32 <GetMethods>d__12::<>1__state
0x195f03  ldarg.0
0x195f04  ldarg.0
0x195f05  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x195f0a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal3
0x195f0f  ldarg.0
0x195f10  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal3
0x195f15  ldstr    aApplytheme// "ApplyTheme"
0x195f1a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x195f1f  ldarg.0
0x195f20  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal3
0x195f25  ldc.i4.0
0x195f26  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x195f2b  ldarg.0
0x195f2c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal3
0x195f31  ldc.i4.0
0x195f32  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x195f37  ldarg.0
0x195f38  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal3
0x195f3d  ldc.i4.8
0x195f3e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x195f43  ldarg.0
0x195f44  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal3
0x195f49  ldstr    aApplytheme// "ApplyTheme"
0x195f4e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x195f53  ldarg.0
0x195f54  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal3
0x195f59  ldc.i4.0
0x195f5a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x195f5f  ldarg.0
0x195f60  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal3
0x195f65  ldtoken  [mscorlib]System.String
0x195f6a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x195f6f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x195f74  ldarg.0
0x195f75  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal3
0x195f7a  ldc.i4.1
0x195f7b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x195f80  ldarg.0
0x195f81  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal3
0x195f86  ldc.i4.0
0x195f87  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x195f8c  ldarg.0
0x195f8d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal3
0x195f92  ldc.i4.0
0x195f93  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x195f98  ldarg.0
0x195f99  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal3
0x195f9e  ldc.i4.0
0x195f9f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x195fa4  ldarg.0
0x195fa5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal3
0x195faa  ldc.i4.1
0x195fab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x195fb0  ldarg.0
0x195fb1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<>g__initLocal3
0x195fb6  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<item>5__14
0x195fbb  ldarg.0
0x195fbc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<item>5__14
0x195fc1  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x195fc6  ldarg.0
0x195fc7  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x195fcc  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal4
0x195fd1  ldarg.0
0x195fd2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal4
0x195fd7  ldstr    aName_0// "name"
0x195fdc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x195fe1  ldarg.0
0x195fe2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal4
0x195fe7  ldc.i4.0
0x195fe8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x195fed  ldarg.0
0x195fee  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal4
0x195ff3  ldtoken  [mscorlib]System.String
0x195ff8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x195ffd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x196002  ldarg.0
0x196003  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal4
0x196008  ldc.i4.1
0x196009  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x19600e  ldarg.0
0x19600f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal4
0x196014  ldc.i4.0
0x196015  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x19601a  ldarg.0
0x19601b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal4
0x196020  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x196025  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x19602a  ldarg.0
0x19602b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal4
0x196030  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x196035  ldarg.0
0x196036  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__12::<item>5__14
0x19603b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x196040  ldarg.0
0x196041  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x196046  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal5
0x19604b  ldarg.0
0x19604c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal5
0x196051  ldstr    aThemejson// "themeJson"
0x196056  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x19605b  ldarg.0
0x19605c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal5
0x196061  ldc.i4.0
0x196062  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x196067  ldarg.0
0x196068  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal5
0x19606d  ldtoken  [mscorlib]System.String
0x196072  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x196077  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x19607c  ldarg.0
0x19607d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__12::<>g__initLocal5
0x196082  ldc.i4.1
  ... truncated ...
```
