# Microsoft.SharePoint.ServerStub.WebParts.SPWebPartDefinitionServerStub::InvokeMethod_0

- ea: `0xa4ef0`
- end: `0xa5007`
- name: `Microsoft.SharePoint.ServerStub.WebParts.SPWebPartDefinitionServerStub::InvokeMethod_0`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0xa4e80`
- `0xa4e90`
- `0xa4ea0`
- `0xa4eb0`
- `0xa4ec0`
- `0xa4ef0`

## string_xrefs

- `0xa4f42`: `OpenWebPart`
- `0xa4faa`: `OpenWebPart`
- `0xa4f4f`: `DeleteWebPart`
- `0xa4fc6`: `DeleteWebPart`
- `0xa4f5c`: `MoveWebPartTo`
- `0xa4fe2`: `MoveWebPartTo`

## pseudocode

```c

```

## disassembly

```asm
0xa4ef0  ldarg.s  4
0xa4ef2  brtrue.s loc_A4EFF
0xa4ef4  ldstr    aProxycontext// "proxyContext"
0xa4ef9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa4efe  throw
0xa4eff  ldarg.1
0xa4f00  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.WebPartPages.SPWebPartDefinition
0xa4f05  stloc.0
0xa4f06  ldloc.0
0xa4f07  brtrue.s loc_A4F14
0xa4f09  ldstr    aTarget// "target"
0xa4f0e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa4f13  throw
0xa4f14  ldarg.0
0xa4f15  ldarg.2
0xa4f16  ldarg.s  4
0xa4f18  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa4f1d  starg.s  2
0xa4f1f  ldarg.2
0xa4f20  dup
0xa4f21  stloc.1
0xa4f22  brfalse  loc_A4FF9
0xa4f27  ldloc.1
0xa4f28  ldstr    aSavewebpartcha// "SaveWebPartChanges"
0xa4f2d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4f32  brtrue.s loc_A4F6D
0xa4f34  ldloc.1
0xa4f35  ldstr    aClosewebpart// "CloseWebPart"
0xa4f3a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4f3f  brtrue.s loc_A4F89
0xa4f41  ldloc.1
0xa4f42  ldstr    aOpenwebpart// "OpenWebPart"
0xa4f47  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4f4c  brtrue.s loc_A4FA5
0xa4f4e  ldloc.1
0xa4f4f  ldstr    aDeletewebpart// "DeleteWebPart"
0xa4f54  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4f59  brtrue.s loc_A4FC1
0xa4f5b  ldloc.1
0xa4f5c  ldstr    aMovewebpartto// "MoveWebPartTo"
0xa4f61  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4f66  brtrue.s loc_A4FDD
0xa4f68  br       loc_A4FF9
0xa4f6d  ldarg.s  5
0xa4f6f  ldc.i4.1
0xa4f70  stind.i1
0xa4f71  ldarg.0
0xa4f72  ldstr    aSavewebpartcha// "SaveWebPartChanges"
0xa4f77  ldarg.s  4
0xa4f79  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa4f7e  ldloc.0
0xa4f7f  ldarg.3
0xa4f80  ldarg.s  4
0xa4f82  call     void Microsoft.SharePoint.ServerStub.WebParts.SPWebPartDefinitionServerStub::SaveWebPartChanges_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.WebPartPages.SPWebPartDefinition target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa4f87  ldnull
0xa4f88  ret
0xa4f89  ldarg.s  5
0xa4f8b  ldc.i4.1
0xa4f8c  stind.i1
0xa4f8d  ldarg.0
0xa4f8e  ldstr    aClosewebpart// "CloseWebPart"
0xa4f93  ldarg.s  4
0xa4f95  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa4f9a  ldloc.0
0xa4f9b  ldarg.3
0xa4f9c  ldarg.s  4
0xa4f9e  call     void Microsoft.SharePoint.ServerStub.WebParts.SPWebPartDefinitionServerStub::CloseWebPart_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.WebPartPages.SPWebPartDefinition target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa4fa3  ldnull
0xa4fa4  ret
0xa4fa5  ldarg.s  5
0xa4fa7  ldc.i4.1
0xa4fa8  stind.i1
0xa4fa9  ldarg.0
0xa4faa  ldstr    aOpenwebpart// "OpenWebPart"
0xa4faf  ldarg.s  4
0xa4fb1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa4fb6  ldloc.0
0xa4fb7  ldarg.3
0xa4fb8  ldarg.s  4
0xa4fba  call     void Microsoft.SharePoint.ServerStub.WebParts.SPWebPartDefinitionServerStub::OpenWebPart_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.WebPartPages.SPWebPartDefinition target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa4fbf  ldnull
0xa4fc0  ret
0xa4fc1  ldarg.s  5
0xa4fc3  ldc.i4.1
0xa4fc4  stind.i1
0xa4fc5  ldarg.0
0xa4fc6  ldstr    aDeletewebpart// "DeleteWebPart"
0xa4fcb  ldarg.s  4
0xa4fcd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa4fd2  ldloc.0
0xa4fd3  ldarg.3
0xa4fd4  ldarg.s  4
0xa4fd6  call     void Microsoft.SharePoint.ServerStub.WebParts.SPWebPartDefinitionServerStub::DeleteWebPart_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.WebPartPages.SPWebPartDefinition target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa4fdb  ldnull
0xa4fdc  ret
0xa4fdd  ldarg.s  5
0xa4fdf  ldc.i4.1
0xa4fe0  stind.i1
0xa4fe1  ldarg.0
0xa4fe2  ldstr    aMovewebpartto// "MoveWebPartTo"
0xa4fe7  ldarg.s  4
0xa4fe9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa4fee  ldloc.0
0xa4fef  ldarg.3
0xa4ff0  ldarg.s  4
0xa4ff2  call     void Microsoft.SharePoint.ServerStub.WebParts.SPWebPartDefinitionServerStub::MoveWebPartTo_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.WebPartPages.SPWebPartDefinition target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa4ff7  ldnull
0xa4ff8  ret
0xa4ff9  ldarg.0
0xa4ffa  ldarg.1
0xa4ffb  ldarg.2
0xa4ffc  ldarg.3
0xa4ffd  ldarg.s  4
0xa4fff  ldarg.s  5
0xa5001  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0xa5006  ret
```
