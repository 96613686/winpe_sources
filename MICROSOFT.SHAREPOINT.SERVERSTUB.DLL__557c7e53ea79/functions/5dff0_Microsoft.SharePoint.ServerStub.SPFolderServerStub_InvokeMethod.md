# Microsoft.SharePoint.ServerStub.SPFolderServerStub::InvokeMethod

- ea: `0x5dff0`
- end: `0x5e1f9`
- name: `Microsoft.SharePoint.ServerStub.SPFolderServerStub::InvokeMethod`
- size: `521`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x5df00`
- `0x5df20`
- `0x5df40`
- `0x5df50`
- `0x5df70`
- `0x5df90`
- `0x5dfb0`
- `0x5dfd0`
- `0x5dfe0`
- `0x5dff0`

## string_xrefs

- `0x5e050`: `Update`
- `0x5e128`: `Update`
- `0x5e08c`: `DeleteObject`
- `0x5e1b4`: `DeleteObject`
- `0x5e05c`: `MoveTo`
- `0x5e144`: `MoveTo`
- `0x5e068`: `MoveToUsingPath`
- `0x5e160`: `MoveToUsingPath`
- `0x5e080`: `AddSubFolderUsingPath`
- `0x5e198`: `AddSubFolderUsingPath`

## pseudocode

```c

