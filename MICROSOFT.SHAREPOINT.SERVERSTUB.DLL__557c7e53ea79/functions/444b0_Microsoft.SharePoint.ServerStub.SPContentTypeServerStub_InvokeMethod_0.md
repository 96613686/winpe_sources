# Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::InvokeMethod_0

- ea: `0x444b0`
- end: `0x4456f`
- name: `Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::InvokeMethod_0`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x44470`
- `0x44480`
- `0x444a0`
- `0x444b0`

## string_xrefs

- `0x444f2`: `Update`
- `0x4452e`: `Update`
- `0x444ff`: `DeleteObject`
- `0x4454a`: `DeleteObject`
- `0x444e5`: `RestUpdate`
- `0x44512`: `RestUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x444b0  ldarg.s  4
0x444b2  brtrue.s loc_444BF
0x444b4  ldstr    aProxycontext// "proxyContext"
0x444b9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x444be  throw
0x444bf  ldarg.1
0x444c0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType
0x444c5  stloc.0
0x444c6  ldloc.0
0x444c7  brtrue.s loc_444D4
0x444c9  ldstr    aTarget// "target"
0x444ce  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x444d3  throw
0x444d4  ldarg.0
0x444d5  ldarg.2
0x444d6  ldarg.s  4
0x444d8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x444dd  starg.s  2
0x444df  ldarg.2
0x444e0  dup
0x444e1  stloc.1
0x444e2  brfalse.s loc_44561
0x444e4  ldloc.1
0x444e5  ldstr    aRestupdate// "RestUpdate"
0x444ea  call     bool [mscorlib]System.String::op_Equality(string, string)
0x444ef  brtrue.s loc_4450D
0x444f1  ldloc.1
0x444f2  ldstr    aUpdate// "Update"
0x444f7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x444fc  brtrue.s loc_44529
0x444fe  ldloc.1
0x444ff  ldstr    aDeleteobject// "DeleteObject"
0x44504  call     bool [mscorlib]System.String::op_Equality(string, string)
0x44509  brtrue.s loc_44545
0x4450b  br.s     loc_44561
0x4450d  ldarg.s  5
0x4450f  ldc.i4.1
0x44510  stind.i1
0x44511  ldarg.0
0x44512  ldstr    aRestupdate// "RestUpdate"
0x44517  ldarg.s  4
0x44519  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4451e  ldloc.0
0x4451f  ldarg.3
0x44520  ldarg.s  4
0x44522  call     void Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::RestUpdate_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x44527  ldnull
0x44528  ret
0x44529  ldarg.s  5
0x4452b  ldc.i4.1
0x4452c  stind.i1
0x4452d  ldarg.0
0x4452e  ldstr    aUpdate// "Update"
0x44533  ldarg.s  4
0x44535  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4453a  ldloc.0
0x4453b  ldarg.3
0x4453c  ldarg.s  4
0x4453e  call     void Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::Update_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x44543  ldnull
0x44544  ret
0x44545  ldarg.s  5
0x44547  ldc.i4.1
0x44548  stind.i1
0x44549  ldarg.0
0x4454a  ldstr    aDeleteobject// "DeleteObject"
0x4454f  ldarg.s  4
0x44551  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x44556  ldloc.0
0x44557  ldarg.3
0x44558  ldarg.s  4
0x4455a  call     void Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::DeleteObject_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4455f  ldnull
0x44560  ret
0x44561  ldarg.0
0x44562  ldarg.1
0x44563  ldarg.2
0x44564  ldarg.3
0x44565  ldarg.s  4
0x44567  ldarg.s  5
0x44569  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x4456e  ret
```
