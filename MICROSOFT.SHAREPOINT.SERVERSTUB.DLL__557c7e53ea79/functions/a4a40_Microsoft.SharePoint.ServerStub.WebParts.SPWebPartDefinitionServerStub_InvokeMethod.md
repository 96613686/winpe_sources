# Microsoft.SharePoint.ServerStub.WebParts.SPWebPartDefinitionServerStub::InvokeMethod

- ea: `0xa4a40`
- end: `0xa4b57`
- name: `Microsoft.SharePoint.ServerStub.WebParts.SPWebPartDefinitionServerStub::InvokeMethod`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0xa49d0`
- `0xa49e0`
- `0xa49f0`
- `0xa4a00`
- `0xa4a10`
- `0xa4a40`

## string_xrefs

- `0xa4a92`: `OpenWebPart`
- `0xa4afa`: `OpenWebPart`
- `0xa4a9f`: `DeleteWebPart`
- `0xa4b16`: `DeleteWebPart`
- `0xa4aac`: `MoveWebPartTo`
- `0xa4b32`: `MoveWebPartTo`

## pseudocode

```c

```

## disassembly

```asm
0xa4a40  ldarg.s  4
0xa4a42  brtrue.s loc_A4A4F
0xa4a44  ldstr    aProxycontext// "proxyContext"
0xa4a49  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa4a4e  throw
0xa4a4f  ldarg.1
0xa4a50  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.WebPartPages.SPWebPartDefinition
0xa4a55  stloc.0
0xa4a56  ldloc.0
0xa4a57  brtrue.s loc_A4A64
0xa4a59  ldstr    aTarget// "target"
0xa4a5e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa4a63  throw
0xa4a64  ldarg.0
0xa4a65  ldarg.2
0xa4a66  ldarg.s  4
0xa4a68  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa4a6d  starg.s  2
0xa4a6f  ldarg.2
0xa4a70  dup
0xa4a71  stloc.1
0xa4a72  brfalse  loc_A4B49
0xa4a77  ldloc.1
0xa4a78  ldstr    aSavewebpartcha// "SaveWebPartChanges"
0xa4a7d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4a82  brtrue.s loc_A4ABD
0xa4a84  ldloc.1
0xa4a85  ldstr    aClosewebpart// "CloseWebPart"
0xa4a8a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4a8f  brtrue.s loc_A4AD9
0xa4a91  ldloc.1
0xa4a92  ldstr    aOpenwebpart// "OpenWebPart"
0xa4a97  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4a9c  brtrue.s loc_A4AF5
0xa4a9e  ldloc.1
0xa4a9f  ldstr    aDeletewebpart// "DeleteWebPart"
0xa4aa4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4aa9  brtrue.s loc_A4B11
0xa4aab  ldloc.1
0xa4aac  ldstr    aMovewebpartto// "MoveWebPartTo"
0xa4ab1  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4ab6  brtrue.s loc_A4B2D
0xa4ab8  br       loc_A4B49
0xa4abd  ldarg.s  5
0xa4abf  ldc.i4.1
0xa4ac0  stind.i1
0xa4ac1  ldarg.0
0xa4ac2  ldstr    aSavewebpartcha// "SaveWebPartChanges"
0xa4ac7  ldarg.s  4
0xa4ac9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa4ace  ldloc.0
0xa4acf  ldarg.3
0xa4ad0  ldarg.s  4
0xa4ad2  call     void Microsoft.SharePoint.ServerStub.WebParts.SPWebPartDefinitionServerStub::SaveWebPartChanges_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.WebPartPages.SPWebPartDefinition target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa4ad7  ldnull
0xa4ad8  ret
0xa4ad9  ldarg.s  5
0xa4adb  ldc.i4.1
0xa4adc  stind.i1
0xa4add  ldarg.0
0xa4ade  ldstr    aClosewebpart// "CloseWebPart"
0xa4ae3  ldarg.s  4
0xa4ae5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa4aea  ldloc.0
0xa4aeb  ldarg.3
0xa4aec  ldarg.s  4
0xa4aee  call     void Microsoft.SharePoint.ServerStub.WebParts.SPWebPartDefinitionServerStub::CloseWebPart_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.WebPartPages.SPWebPartDefinition target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa4af3  ldnull
0xa4af4  ret
0xa4af5  ldarg.s  5
0xa4af7  ldc.i4.1
0xa4af8  stind.i1
0xa4af9  ldarg.0
0xa4afa  ldstr    aOpenwebpart// "OpenWebPart"
0xa4aff  ldarg.s  4
0xa4b01  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa4b06  ldloc.0
0xa4b07  ldarg.3
0xa4b08  ldarg.s  4
0xa4b0a  call     void Microsoft.SharePoint.ServerStub.WebParts.SPWebPartDefinitionServerStub::OpenWebPart_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.WebPartPages.SPWebPartDefinition target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa4b0f  ldnull
0xa4b10  ret
0xa4b11  ldarg.s  5
0xa4b13  ldc.i4.1
0xa4b14  stind.i1
0xa4b15  ldarg.0
0xa4b16  ldstr    aDeletewebpart// "DeleteWebPart"
0xa4b1b  ldarg.s  4
0xa4b1d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa4b22  ldloc.0
0xa4b23  ldarg.3
0xa4b24  ldarg.s  4
0xa4b26  call     void Microsoft.SharePoint.ServerStub.WebParts.SPWebPartDefinitionServerStub::DeleteWebPart_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.WebPartPages.SPWebPartDefinition target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa4b2b  ldnull
0xa4b2c  ret
0xa4b2d  ldarg.s  5
0xa4b2f  ldc.i4.1
0xa4b30  stind.i1
0xa4b31  ldarg.0
0xa4b32  ldstr    aMovewebpartto// "MoveWebPartTo"
0xa4b37  ldarg.s  4
0xa4b39  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa4b3e  ldloc.0
0xa4b3f  ldarg.3
0xa4b40  ldarg.s  4
0xa4b42  call     void Microsoft.SharePoint.ServerStub.WebParts.SPWebPartDefinitionServerStub::MoveWebPartTo_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.WebPartPages.SPWebPartDefinition target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa4b47  ldnull
0xa4b48  ret
0xa4b49  ldarg.0
0xa4b4a  ldarg.1
0xa4b4b  ldarg.2
0xa4b4c  ldarg.3
0xa4b4d  ldarg.s  4
0xa4b4f  ldarg.s  5
0xa4b51  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0xa4b56  ret
```
