# <GetMethods>d__f::MoveNext_0

- ea: `0x1388d0`
- end: `0x139444`
- name: `<GetMethods>d__f::MoveNext_0`
- size: `2932`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callees

- `0x5f550`
- `0x1388d0`
- `0x139470`
- `0x1394d0`

## string_xrefs

- `0x13936e`: `Update`
- `0x1393a6`: `Update`
- `0x138c56`: `DeleteObject`
- `0x138c8e`: `Delete`
- `0x138fe1`: `MoveTo`
- `0x139170`: `MoveTo`
- `0x139138`: `MoveToUsingPath`
- `0x1391fe`: `newPath`
- `0x138aff`: `AddSubFolderUsingPath`
- `0x138bc5`: `leafPath`
- `0x139019`: `MoveTo_Client`

## pseudocode

```c

```

## disassembly

```asm
0x1388d0  ldarg.0
0x1388d1  ldfld    int32 <GetMethods>d__f::<>1__state
0x1388d6  stloc.1
0x1388d7  ldloc.1
0x1388d8  switch   loc_138912, loc_139437, loc_13897C, loc_138AE6, loc_138C3D, loc_138D1A, loc_138E71, loc_138FC8, loc_13911F, loc_139277, loc_139355, loc_139430
0x13890d  br       loc_139437
0x138912  ldarg.0
0x138913  ldc.i4.m1
0x138914  stfld    int32 <GetMethods>d__f::<>1__state
0x138919  ldarg.0
0x13891a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__f::proxyContext
0x13891f  brtrue.s loc_13892C
0x138921  ldstr    aProxycontext// "proxyContext"
0x138926  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13892b  throw
0x13892c  ldarg.0
0x13892d  ldarg.0
0x13892e  ldfld    class Microsoft.SharePoint.ServerStub.SPFolderServerStub <GetMethods>d__f::<>4__this
0x138933  ldarg.0
0x138934  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__f::proxyContext
0x138939  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPFolderServerStub::<>n__FabricatedMethod14(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x13893e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x138943  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__f::<>7__wrap12
0x138948  ldarg.0
0x138949  ldc.i4.1
0x13894a  stfld    int32 <GetMethods>d__f::<>1__state
0x13894f  br.s     loc_138983
0x138951  ldarg.0
0x138952  ldarg.0
0x138953  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__f::<>7__wrap12
0x138958  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x13895d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<itemBase>5__10
0x138962  ldarg.0
0x138963  ldarg.0
0x138964  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<itemBase>5__10
0x138969  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>2__current
0x13896e  ldarg.0
0x13896f  ldc.i4.2
0x138970  stfld    int32 <GetMethods>d__f::<>1__state
0x138975  ldc.i4.1
0x138976  stloc.0
0x138977  leave    loc_139442
0x13897c  ldarg.0
0x13897d  ldc.i4.1
0x13897e  stfld    int32 <GetMethods>d__f::<>1__state
0x138983  ldarg.0
0x138984  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__f::<>7__wrap12
0x138989  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13898e  brtrue.s loc_138951
0x138990  ldarg.0
0x138991  call     instance void <GetMethods>d__f::<>m__Finally13()
0x138996  ldarg.0
0x138997  ldarg.0
0x138998  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x13899d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1389a2  ldarg.0
0x1389a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1389a8  ldstr    aAddsubfolder// "AddSubFolder"
0x1389ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1389b2  ldarg.0
0x1389b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1389b8  ldc.i4.0
0x1389b9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1389be  ldarg.0
0x1389bf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1389c4  ldc.i4.0
0x1389c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1389ca  ldarg.0
0x1389cb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1389d0  ldc.i4   0xFFFFFFF
0x1389d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1389da  ldarg.0
0x1389db  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1389e0  ldstr    aAddsubfolder// "AddSubFolder"
0x1389e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1389ea  ldarg.0
0x1389eb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1389f0  ldc.i4.0
0x1389f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1389f6  ldarg.0
0x1389f7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1389fc  ldtoken  [mscorlib]System.Void
0x138a01  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x138a06  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x138a0b  ldarg.0
0x138a0c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x138a11  ldc.i4.0
0x138a12  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x138a17  ldarg.0
0x138a18  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x138a1d  ldc.i4.0
0x138a1e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x138a23  ldarg.0
0x138a24  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x138a29  ldc.i4.0
0x138a2a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x138a2f  ldarg.0
0x138a30  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x138a35  ldc.i4.0
0x138a36  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x138a3b  ldarg.0
0x138a3c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x138a41  ldc.i4.0
0x138a42  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x138a47  ldarg.0
0x138a48  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x138a4d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x138a52  ldarg.0
0x138a53  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x138a58  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x138a5d  ldarg.0
0x138a5e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x138a63  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x138a68  ldarg.0
0x138a69  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x138a6e  ldstr    aLeafname// "leafName"
0x138a73  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x138a78  ldarg.0
0x138a79  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x138a7e  ldc.i4.0
0x138a7f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x138a84  ldarg.0
0x138a85  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x138a8a  ldtoken  [mscorlib]System.String
0x138a8f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x138a94  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x138a99  ldarg.0
0x138a9a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x138a9f  ldc.i4.1
0x138aa0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x138aa5  ldarg.0
0x138aa6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x138aab  ldc.i4.0
0x138aac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x138ab1  ldarg.0
0x138ab2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x138ab7  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x138abc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x138ac1  ldarg.0
0x138ac2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x138ac7  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x138acc  ldarg.0
0x138acd  ldarg.0
0x138ace  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x138ad3  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>2__current
0x138ad8  ldarg.0
0x138ad9  ldc.i4.3
0x138ada  stfld    int32 <GetMethods>d__f::<>1__state
0x138adf  ldc.i4.1
0x138ae0  stloc.0
0x138ae1  leave    loc_139442
0x138ae6  ldarg.0
0x138ae7  ldc.i4.m1
0x138ae8  stfld    int32 <GetMethods>d__f::<>1__state
0x138aed  ldarg.0
0x138aee  ldarg.0
0x138aef  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x138af4  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x138af9  ldarg.0
0x138afa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x138aff  ldstr    aAddsubfolderus// "AddSubFolderUsingPath"
0x138b04  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x138b09  ldarg.0
0x138b0a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x138b0f  ldc.i4.0
0x138b10  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x138b15  ldarg.0
0x138b16  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x138b1b  ldc.i4.0
0x138b1c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x138b21  ldarg.0
0x138b22  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x138b27  ldc.i4   0xFFFFFFF
0x138b2c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x138b31  ldarg.0
0x138b32  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x138b37  ldstr    aAddsubfolder// "AddSubFolder"
0x138b3c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x138b41  ldarg.0
0x138b42  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x138b47  ldc.i4.0
0x138b48  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x138b4d  ldarg.0
0x138b4e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x138b53  ldtoken  [mscorlib]System.Void
0x138b58  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x138b5d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x138b62  ldarg.0
0x138b63  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x138b68  ldc.i4.0
0x138b69  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x138b6e  ldarg.0
0x138b6f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x138b74  ldc.i4.0
0x138b75  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x138b7a  ldarg.0
0x138b7b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x138b80  ldc.i4.0
0x138b81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x138b86  ldarg.0
0x138b87  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x138b8c  ldc.i4.0
0x138b8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x138b92  ldarg.0
0x138b93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x138b98  ldc.i4.1
0x138b99  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x138b9e  ldarg.0
0x138b9f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x138ba4  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x138ba9  ldarg.0
0x138baa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x138baf  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x138bb4  ldarg.0
0x138bb5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x138bba  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x138bbf  ldarg.0
0x138bc0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x138bc5  ldstr    aLeafpath// "leafPath"
0x138bca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x138bcf  ldarg.0
0x138bd0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x138bd5  ldc.i4.1
0x138bd6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x138bdb  ldarg.0
0x138bdc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x138be1  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath
0x138be6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x138beb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x138bf0  ldarg.0
0x138bf1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x138bf6  ldc.i4.2
0x138bf7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x138bfc  ldarg.0
0x138bfd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x138c02  ldc.i4.0
0x138c03  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x138c08  ldarg.0
0x138c09  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x138c0e  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x138c13  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x138c18  ldarg.0
0x138c19  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x138c1e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x138c23  ldarg.0
0x138c24  ldarg.0
0x138c25  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x138c2a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>2__current
0x138c2f  ldarg.0
0x138c30  ldc.i4.4
0x138c31  stfld    int32 <GetMethods>d__f::<>1__state
0x138c36  ldc.i4.1
0x138c37  stloc.0
0x138c38  leave    loc_139442
0x138c3d  ldarg.0
0x138c3e  ldc.i4.m1
0x138c3f  stfld    int32 <GetMethods>d__f::<>1__state
0x138c44  ldarg.0
0x138c45  ldarg.0
0x138c46  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x138c4b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x138c50  ldarg.0
0x138c51  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x138c56  ldstr    aDeleteobject// "DeleteObject"
0x138c5b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x138c60  ldarg.0
0x138c61  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x138c66  ldc.i4.0
0x138c67  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x138c6c  ldarg.0
0x138c6d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x138c72  ldc.i4.0
0x138c73  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x138c78  ldarg.0
0x138c79  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x138c7e  ldc.i4   0xFFFFFFF
0x138c83  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x138c88  ldarg.0
0x138c89  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x138c8e  ldstr    aDelete// "Delete"
0x138c93  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x138c98  ldarg.0
0x138c99  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x138c9e  ldc.i4.0
0x138c9f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x138ca4  ldarg.0
0x138ca5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x138caa  ldtoken  [mscorlib]System.Void
0x138caf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x138cb4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x138cb9  ldarg.0
0x138cba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x138cbf  ldc.i4.0
0x138cc0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x138cc5  ldarg.0
0x138cc6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x138ccb  ldc.i4.0
0x138ccc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x138cd1  ldarg.0
0x138cd2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
  ... truncated ...
```