```

## disassembly

```asm
0x5dff0  ldarg.s  4
0x5dff2  brtrue.s loc_5DFFF
0x5dff4  ldstr    aProxycontext// "proxyContext"
0x5dff9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5dffe  throw
0x5dfff  ldarg.1
0x5e000  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder
0x5e005  stloc.0
0x5e006  ldloc.0
0x5e007  brtrue.s loc_5E014
0x5e009  ldstr    aTarget// "target"
0x5e00e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5e013  throw
0x5e014  ldarg.0
0x5e015  ldarg.2
0x5e016  ldarg.s  4
0x5e018  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e01d  starg.s  2
0x5e01f  ldarg.2
0x5e020  dup
0x5e021  stloc.1
0x5e022  brfalse  loc_5E1EB
0x5e027  volatile.
0x5e029  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60010c8-1
0x5e02e  brtrue.s loc_5E0AA
0x5e030  ldc.i4.s 9
0x5e032  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x5e037  dup
0x5e038  ldstr    aGetlistitemcha_0// "GetListItemChanges"
0x5e03d  ldc.i4.0
0x5e03e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e043  dup
0x5e044  ldstr    aGetchanges// "GetChanges"
0x5e049  ldc.i4.1
0x5e04a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e04f  dup
0x5e050  ldstr    aUpdate// "Update"
0x5e055  ldc.i4.2
0x5e056  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e05b  dup
0x5e05c  ldstr    aMoveto// "MoveTo"
0x5e061  ldc.i4.3
0x5e062  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e067  dup
0x5e068  ldstr    aMovetousingpat// "MoveToUsingPath"
0x5e06d  ldc.i4.4
0x5e06e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e073  dup
0x5e074  ldstr    aAddsubfolder// "AddSubFolder"
0x5e079  ldc.i4.5
0x5e07a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e07f  dup
0x5e080  ldstr    aAddsubfolderus// "AddSubFolderUsingPath"
0x5e085  ldc.i4.6
0x5e086  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e08b  dup
0x5e08c  ldstr    aDeleteobject// "DeleteObject"
0x5e091  ldc.i4.7
0x5e092  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e097  dup
0x5e098  ldstr    aRecycle// "Recycle"
0x5e09d  ldc.i4.8
0x5e09e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e0a3  volatile.
0x5e0a5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60010c8-1
0x5e0aa  volatile.
0x5e0ac  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60010c8-1
0x5e0b1  ldloc.1
0x5e0b2  ldloca.s 2
0x5e0b4  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x5e0b9  brfalse  loc_5E1EB
0x5e0be  ldloc.2
0x5e0bf  switch   loc_5E0ED, loc_5E108, loc_5E123, loc_5E13F, loc_5E15B, loc_5E177, loc_5E193, loc_5E1AF, loc_5E1CB
0x5e0e8  br       loc_5E1EB
0x5e0ed  ldarg.s  5
0x5e0ef  ldc.i4.0
0x5e0f0  stind.i1
0x5e0f1  ldarg.0
0x5e0f2  ldstr    aGetlistitemcha_0// "GetListItemChanges"
0x5e0f7  ldarg.s  4
0x5e0f9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e0fe  ldloc.0
0x5e0ff  ldarg.3
0x5e100  ldarg.s  4
0x5e102  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeCollection Microsoft.SharePoint.ServerStub.SPFolderServerStub::GetListItemChanges_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5e107  ret
0x5e108  ldarg.s  5
0x5e10a  ldc.i4.0
0x5e10b  stind.i1
0x5e10c  ldarg.0
0x5e10d  ldstr    aGetchanges// "GetChanges"
0x5e112  ldarg.s  4
0x5e114  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e119  ldloc.0
0x5e11a  ldarg.3
0x5e11b  ldarg.s  4
0x5e11d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeCollection Microsoft.SharePoint.ServerStub.SPFolderServerStub::GetChanges_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5e122  ret
0x5e123  ldarg.s  5
0x5e125  ldc.i4.1
0x5e126  stind.i1
0x5e127  ldarg.0
0x5e128  ldstr    aUpdate// "Update"
0x5e12d  ldarg.s  4
0x5e12f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e134  ldloc.0
0x5e135  ldarg.3
0x5e136  ldarg.s  4
0x5e138  call     void Microsoft.SharePoint.ServerStub.SPFolderServerStub::Update_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5e13d  ldnull
0x5e13e  ret
0x5e13f  ldarg.s  5
0x5e141  ldc.i4.1
0x5e142  stind.i1
0x5e143  ldarg.0
0x5e144  ldstr    aMoveto// "MoveTo"
0x5e149  ldarg.s  4
0x5e14b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e150  ldloc.0
0x5e151  ldarg.3
0x5e152  ldarg.s  4
0x5e154  call     void Microsoft.SharePoint.ServerStub.SPFolderServerStub::MoveTo_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5e159  ldnull
0x5e15a  ret
0x5e15b  ldarg.s  5
0x5e15d  ldc.i4.1
0x5e15e  stind.i1
0x5e15f  ldarg.0
0x5e160  ldstr    aMovetousingpat// "MoveToUsingPath"
0x5e165  ldarg.s  4
0x5e167  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e16c  ldloc.0
0x5e16d  ldarg.3
0x5e16e  ldarg.s  4
0x5e170  call     void Microsoft.SharePoint.ServerStub.SPFolderServerStub::MoveToUsingPath_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5e175  ldnull
0x5e176  ret
0x5e177  ldarg.s  5
0x5e179  ldc.i4.1
0x5e17a  stind.i1
0x5e17b  ldarg.0
0x5e17c  ldstr    aAddsubfolder// "AddSubFolder"
0x5e181  ldarg.s  4
0x5e183  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e188  ldloc.0
0x5e189  ldarg.3
0x5e18a  ldarg.s  4
0x5e18c  call     void Microsoft.SharePoint.ServerStub.SPFolderServerStub::AddSubFolder_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5e191  ldnull
0x5e192  ret
0x5e193  ldarg.s  5
0x5e195  ldc.i4.1
0x5e196  stind.i1
0x5e197  ldarg.0
0x5e198  ldstr    aAddsubfolderus// "AddSubFolderUsingPath"
0x5e19d  ldarg.s  4
0x5e19f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e1a4  ldloc.0
0x5e1a5  ldarg.3
0x5e1a6  ldarg.s  4
0x5e1a8  call     void Microsoft.SharePoint.ServerStub.SPFolderServerStub::AddSubFolderUsingPath_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5e1ad  ldnull
0x5e1ae  ret
0x5e1af  ldarg.s  5
0x5e1b1  ldc.i4.1
0x5e1b2  stind.i1
0x5e1b3  ldarg.0
0x5e1b4  ldstr    aDeleteobject// "DeleteObject"
0x5e1b9  ldarg.s  4
0x5e1bb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e1c0  ldloc.0
0x5e1c1  ldarg.3
0x5e1c2  ldarg.s  4
0x5e1c4  call     void Microsoft.SharePoint.ServerStub.SPFolderServerStub::DeleteObject_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5e1c9  ldnull
0x5e1ca  ret
0x5e1cb  ldarg.s  5
0x5e1cd  ldc.i4.0
0x5e1ce  stind.i1
0x5e1cf  ldarg.0
0x5e1d0  ldstr    aRecycle// "Recycle"
0x5e1d5  ldarg.s  4
0x5e1d7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e1dc  ldloc.0
0x5e1dd  ldarg.3
0x5e1de  ldarg.s  4
0x5e1e0  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.ServerStub.SPFolderServerStub::Recycle_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5e1e5  box      [mscorlib]System.Guid
0x5e1ea  ret
0x5e1eb  ldarg.0
0x5e1ec  ldarg.1
0x5e1ed  ldarg.2
0x5e1ee  ldarg.3
0x5e1ef  ldarg.s  4
0x5e1f1  ldarg.s  5
0x5e1f3  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x5e1f8  ret
```
