# <GetMethods>d__33::MoveNext

- ea: `0x113b00`
- end: `0x1159a4`
- name: `<GetMethods>d__33::MoveNext`
- size: `7844`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x41d20`
- `0x113b00`
- `0x1159d0`
- `0x115a30`

## string_xrefs

- `0x1140ce`: `folderPath`
- `0x114b52`: `folderPath`
- `0x11504e`: `folderPath`
- `0x115654`: `comments`
- `0x113dbd`: `DeleteListItem`
- `0x113df5`: `DeleteListItem`
- `0x114f0e`: `GetUpdatedListItems`
- `0x114f46`: `GetUpdatedListItems`
- `0x113f8e`: `GetDeletedListItems`
- `0x113fc6`: `GetDeletedListItems`
- `0x113bec`: `CreateListItem`
- `0x113c24`: `CreateListItem`
- `0x115760`: `UpdateListItem`
- `0x115798`: `UpdateListItem`

## pseudocode

```c

```

## disassembly

```asm
0x113b00  ldarg.0
0x113b01  ldfld    int32 <GetMethods>d__33::<>1__state
0x113b06  stloc.1
0x113b07  ldloc.1
0x113b08  switch   loc_113B56, loc_115997, loc_113BC0, loc_113DA4, loc_113F75, loc_11423A, loc_11440B, loc_114656, loc_114827, loc_1149F9, loc_114CBF, loc_114E17, loc_114EF5, loc_1151BB, loc_115407, loc_115747, loc_115990
0x113b51  br       loc_115997
0x113b56  ldarg.0
0x113b57  ldc.i4.m1
0x113b58  stfld    int32 <GetMethods>d__33::<>1__state
0x113b5d  ldarg.0
0x113b5e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__33::proxyContext
0x113b63  brtrue.s loc_113B70
0x113b65  ldstr    aProxycontext// "proxyContext"
0x113b6a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x113b6f  throw
0x113b70  ldarg.0
0x113b71  ldarg.0
0x113b72  ldfld    class Microsoft.SharePoint.ServerStub.SPConnectorServerStub <GetMethods>d__33::<>4__this
0x113b77  ldarg.0
0x113b78  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__33::proxyContext
0x113b7d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPConnectorServerStub::<>n__FabricatedMethod38(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x113b82  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x113b87  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__33::<>7__wrap36
0x113b8c  ldarg.0
0x113b8d  ldc.i4.1
0x113b8e  stfld    int32 <GetMethods>d__33::<>1__state
0x113b93  br.s     loc_113BC7
0x113b95  ldarg.0
0x113b96  ldarg.0
0x113b97  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__33::<>7__wrap36
0x113b9c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x113ba1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<itemBase>5__34
0x113ba6  ldarg.0
0x113ba7  ldarg.0
0x113ba8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<itemBase>5__34
0x113bad  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>2__current
0x113bb2  ldarg.0
0x113bb3  ldc.i4.2
0x113bb4  stfld    int32 <GetMethods>d__33::<>1__state
0x113bb9  ldc.i4.1
0x113bba  stloc.0
0x113bbb  leave    loc_1159A2
0x113bc0  ldarg.0
0x113bc1  ldc.i4.1
0x113bc2  stfld    int32 <GetMethods>d__33::<>1__state
0x113bc7  ldarg.0
0x113bc8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__33::<>7__wrap36
0x113bcd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x113bd2  brtrue.s loc_113B95
0x113bd4  ldarg.0
0x113bd5  call     instance void <GetMethods>d__33::<>m__Finally37()
0x113bda  ldarg.0
0x113bdb  ldarg.0
0x113bdc  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x113be1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal0
0x113be6  ldarg.0
0x113be7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal0
0x113bec  ldstr    aCreatelistitem// "CreateListItem"
0x113bf1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x113bf6  ldarg.0
0x113bf7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal0
0x113bfc  ldc.i4.1
0x113bfd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x113c02  ldarg.0
0x113c03  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal0
0x113c08  ldc.i4.0
0x113c09  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x113c0e  ldarg.0
0x113c0f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal0
0x113c14  ldc.i4   0xFFFFFFF
0x113c19  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x113c1e  ldarg.0
0x113c1f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal0
0x113c24  ldstr    aCreatelistitem// "CreateListItem"
0x113c29  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x113c2e  ldarg.0
0x113c2f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal0
0x113c34  ldc.i4.0
0x113c35  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x113c3a  ldarg.0
0x113c3b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal0
0x113c40  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult
0x113c45  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x113c4a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x113c4f  ldarg.0
0x113c50  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal0
0x113c55  ldc.i4.4
0x113c56  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x113c5b  ldarg.0
0x113c5c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal0
0x113c61  ldc.i4.0
0x113c62  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x113c67  ldarg.0
0x113c68  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal0
0x113c6d  ldc.i4.0
0x113c6e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x113c73  ldarg.0
0x113c74  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal0
0x113c79  ldc.i4.0
0x113c7a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x113c7f  ldarg.0
0x113c80  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal0
0x113c85  ldc.i4.1
0x113c86  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x113c8b  ldarg.0
0x113c8c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal0
0x113c91  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<item>5__35
0x113c96  ldarg.0
0x113c97  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<item>5__35
0x113c9c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x113ca1  ldarg.0
0x113ca2  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x113ca7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal1
0x113cac  ldarg.0
0x113cad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal1
0x113cb2  ldstr    aListname// "listName"
0x113cb7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x113cbc  ldarg.0
0x113cbd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal1
0x113cc2  ldc.i4.0
0x113cc3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x113cc8  ldarg.0
0x113cc9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal1
0x113cce  ldtoken  [mscorlib]System.String
0x113cd3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x113cd8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x113cdd  ldarg.0
0x113cde  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal1
0x113ce3  ldc.i4.1
0x113ce4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x113ce9  ldarg.0
0x113cea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal1
0x113cef  ldc.i4.0
0x113cf0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x113cf5  ldarg.0
0x113cf6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal1
0x113cfb  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x113d00  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x113d05  ldarg.0
0x113d06  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal1
0x113d0b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x113d10  ldarg.0
0x113d11  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<item>5__35
0x113d16  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x113d1b  ldarg.0
0x113d1c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x113d21  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal2
0x113d26  ldarg.0
0x113d27  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal2
0x113d2c  ldstr    aItemdata// "itemData"
0x113d31  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x113d36  ldarg.0
0x113d37  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal2
0x113d3c  ldc.i4.0
0x113d3d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x113d42  ldarg.0
0x113d43  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal2
0x113d48  ldtoken  [mscorlib]System.String
0x113d4d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x113d52  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x113d57  ldarg.0
0x113d58  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal2
0x113d5d  ldc.i4.1
0x113d5e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x113d63  ldarg.0
0x113d64  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal2
0x113d69  ldc.i4.0
0x113d6a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x113d6f  ldarg.0
0x113d70  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal2
0x113d75  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x113d7a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x113d7f  ldarg.0
0x113d80  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal2
0x113d85  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x113d8a  ldarg.0
0x113d8b  ldarg.0
0x113d8c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<item>5__35
0x113d91  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>2__current
0x113d96  ldarg.0
0x113d97  ldc.i4.3
0x113d98  stfld    int32 <GetMethods>d__33::<>1__state
0x113d9d  ldc.i4.1
0x113d9e  stloc.0
0x113d9f  leave    loc_1159A2
0x113da4  ldarg.0
0x113da5  ldc.i4.m1
0x113da6  stfld    int32 <GetMethods>d__33::<>1__state
0x113dab  ldarg.0
0x113dac  ldarg.0
0x113dad  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x113db2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal3
0x113db7  ldarg.0
0x113db8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal3
0x113dbd  ldstr    aDeletelistitem// "DeleteListItem"
0x113dc2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x113dc7  ldarg.0
0x113dc8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal3
0x113dcd  ldc.i4.1
0x113dce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x113dd3  ldarg.0
0x113dd4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal3
0x113dd9  ldc.i4.0
0x113dda  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x113ddf  ldarg.0
0x113de0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal3
0x113de5  ldc.i4   0xFFFFFFF
0x113dea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x113def  ldarg.0
0x113df0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal3
0x113df5  ldstr    aDeletelistitem// "DeleteListItem"
0x113dfa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x113dff  ldarg.0
0x113e00  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal3
0x113e05  ldc.i4.0
0x113e06  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x113e0b  ldarg.0
0x113e0c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal3
0x113e11  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult
0x113e16  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x113e1b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x113e20  ldarg.0
0x113e21  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal3
0x113e26  ldc.i4.4
0x113e27  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x113e2c  ldarg.0
0x113e2d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal3
0x113e32  ldc.i4.0
0x113e33  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x113e38  ldarg.0
0x113e39  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal3
0x113e3e  ldc.i4.0
0x113e3f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x113e44  ldarg.0
0x113e45  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal3
0x113e4a  ldc.i4.0
0x113e4b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x113e50  ldarg.0
0x113e51  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal3
0x113e56  ldc.i4.1
0x113e57  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x113e5c  ldarg.0
0x113e5d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<>g__initLocal3
0x113e62  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<item>5__35
0x113e67  ldarg.0
0x113e68  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<item>5__35
0x113e6d  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x113e72  ldarg.0
0x113e73  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x113e78  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal4
0x113e7d  ldarg.0
0x113e7e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal4
0x113e83  ldstr    aListname// "listName"
0x113e88  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x113e8d  ldarg.0
0x113e8e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal4
0x113e93  ldc.i4.0
0x113e94  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x113e99  ldarg.0
0x113e9a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal4
0x113e9f  ldtoken  [mscorlib]System.String
0x113ea4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x113ea9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x113eae  ldarg.0
0x113eaf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal4
0x113eb4  ldc.i4.1
0x113eb5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x113eba  ldarg.0
0x113ebb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal4
0x113ec0  ldc.i4.0
0x113ec1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x113ec6  ldarg.0
0x113ec7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal4
0x113ecc  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x113ed1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x113ed6  ldarg.0
0x113ed7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal4
0x113edc  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x113ee1  ldarg.0
0x113ee2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__33::<item>5__35
0x113ee7  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x113eec  ldarg.0
0x113eed  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x113ef2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal5
0x113ef7  ldarg.0
0x113ef8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal5
0x113efd  ldstr    aItemid// "itemId"
0x113f02  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x113f07  ldarg.0
0x113f08  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal5
0x113f0d  ldc.i4.0
0x113f0e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x113f13  ldarg.0
0x113f14  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal5
0x113f19  ldtoken  [mscorlib]System.String
0x113f1e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x113f23  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x113f28  ldarg.0
0x113f29  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__33::<>g__initLocal5
0x113f2e  ldc.i4.1
  ... truncated ...
```
