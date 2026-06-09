# <GetMethods>d__25::MoveNext

- ea: `0xc61e0`
- end: `0xc7921`
- name: `<GetMethods>d__25::MoveNext`
- size: `5953`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0xb740`
- `0xc61e0`
- `0xc7950`
- `0xc79b0`

## string_xrefs

- `0xc639e`: `copyRoleAssignments`
- `0xc7446`: `Update`
- `0xc747e`: `Update`
- `0xc64a9`: `DeleteObject`
- `0xc781d`: `bNewDocumentUpdate`
- `0xc7897`: `checkInComment`
- `0xc64e1`: `Delete`
- `0xc7602`: `UpdateWithFieldValues`
- `0xc7637`: `UpdateWithFieldValues`
- `0xc7368`: `SystemUpdate`
- `0xc7524`: `UpdateOverwriteVersion`
- `0xc755c`: `UpdateOverwriteVersion`
- `0xc703e`: `SetCommentsDisabled`
- `0xc7076`: `SetCommentsDisabled`
- `0xc76dd`: `ValidateUpdateListItem`
- `0xc73a0`: `SystemUpdate_Client`
- `0xc7715`: `ValidateUpdateListItem_Client`

## pseudocode

```c

```

## disassembly

```asm
0xc61e0  ldarg.0
0xc61e1  ldfld    int32 <GetMethods>d__25::<>1__state
0xc61e6  stloc.1
0xc61e7  ldloc.1
0xc61e8  switch   loc_C6242, loc_C7914, loc_C62AC, loc_C6490, loc_C656D, loc_C66C4, loc_C6817, loc_C696E, loc_C6AC5, loc_C6C97, loc_C6E69, loc_C6F47, loc_C7025, loc_C717D, loc_C734F, loc_C742D, loc_C750B, loc_C75E9, loc_C76C4, loc_C790D
0xc623d  br       loc_C7914
0xc6242  ldarg.0
0xc6243  ldc.i4.m1
0xc6244  stfld    int32 <GetMethods>d__25::<>1__state
0xc6249  ldarg.0
0xc624a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__25::proxyContext
0xc624f  brtrue.s loc_C625C
0xc6251  ldstr    aProxycontext// "proxyContext"
0xc6256  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xc625b  throw
0xc625c  ldarg.0
0xc625d  ldarg.0
0xc625e  ldfld    class Microsoft.SharePoint.ServerStub.SPListItemServerStub <GetMethods>d__25::<>4__this
0xc6263  ldarg.0
0xc6264  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__25::proxyContext
0xc6269  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPListItemServerStub::<>n__FabricatedMethod2a(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0xc626e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0xc6273  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__25::<>7__wrap28
0xc6278  ldarg.0
0xc6279  ldc.i4.1
0xc627a  stfld    int32 <GetMethods>d__25::<>1__state
0xc627f  br.s     loc_C62B3
0xc6281  ldarg.0
0xc6282  ldarg.0
0xc6283  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__25::<>7__wrap28
0xc6288  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0xc628d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<itemBase>5__26
0xc6292  ldarg.0
0xc6293  ldarg.0
0xc6294  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<itemBase>5__26
0xc6299  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>2__current
0xc629e  ldarg.0
0xc629f  ldc.i4.2
0xc62a0  stfld    int32 <GetMethods>d__25::<>1__state
0xc62a5  ldc.i4.1
0xc62a6  stloc.0
0xc62a7  leave    loc_C791F
0xc62ac  ldarg.0
0xc62ad  ldc.i4.1
0xc62ae  stfld    int32 <GetMethods>d__25::<>1__state
0xc62b3  ldarg.0
0xc62b4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__25::<>7__wrap28
0xc62b9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc62be  brtrue.s loc_C6281
0xc62c0  ldarg.0
0xc62c1  call     instance void <GetMethods>d__25::<>m__Finally29()
0xc62c6  ldarg.0
0xc62c7  ldarg.0
0xc62c8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xc62cd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal4
0xc62d2  ldarg.0
0xc62d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal4
0xc62d8  ldstr    aBreakroleinher// "BreakRoleInheritance"
0xc62dd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xc62e2  ldarg.0
0xc62e3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal4
0xc62e8  ldc.i4.0
0xc62e9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xc62ee  ldarg.0
0xc62ef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal4
0xc62f4  ldc.i4.0
0xc62f5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xc62fa  ldarg.0
0xc62fb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal4
0xc6300  ldc.i4   0xFFFFFFF
0xc6305  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xc630a  ldarg.0
0xc630b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal4
0xc6310  ldstr    aBreakroleinher// "BreakRoleInheritance"
0xc6315  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xc631a  ldarg.0
0xc631b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal4
0xc6320  ldc.i4.0
0xc6321  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xc6326  ldarg.0
0xc6327  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal4
0xc632c  ldtoken  [mscorlib]System.Void
0xc6331  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc6336  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xc633b  ldarg.0
0xc633c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal4
0xc6341  ldc.i4.0
0xc6342  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xc6347  ldarg.0
0xc6348  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal4
0xc634d  ldc.i4.0
0xc634e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xc6353  ldarg.0
0xc6354  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal4
0xc6359  ldc.i4.0
0xc635a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0xc635f  ldarg.0
0xc6360  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal4
0xc6365  ldc.i4.0
0xc6366  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xc636b  ldarg.0
0xc636c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal4
0xc6371  ldc.i4.0
0xc6372  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0xc6377  ldarg.0
0xc6378  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal4
0xc637d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<item>5__27
0xc6382  ldarg.0
0xc6383  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<item>5__27
0xc6388  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xc638d  ldarg.0
0xc638e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xc6393  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__25::<>g__initLocal5
0xc6398  ldarg.0
0xc6399  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__25::<>g__initLocal5
0xc639e  ldstr    aCopyroleassign// "copyRoleAssignments"
0xc63a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xc63a8  ldarg.0
0xc63a9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__25::<>g__initLocal5
0xc63ae  ldc.i4.0
0xc63af  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xc63b4  ldarg.0
0xc63b5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__25::<>g__initLocal5
0xc63ba  ldtoken  [mscorlib]System.Boolean
0xc63bf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc63c4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xc63c9  ldarg.0
0xc63ca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__25::<>g__initLocal5
0xc63cf  ldc.i4.1
0xc63d0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xc63d5  ldarg.0
0xc63d6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__25::<>g__initLocal5
0xc63db  ldc.i4.0
0xc63dc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0xc63e1  ldarg.0
0xc63e2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__25::<>g__initLocal5
0xc63e7  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xc63ec  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0xc63f1  ldarg.0
0xc63f2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__25::<>g__initLocal5
0xc63f7  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0xc63fc  ldarg.0
0xc63fd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<item>5__27
0xc6402  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xc6407  ldarg.0
0xc6408  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xc640d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__25::<>g__initLocal6
0xc6412  ldarg.0
0xc6413  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__25::<>g__initLocal6
0xc6418  ldstr    aClearsubscopes// "clearSubscopes"
0xc641d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xc6422  ldarg.0
0xc6423  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__25::<>g__initLocal6
0xc6428  ldc.i4.0
0xc6429  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xc642e  ldarg.0
0xc642f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__25::<>g__initLocal6
0xc6434  ldtoken  [mscorlib]System.Boolean
0xc6439  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc643e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xc6443  ldarg.0
0xc6444  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__25::<>g__initLocal6
0xc6449  ldc.i4.1
0xc644a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xc644f  ldarg.0
0xc6450  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__25::<>g__initLocal6
0xc6455  ldc.i4.0
0xc6456  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0xc645b  ldarg.0
0xc645c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__25::<>g__initLocal6
0xc6461  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xc6466  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0xc646b  ldarg.0
0xc646c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__25::<>g__initLocal6
0xc6471  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0xc6476  ldarg.0
0xc6477  ldarg.0
0xc6478  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<item>5__27
0xc647d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>2__current
0xc6482  ldarg.0
0xc6483  ldc.i4.3
0xc6484  stfld    int32 <GetMethods>d__25::<>1__state
0xc6489  ldc.i4.1
0xc648a  stloc.0
0xc648b  leave    loc_C791F
0xc6490  ldarg.0
0xc6491  ldc.i4.m1
0xc6492  stfld    int32 <GetMethods>d__25::<>1__state
0xc6497  ldarg.0
0xc6498  ldarg.0
0xc6499  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xc649e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal7
0xc64a3  ldarg.0
0xc64a4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal7
0xc64a9  ldstr    aDeleteobject// "DeleteObject"
0xc64ae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xc64b3  ldarg.0
0xc64b4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal7
0xc64b9  ldc.i4.0
0xc64ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xc64bf  ldarg.0
0xc64c0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal7
0xc64c5  ldc.i4.0
0xc64c6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xc64cb  ldarg.0
0xc64cc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal7
0xc64d1  ldc.i4   0xFFFFFFF
0xc64d6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xc64db  ldarg.0
0xc64dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal7
0xc64e1  ldstr    aDelete// "Delete"
0xc64e6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xc64eb  ldarg.0
0xc64ec  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal7
0xc64f1  ldc.i4.0
0xc64f2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xc64f7  ldarg.0
0xc64f8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal7
0xc64fd  ldtoken  [mscorlib]System.Void
0xc6502  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc6507  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xc650c  ldarg.0
0xc650d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal7
0xc6512  ldc.i4.0
0xc6513  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xc6518  ldarg.0
0xc6519  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal7
0xc651e  ldc.i4.0
0xc651f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xc6524  ldarg.0
0xc6525  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal7
0xc652a  ldc.i4.0
0xc652b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0xc6530  ldarg.0
0xc6531  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal7
0xc6536  ldc.i4.0
0xc6537  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xc653c  ldarg.0
0xc653d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal7
0xc6542  ldc.i4.0
0xc6543  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0xc6548  ldarg.0
0xc6549  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal7
0xc654e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<item>5__27
0xc6553  ldarg.0
0xc6554  ldarg.0
0xc6555  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<item>5__27
0xc655a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>2__current
0xc655f  ldarg.0
0xc6560  ldc.i4.4
0xc6561  stfld    int32 <GetMethods>d__25::<>1__state
0xc6566  ldc.i4.1
0xc6567  stloc.0
0xc6568  leave    loc_C791F
0xc656d  ldarg.0
0xc656e  ldc.i4.m1
0xc656f  stfld    int32 <GetMethods>d__25::<>1__state
0xc6574  ldarg.0
0xc6575  ldarg.0
0xc6576  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xc657b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal8
0xc6580  ldarg.0
0xc6581  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal8
0xc6586  ldstr    aGetchanges// "GetChanges"
0xc658b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xc6590  ldarg.0
0xc6591  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal8
0xc6596  ldc.i4.0
0xc6597  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xc659c  ldarg.0
0xc659d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal8
0xc65a2  ldc.i4.0
0xc65a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xc65a8  ldarg.0
0xc65a9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal8
0xc65ae  ldc.i4   0xFFFFFFF
0xc65b3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xc65b8  ldarg.0
0xc65b9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal8
0xc65be  ldstr    aGetchanges// "GetChanges"
0xc65c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xc65c8  ldarg.0
0xc65c9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal8
0xc65ce  ldc.i4.0
0xc65cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xc65d4  ldarg.0
0xc65d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal8
0xc65da  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeCollection
0xc65df  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc65e4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xc65e9  ldarg.0
0xc65ea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal8
0xc65ef  ldc.i4.5
0xc65f0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xc65f5  ldarg.0
0xc65f6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal8
0xc65fb  ldc.i4.0
0xc65fc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xc6601  ldarg.0
0xc6602  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__25::<>g__initLocal8
  ... truncated ...
```
