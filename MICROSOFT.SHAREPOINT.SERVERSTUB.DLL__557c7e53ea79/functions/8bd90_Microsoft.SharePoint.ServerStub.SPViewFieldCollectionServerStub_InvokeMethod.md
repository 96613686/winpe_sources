# Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::InvokeMethod

- ea: `0x8bd90`
- end: `0x8bf6a`
- name: `Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::InvokeMethod`
- size: `474`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x8bc90`
- `0x8bcc0`
- `0x8bcf0`
- `0x8bd10`
- `0x8bd30`
- `0x8bd50`
- `0x8bd70`
- `0x8bd80`
- `0x8bd90`

## string_xrefs

- `0x8be07`: `Remove`
- `0x8bef1`: `Remove`
- `0x8be1f`: `RemoveAll`
- `0x8bf29`: `RemoveAll`
- `0x8bdd7`: `MoveFieldTo`
- `0x8be81`: `MoveFieldTo`
- `0x8bde3`: `MoveViewFieldTo`
- `0x8be9d`: `MoveViewFieldTo`
- `0x8be13`: `RemoveViewField`
- `0x8bf0d`: `RemoveViewField`
- `0x8be2b`: `RemoveAllViewFields`
- `0x8bf45`: `RemoveAllViewFields`

## pseudocode

```c

