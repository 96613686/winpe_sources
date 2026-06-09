# Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::InvokeMethod

- ea: `0x42a60`
- end: `0x42b1f`
- name: `Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::InvokeMethod`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x42a20`
- `0x42a30`
- `0x42a50`
- `0x42a60`

## string_xrefs

- `0x42aa2`: `Update`
- `0x42ade`: `Update`
- `0x42aaf`: `DeleteObject`
- `0x42afa`: `DeleteObject`
- `0x42a95`: `RestUpdate`
- `0x42ac2`: `RestUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x42a60  ldarg.s  4
0x42a62  brtrue.s loc_42A6F
0x42a64  ldstr    aProxycontext// "proxyContext"
0x42a69  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x42a6e  throw
0x42a6f  ldarg.1
0x42a70  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType
0x42a75  stloc.0
0x42a76  ldloc.0
0x42a77  brtrue.s loc_42A84
0x42a79  ldstr    aTarget// "target"
0x42a7e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x42a83  throw
0x42a84  ldarg.0
0x42a85  ldarg.2
0x42a86  ldarg.s  4
0x42a88  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42a8d  starg.s  2
0x42a8f  ldarg.2
0x42a90  dup
0x42a91  stloc.1
0x42a92  brfalse.s loc_42B11
0x42a94  ldloc.1
0x42a95  ldstr    aRestupdate// "RestUpdate"
0x42a9a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x42a9f  brtrue.s loc_42ABD
0x42aa1  ldloc.1
0x42aa2  ldstr    aUpdate// "Update"
0x42aa7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x42aac  brtrue.s loc_42AD9
0x42aae  ldloc.1
0x42aaf  ldstr    aDeleteobject// "DeleteObject"
0x42ab4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x42ab9  brtrue.s loc_42AF5
0x42abb  br.s     loc_42B11
0x42abd  ldarg.s  5
0x42abf  ldc.i4.1
0x42ac0  stind.i1
0x42ac1  ldarg.0
0x42ac2  ldstr    aRestupdate// "RestUpdate"
0x42ac7  ldarg.s  4
0x42ac9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42ace  ldloc.0
0x42acf  ldarg.3
0x42ad0  ldarg.s  4
0x42ad2  call     void Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::RestUpdate_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x42ad7  ldnull
0x42ad8  ret
0x42ad9  ldarg.s  5
0x42adb  ldc.i4.1
0x42adc  stind.i1
0x42add  ldarg.0
0x42ade  ldstr    aUpdate// "Update"
0x42ae3  ldarg.s  4
0x42ae5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42aea  ldloc.0
0x42aeb  ldarg.3
0x42aec  ldarg.s  4
0x42aee  call     void Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::Update_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x42af3  ldnull
0x42af4  ret
0x42af5  ldarg.s  5
0x42af7  ldc.i4.1
0x42af8  stind.i1
0x42af9  ldarg.0
0x42afa  ldstr    aDeleteobject// "DeleteObject"
0x42aff  ldarg.s  4
0x42b01  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42b06  ldloc.0
0x42b07  ldarg.3
0x42b08  ldarg.s  4
0x42b0a  call     void Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::DeleteObject_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x42b0f  ldnull
0x42b10  ret
0x42b11  ldarg.0
0x42b12  ldarg.1
0x42b13  ldarg.2
0x42b14  ldarg.3
0x42b15  ldarg.s  4
0x42b17  ldarg.s  5
0x42b19  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x42b1e  ret
```
