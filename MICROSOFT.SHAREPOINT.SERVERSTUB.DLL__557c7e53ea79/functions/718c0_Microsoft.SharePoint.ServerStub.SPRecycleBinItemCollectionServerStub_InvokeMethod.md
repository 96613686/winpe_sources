# Microsoft.SharePoint.ServerStub.SPRecycleBinItemCollectionServerStub::InvokeMethod

- ea: `0x718c0`
- end: `0x719d6`
- name: `Microsoft.SharePoint.ServerStub.SPRecycleBinItemCollectionServerStub::InvokeMethod`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x71860`
- `0x71880`
- `0x71890`
- `0x718a0`
- `0x718b0`
- `0x718c0`

## string_xrefs

- `0x71912`: `DeleteAll`
- `0x71979`: `DeleteAll`
- `0x71905`: `MoveAllToSecondStage`
- `0x7195d`: `MoveAllToSecondStage`
- `0x7192c`: `DeleteAllSecondStageItems`
- `0x719b1`: `DeleteAllSecondStageItems`

## pseudocode

```c

```

## disassembly

```asm
0x718c0  ldarg.s  4
0x718c2  brtrue.s loc_718CF
0x718c4  ldstr    aProxycontext// "proxyContext"
0x718c9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x718ce  throw
0x718cf  ldarg.1
0x718d0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemCollection
0x718d5  stloc.0
0x718d6  ldloc.0
0x718d7  brtrue.s loc_718E4
0x718d9  ldstr    aTarget// "target"
0x718de  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x718e3  throw
0x718e4  ldarg.0
0x718e5  ldarg.2
0x718e6  ldarg.s  4
0x718e8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x718ed  starg.s  2
0x718ef  ldarg.2
0x718f0  dup
0x718f1  stloc.1
0x718f2  brfalse  loc_719C8
0x718f7  ldloc.1
0x718f8  ldstr    aGetbyid// "GetById"
0x718fd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x71902  brtrue.s loc_7193D
0x71904  ldloc.1
0x71905  ldstr    aMovealltosecon// "MoveAllToSecondStage"
0x7190a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7190f  brtrue.s loc_71958
0x71911  ldloc.1
0x71912  ldstr    aDeleteall// "DeleteAll"
0x71917  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7191c  brtrue.s loc_71974
0x7191e  ldloc.1
0x7191f  ldstr    aRestoreall// "RestoreAll"
0x71924  call     bool [mscorlib]System.String::op_Equality(string, string)
0x71929  brtrue.s loc_71990
0x7192b  ldloc.1
0x7192c  ldstr    aDeleteallsecon// "DeleteAllSecondStageItems"
0x71931  call     bool [mscorlib]System.String::op_Equality(string, string)
0x71936  brtrue.s loc_719AC
0x71938  br       loc_719C8
0x7193d  ldarg.s  5
0x7193f  ldc.i4.0
0x71940  stind.i1
0x71941  ldarg.0
0x71942  ldstr    aGetbyid// "GetById"
0x71947  ldarg.s  4
0x71949  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7194e  ldloc.0
0x7194f  ldarg.3
0x71950  ldarg.s  4
0x71952  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem Microsoft.SharePoint.ServerStub.SPRecycleBinItemCollectionServerStub::GetById_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x71957  ret
0x71958  ldarg.s  5
0x7195a  ldc.i4.1
0x7195b  stind.i1
0x7195c  ldarg.0
0x7195d  ldstr    aMovealltosecon// "MoveAllToSecondStage"
0x71962  ldarg.s  4
0x71964  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71969  ldloc.0
0x7196a  ldarg.3
0x7196b  ldarg.s  4
0x7196d  call     void Microsoft.SharePoint.ServerStub.SPRecycleBinItemCollectionServerStub::MoveAllToSecondStage_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x71972  ldnull
0x71973  ret
0x71974  ldarg.s  5
0x71976  ldc.i4.1
0x71977  stind.i1
0x71978  ldarg.0
0x71979  ldstr    aDeleteall// "DeleteAll"
0x7197e  ldarg.s  4
0x71980  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71985  ldloc.0
0x71986  ldarg.3
0x71987  ldarg.s  4
0x71989  call     void Microsoft.SharePoint.ServerStub.SPRecycleBinItemCollectionServerStub::DeleteAll_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7198e  ldnull
0x7198f  ret
0x71990  ldarg.s  5
0x71992  ldc.i4.1
0x71993  stind.i1
0x71994  ldarg.0
0x71995  ldstr    aRestoreall// "RestoreAll"
0x7199a  ldarg.s  4
0x7199c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x719a1  ldloc.0
0x719a2  ldarg.3
0x719a3  ldarg.s  4
0x719a5  call     void Microsoft.SharePoint.ServerStub.SPRecycleBinItemCollectionServerStub::RestoreAll_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x719aa  ldnull
0x719ab  ret
0x719ac  ldarg.s  5
0x719ae  ldc.i4.1
0x719af  stind.i1
0x719b0  ldarg.0
0x719b1  ldstr    aDeleteallsecon// "DeleteAllSecondStageItems"
0x719b6  ldarg.s  4
0x719b8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x719bd  ldloc.0
0x719be  ldarg.3
0x719bf  ldarg.s  4
0x719c1  call     void Microsoft.SharePoint.ServerStub.SPRecycleBinItemCollectionServerStub::DeleteAllSecondStageItems_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x719c6  ldnull
0x719c7  ret
0x719c8  ldarg.0
0x719c9  ldarg.1
0x719ca  ldarg.2
0x719cb  ldarg.3
0x719cc  ldarg.s  4
0x719ce  ldarg.s  5
0x719d0  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x719d5  ret
```