```

## disassembly

```asm
0x8bd90  ldarg.s  4
0x8bd92  brtrue.s loc_8BD9F
0x8bd94  ldstr    aProxycontext// "proxyContext"
0x8bd99  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8bd9e  throw
0x8bd9f  ldarg.1
0x8bda0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection
0x8bda5  stloc.0
0x8bda6  ldloc.0
0x8bda7  brtrue.s loc_8BDB4
0x8bda9  ldstr    aTarget// "target"
0x8bdae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8bdb3  throw
0x8bdb4  ldarg.0
0x8bdb5  ldarg.2
0x8bdb6  ldarg.s  4
0x8bdb8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8bdbd  starg.s  2
0x8bdbf  ldarg.2
0x8bdc0  dup
0x8bdc1  stloc.1
0x8bdc2  brfalse  loc_8BF5C
0x8bdc7  volatile.
0x8bdc9  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001764-1
0x8bdce  brtrue.s loc_8BE3D
0x8bdd0  ldc.i4.8
0x8bdd1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x8bdd6  dup
0x8bdd7  ldstr    aMovefieldto// "MoveFieldTo"
0x8bddc  ldc.i4.0
0x8bddd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8bde2  dup
0x8bde3  ldstr    aMoveviewfieldt// "MoveViewFieldTo"
0x8bde8  ldc.i4.1
0x8bde9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8bdee  dup
0x8bdef  ldstr    aAdd// "Add"
0x8bdf4  ldc.i4.2
0x8bdf5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8bdfa  dup
0x8bdfb  ldstr    aAddviewfield// "AddViewField"
0x8be00  ldc.i4.3
0x8be01  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8be06  dup
0x8be07  ldstr    aRemove// "Remove"
0x8be0c  ldc.i4.4
0x8be0d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8be12  dup
0x8be13  ldstr    aRemoveviewfiel// "RemoveViewField"
0x8be18  ldc.i4.5
0x8be19  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8be1e  dup
0x8be1f  ldstr    aRemoveall// "RemoveAll"
0x8be24  ldc.i4.6
0x8be25  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8be2a  dup
0x8be2b  ldstr    aRemoveallviewf// "RemoveAllViewFields"
0x8be30  ldc.i4.7
0x8be31  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8be36  volatile.
0x8be38  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001764-1
0x8be3d  volatile.
0x8be3f  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001764-1
0x8be44  ldloc.1
0x8be45  ldloca.s 2
0x8be47  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x8be4c  brfalse  loc_8BF5C
0x8be51  ldloc.2
0x8be52  switch   loc_8BE7C, loc_8BE98, loc_8BEB4, loc_8BED0, loc_8BEEC, loc_8BF08, loc_8BF24, loc_8BF40
0x8be77  br       loc_8BF5C
0x8be7c  ldarg.s  5
0x8be7e  ldc.i4.1
0x8be7f  stind.i1
0x8be80  ldarg.0
0x8be81  ldstr    aMovefieldto// "MoveFieldTo"
0x8be86  ldarg.s  4
0x8be88  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8be8d  ldloc.0
0x8be8e  ldarg.3
0x8be8f  ldarg.s  4
0x8be91  call     void Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::MoveFieldTo_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8be96  ldnull
0x8be97  ret
0x8be98  ldarg.s  5
0x8be9a  ldc.i4.1
0x8be9b  stind.i1
0x8be9c  ldarg.0
0x8be9d  ldstr    aMoveviewfieldt// "MoveViewFieldTo"
0x8bea2  ldarg.s  4
0x8bea4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8bea9  ldloc.0
0x8beaa  ldarg.3
0x8beab  ldarg.s  4
0x8bead  call     void Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::MoveViewFieldTo_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8beb2  ldnull
0x8beb3  ret
0x8beb4  ldarg.s  5
0x8beb6  ldc.i4.1
0x8beb7  stind.i1
0x8beb8  ldarg.0
0x8beb9  ldstr    aAdd// "Add"
0x8bebe  ldarg.s  4
0x8bec0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8bec5  ldloc.0
0x8bec6  ldarg.3
0x8bec7  ldarg.s  4
0x8bec9  call     void Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::Add_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8bece  ldnull
0x8becf  ret
0x8bed0  ldarg.s  5
0x8bed2  ldc.i4.1
0x8bed3  stind.i1
0x8bed4  ldarg.0
0x8bed5  ldstr    aAddviewfield// "AddViewField"
0x8beda  ldarg.s  4
0x8bedc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8bee1  ldloc.0
0x8bee2  ldarg.3
0x8bee3  ldarg.s  4
0x8bee5  call     void Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::AddViewField_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8beea  ldnull
0x8beeb  ret
0x8beec  ldarg.s  5
0x8beee  ldc.i4.1
0x8beef  stind.i1
0x8bef0  ldarg.0
0x8bef1  ldstr    aRemove// "Remove"
0x8bef6  ldarg.s  4
0x8bef8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8befd  ldloc.0
0x8befe  ldarg.3
0x8beff  ldarg.s  4
0x8bf01  call     void Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::Remove_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8bf06  ldnull
0x8bf07  ret
0x8bf08  ldarg.s  5
0x8bf0a  ldc.i4.1
0x8bf0b  stind.i1
0x8bf0c  ldarg.0
0x8bf0d  ldstr    aRemoveviewfiel// "RemoveViewField"
0x8bf12  ldarg.s  4
0x8bf14  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8bf19  ldloc.0
0x8bf1a  ldarg.3
0x8bf1b  ldarg.s  4
0x8bf1d  call     void Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::RemoveViewField_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8bf22  ldnull
0x8bf23  ret
0x8bf24  ldarg.s  5
0x8bf26  ldc.i4.1
0x8bf27  stind.i1
0x8bf28  ldarg.0
0x8bf29  ldstr    aRemoveall// "RemoveAll"
0x8bf2e  ldarg.s  4
0x8bf30  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8bf35  ldloc.0
0x8bf36  ldarg.3
0x8bf37  ldarg.s  4
0x8bf39  call     void Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::RemoveAll_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8bf3e  ldnull
0x8bf3f  ret
0x8bf40  ldarg.s  5
0x8bf42  ldc.i4.1
0x8bf43  stind.i1
0x8bf44  ldarg.0
0x8bf45  ldstr    aRemoveallviewf// "RemoveAllViewFields"
0x8bf4a  ldarg.s  4
0x8bf4c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8bf51  ldloc.0
0x8bf52  ldarg.3
0x8bf53  ldarg.s  4
0x8bf55  call     void Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::RemoveAllViewFields_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8bf5a  ldnull
0x8bf5b  ret
0x8bf5c  ldarg.0
0x8bf5d  ldarg.1
0x8bf5e  ldarg.2
0x8bf5f  ldarg.3
0x8bf60  ldarg.s  4
0x8bf62  ldarg.s  5
0x8bf64  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x8bf69  ret
```
