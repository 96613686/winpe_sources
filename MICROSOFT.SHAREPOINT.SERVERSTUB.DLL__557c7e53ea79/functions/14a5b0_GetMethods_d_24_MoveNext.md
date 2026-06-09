# <GetMethods>d__24::MoveNext

- ea: `0x14a5b0`
- end: `0x14ba9e`
- name: `<GetMethods>d__24::MoveNext`
- size: `5358`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x6d370`
- `0x14a5b0`
- `0x14bac0`
- `0x14bb20`

## string_xrefs

- `0x14a83e`: `overwrite`
- `0x14aaff`: `overwrite`
- `0x14b24e`: `overwrite`
- `0x14b50f`: `overwrite`
- `0x14b094`: `MoveFile`
- `0x14b0cc`: `MoveFile`
- `0x14b38d`: `MoveFile`
- `0x14b355`: `MoveFileByPath`
- `0x14a684`: `CopyFile`
- `0x14a6bc`: `CopyFile`
- `0x14a97d`: `CopyFile`
- `0x14a945`: `CopyFileByPath`
- `0x14b616`: `MoveFolder`
- `0x14b64e`: `MoveFolder`
- `0x14b896`: `MoveFolder`
- `0x14b85e`: `MoveFolderByPath`
- `0x14ac06`: `CopyFolder`
- `0x14ac3e`: `CopyFolder`
- `0x14ae85`: `CopyFolder`
- `0x14ae4d`: `CopyFolderByPath`
- `0x14aa0b`: `srcPath`
- `0x14af13`: `srcPath`
- `0x14b41b`: `srcPath`
- `0x14b924`: `srcPath`
- `0x14aa85`: `destPath`
- `0x14af8d`: `destPath`
- `0x14b495`: `destPath`
- `0x14b99e`: `destPath`

## pseudocode

```c

```

## disassembly

```asm
0x14a5b0  ldarg.0
0x14a5b1  ldfld    int32 <GetMethods>d__24::<>1__state
0x14a5b6  stloc.1
0x14a5b7  ldloc.1
0x14a5b8  switch   loc_14A5EE, loc_14BA91, loc_14A658, loc_14A92C, loc_14ABED, loc_14AE34, loc_14B07B, loc_14B33C, loc_14B5FD, loc_14B845, loc_14BA8A
0x14a5e9  br       loc_14BA91
0x14a5ee  ldarg.0
0x14a5ef  ldc.i4.m1
0x14a5f0  stfld    int32 <GetMethods>d__24::<>1__state
0x14a5f5  ldarg.0
0x14a5f6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__24::proxyContext
0x14a5fb  brtrue.s loc_14A608
0x14a5fd  ldstr    aProxycontext// "proxyContext"
0x14a602  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x14a607  throw
0x14a608  ldarg.0
0x14a609  ldarg.0
0x14a60a  ldfld    class Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub <GetMethods>d__24::<>4__this
0x14a60f  ldarg.0
0x14a610  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__24::proxyContext
0x14a615  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::<>n__FabricatedMethod29(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x14a61a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x14a61f  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__24::<>7__wrap27
0x14a624  ldarg.0
0x14a625  ldc.i4.1
0x14a626  stfld    int32 <GetMethods>d__24::<>1__state
0x14a62b  br.s     loc_14A65F
0x14a62d  ldarg.0
0x14a62e  ldarg.0
0x14a62f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__24::<>7__wrap27
0x14a634  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x14a639  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<itemBase>5__25
0x14a63e  ldarg.0
0x14a63f  ldarg.0
0x14a640  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<itemBase>5__25
0x14a645  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>2__current
0x14a64a  ldarg.0
0x14a64b  ldc.i4.2
0x14a64c  stfld    int32 <GetMethods>d__24::<>1__state
0x14a651  ldc.i4.1
0x14a652  stloc.0
0x14a653  leave    loc_14BA9C
0x14a658  ldarg.0
0x14a659  ldc.i4.1
0x14a65a  stfld    int32 <GetMethods>d__24::<>1__state
0x14a65f  ldarg.0
0x14a660  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__24::<>7__wrap27
0x14a665  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x14a66a  brtrue.s loc_14A62D
0x14a66c  ldarg.0
0x14a66d  call     instance void <GetMethods>d__24::<>m__Finally28()
0x14a672  ldarg.0
0x14a673  ldarg.0
0x14a674  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x14a679  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal0
0x14a67e  ldarg.0
0x14a67f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal0
0x14a684  ldstr    aCopyfile// "CopyFile"
0x14a689  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x14a68e  ldarg.0
0x14a68f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal0
0x14a694  ldc.i4.1
0x14a695  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x14a69a  ldarg.0
0x14a69b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal0
0x14a6a0  ldc.i4.0
0x14a6a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x14a6a6  ldarg.0
0x14a6a7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal0
0x14a6ac  ldc.i4   0xFFFFFFF
0x14a6b1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x14a6b6  ldarg.0
0x14a6b7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal0
0x14a6bc  ldstr    aCopyfile// "CopyFile"
0x14a6c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x14a6c6  ldarg.0
0x14a6c7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal0
0x14a6cc  ldc.i4.0
0x14a6cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x14a6d2  ldarg.0
0x14a6d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal0
0x14a6d8  ldtoken  [mscorlib]System.Void
0x14a6dd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14a6e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x14a6e7  ldarg.0
0x14a6e8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal0
0x14a6ed  ldc.i4.0
0x14a6ee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14a6f3  ldarg.0
0x14a6f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal0
0x14a6f9  ldc.i4.0
0x14a6fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x14a6ff  ldarg.0
0x14a700  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal0
0x14a705  ldc.i4.0
0x14a706  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x14a70b  ldarg.0
0x14a70c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal0
0x14a711  ldc.i4.0
0x14a712  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x14a717  ldarg.0
0x14a718  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal0
0x14a71d  ldc.i4.0
0x14a71e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x14a723  ldarg.0
0x14a724  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal0
0x14a729  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<item>5__26
0x14a72e  ldarg.0
0x14a72f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<item>5__26
0x14a734  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x14a739  ldarg.0
0x14a73a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x14a73f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal1
0x14a744  ldarg.0
0x14a745  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal1
0x14a74a  ldstr    aSrcurl// "srcUrl"
0x14a74f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x14a754  ldarg.0
0x14a755  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal1
0x14a75a  ldc.i4.0
0x14a75b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x14a760  ldarg.0
0x14a761  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal1
0x14a766  ldtoken  [mscorlib]System.String
0x14a76b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14a770  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x14a775  ldarg.0
0x14a776  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal1
0x14a77b  ldc.i4.1
0x14a77c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14a781  ldarg.0
0x14a782  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal1
0x14a787  ldc.i4.0
0x14a788  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x14a78d  ldarg.0
0x14a78e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal1
0x14a793  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x14a798  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x14a79d  ldarg.0
0x14a79e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal1
0x14a7a3  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x14a7a8  ldarg.0
0x14a7a9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<item>5__26
0x14a7ae  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x14a7b3  ldarg.0
0x14a7b4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x14a7b9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal2
0x14a7be  ldarg.0
0x14a7bf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal2
0x14a7c4  ldstr    aDesturl// "destUrl"
0x14a7c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x14a7ce  ldarg.0
0x14a7cf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal2
0x14a7d4  ldc.i4.0
0x14a7d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x14a7da  ldarg.0
0x14a7db  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal2
0x14a7e0  ldtoken  [mscorlib]System.String
0x14a7e5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14a7ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x14a7ef  ldarg.0
0x14a7f0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal2
0x14a7f5  ldc.i4.1
0x14a7f6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14a7fb  ldarg.0
0x14a7fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal2
0x14a801  ldc.i4.0
0x14a802  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x14a807  ldarg.0
0x14a808  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal2
0x14a80d  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x14a812  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x14a817  ldarg.0
0x14a818  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal2
0x14a81d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x14a822  ldarg.0
0x14a823  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<item>5__26
0x14a828  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x14a82d  ldarg.0
0x14a82e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x14a833  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal3
0x14a838  ldarg.0
0x14a839  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal3
0x14a83e  ldstr    aOverwrite_0// "overwrite"
0x14a843  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x14a848  ldarg.0
0x14a849  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal3
0x14a84e  ldc.i4.0
0x14a84f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x14a854  ldarg.0
0x14a855  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal3
0x14a85a  ldtoken  [mscorlib]System.Boolean
0x14a85f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14a864  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x14a869  ldarg.0
0x14a86a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal3
0x14a86f  ldc.i4.1
0x14a870  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14a875  ldarg.0
0x14a876  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal3
0x14a87b  ldc.i4.0
0x14a87c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x14a881  ldarg.0
0x14a882  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal3
0x14a887  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x14a88c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x14a891  ldarg.0
0x14a892  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal3
0x14a897  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x14a89c  ldarg.0
0x14a89d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<item>5__26
0x14a8a2  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x14a8a7  ldarg.0
0x14a8a8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x14a8ad  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal4
0x14a8b2  ldarg.0
0x14a8b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal4
0x14a8b8  ldstr    aOptions// "options"
0x14a8bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x14a8c2  ldarg.0
0x14a8c3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal4
0x14a8c8  ldc.i4.0
0x14a8c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x14a8ce  ldarg.0
0x14a8cf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal4
0x14a8d4  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPMoveCopyOptions
0x14a8d9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14a8de  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x14a8e3  ldarg.0
0x14a8e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal4
0x14a8e9  ldc.i4.2
0x14a8ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14a8ef  ldarg.0
0x14a8f0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal4
0x14a8f5  ldc.i4.1
0x14a8f6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x14a8fb  ldarg.0
0x14a8fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal4
0x14a901  ldnull
0x14a902  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x14a907  ldarg.0
0x14a908  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__24::<>g__initLocal4
0x14a90d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x14a912  ldarg.0
0x14a913  ldarg.0
0x14a914  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<item>5__26
0x14a919  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>2__current
0x14a91e  ldarg.0
0x14a91f  ldc.i4.3
0x14a920  stfld    int32 <GetMethods>d__24::<>1__state
0x14a925  ldc.i4.1
0x14a926  stloc.0
0x14a927  leave    loc_14BA9C
0x14a92c  ldarg.0
0x14a92d  ldc.i4.m1
0x14a92e  stfld    int32 <GetMethods>d__24::<>1__state
0x14a933  ldarg.0
0x14a934  ldarg.0
0x14a935  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x14a93a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal5
0x14a93f  ldarg.0
0x14a940  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal5
0x14a945  ldstr    aCopyfilebypath// "CopyFileByPath"
0x14a94a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x14a94f  ldarg.0
0x14a950  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal5
0x14a955  ldc.i4.1
0x14a956  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x14a95b  ldarg.0
0x14a95c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal5
0x14a961  ldc.i4.0
0x14a962  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x14a967  ldarg.0
0x14a968  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal5
0x14a96d  ldc.i4   0xFFFFFFF
0x14a972  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x14a977  ldarg.0
0x14a978  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal5
0x14a97d  ldstr    aCopyfile// "CopyFile"
0x14a982  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x14a987  ldarg.0
0x14a988  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal5
0x14a98d  ldc.i4.0
0x14a98e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x14a993  ldarg.0
0x14a994  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal5
0x14a999  ldtoken  [mscorlib]System.Void
0x14a99e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14a9a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x14a9a8  ldarg.0
0x14a9a9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal5
0x14a9ae  ldc.i4.0
0x14a9af  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14a9b4  ldarg.0
0x14a9b5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal5
0x14a9ba  ldc.i4.0
0x14a9bb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x14a9c0  ldarg.0
0x14a9c1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__24::<>g__initLocal5
0x14a9c6  ldc.i4.0
  ... truncated ...
```
