# Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::InvokeMethod

- ea: `0x5b720`
- end: `0x5b8cd`
- name: `Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::InvokeMethod`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x5b650`
- `0x5b670`
- `0x5b690`
- `0x5b6b0`
- `0x5b6d0`
- `0x5b6f0`
- `0x5b700`
- `0x5b720`

## string_xrefs

- `0x5b7a3`: `DeleteAll`
- `0x5b88c`: `DeleteAll`
- `0x5b773`: `DeleteByID`
- `0x5b81c`: `DeleteByID`
- `0x5b78b`: `DeleteByLabel`
- `0x5b854`: `DeleteByLabel`

## pseudocode

```c

```

## disassembly

```asm
0x5b720  ldarg.s  4
0x5b722  brtrue.s loc_5B72F
0x5b724  ldstr    aProxycontext// "proxyContext"
0x5b729  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5b72e  throw
0x5b72f  ldarg.1
0x5b730  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersionCollection
0x5b735  stloc.0
0x5b736  ldloc.0
0x5b737  brtrue.s loc_5B744
0x5b739  ldstr    aTarget// "target"
0x5b73e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5b743  throw
0x5b744  ldarg.0
0x5b745  ldarg.2
0x5b746  ldarg.s  4
0x5b748  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5b74d  starg.s  2
0x5b74f  ldarg.2
0x5b750  dup
0x5b751  stloc.1
0x5b752  brfalse  loc_5B8BF
0x5b757  volatile.
0x5b759  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001039-1
0x5b75e  brtrue.s loc_5B7C1
0x5b760  ldc.i4.7
0x5b761  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x5b766  dup
0x5b767  ldstr    aGetbyid// "GetById"
0x5b76c  ldc.i4.0
0x5b76d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5b772  dup
0x5b773  ldstr    aDeletebyid// "DeleteByID"
0x5b778  ldc.i4.1
0x5b779  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5b77e  dup
0x5b77f  ldstr    aRecyclebyid// "RecycleByID"
0x5b784  ldc.i4.2
0x5b785  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5b78a  dup
0x5b78b  ldstr    aDeletebylabel// "DeleteByLabel"
0x5b790  ldc.i4.3
0x5b791  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5b796  dup
0x5b797  ldstr    aRecyclebylabel// "RecycleByLabel"
0x5b79c  ldc.i4.4
0x5b79d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5b7a2  dup
0x5b7a3  ldstr    aDeleteall// "DeleteAll"
0x5b7a8  ldc.i4.5
0x5b7a9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5b7ae  dup
0x5b7af  ldstr    aRestorebylabel// "RestoreByLabel"
0x5b7b4  ldc.i4.6
0x5b7b5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5b7ba  volatile.
0x5b7bc  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001039-1
0x5b7c1  volatile.
0x5b7c3  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001039-1
0x5b7c8  ldloc.1
0x5b7c9  ldloca.s 2
0x5b7cb  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x5b7d0  brfalse  loc_5B8BF
0x5b7d5  ldloc.2
0x5b7d6  switch   loc_5B7FC, loc_5B817, loc_5B833, loc_5B84F, loc_5B86B, loc_5B887, loc_5B8A3
0x5b7f7  br       loc_5B8BF
0x5b7fc  ldarg.s  5
0x5b7fe  ldc.i4.0
0x5b7ff  stind.i1
0x5b800  ldarg.0
0x5b801  ldstr    aGetbyid// "GetById"
0x5b806  ldarg.s  4
0x5b808  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5b80d  ldloc.0
0x5b80e  ldarg.3
0x5b80f  ldarg.s  4
0x5b811  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::GetById_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersionCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5b816  ret
0x5b817  ldarg.s  5
0x5b819  ldc.i4.1
0x5b81a  stind.i1
0x5b81b  ldarg.0
0x5b81c  ldstr    aDeletebyid// "DeleteByID"
0x5b821  ldarg.s  4
0x5b823  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5b828  ldloc.0
0x5b829  ldarg.3
0x5b82a  ldarg.s  4
0x5b82c  call     void Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::DeleteByID_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersionCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5b831  ldnull
0x5b832  ret
0x5b833  ldarg.s  5
0x5b835  ldc.i4.1
0x5b836  stind.i1
0x5b837  ldarg.0
0x5b838  ldstr    aRecyclebyid// "RecycleByID"
0x5b83d  ldarg.s  4
0x5b83f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5b844  ldloc.0
0x5b845  ldarg.3
0x5b846  ldarg.s  4
0x5b848  call     void Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::RecycleByID_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersionCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5b84d  ldnull
0x5b84e  ret
0x5b84f  ldarg.s  5
0x5b851  ldc.i4.1
0x5b852  stind.i1
0x5b853  ldarg.0
0x5b854  ldstr    aDeletebylabel// "DeleteByLabel"
0x5b859  ldarg.s  4
0x5b85b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5b860  ldloc.0
0x5b861  ldarg.3
0x5b862  ldarg.s  4
0x5b864  call     void Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::DeleteByLabel_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersionCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5b869  ldnull
0x5b86a  ret
0x5b86b  ldarg.s  5
0x5b86d  ldc.i4.1
0x5b86e  stind.i1
0x5b86f  ldarg.0
0x5b870  ldstr    aRecyclebylabel// "RecycleByLabel"
0x5b875  ldarg.s  4
0x5b877  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5b87c  ldloc.0
0x5b87d  ldarg.3
0x5b87e  ldarg.s  4
0x5b880  call     void Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::RecycleByLabel_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersionCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5b885  ldnull
0x5b886  ret
0x5b887  ldarg.s  5
0x5b889  ldc.i4.1
0x5b88a  stind.i1
0x5b88b  ldarg.0
0x5b88c  ldstr    aDeleteall// "DeleteAll"
0x5b891  ldarg.s  4
0x5b893  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5b898  ldloc.0
0x5b899  ldarg.3
0x5b89a  ldarg.s  4
0x5b89c  call     void Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::DeleteAll_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersionCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5b8a1  ldnull
0x5b8a2  ret
0x5b8a3  ldarg.s  5
0x5b8a5  ldc.i4.1
0x5b8a6  stind.i1
0x5b8a7  ldarg.0
0x5b8a8  ldstr    aRestorebylabel// "RestoreByLabel"
0x5b8ad  ldarg.s  4
0x5b8af  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5b8b4  ldloc.0
0x5b8b5  ldarg.3
0x5b8b6  ldarg.s  4
0x5b8b8  call     void Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::RestoreByLabel_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersionCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5b8bd  ldnull
0x5b8be  ret
0x5b8bf  ldarg.0
0x5b8c0  ldarg.1
0x5b8c1  ldarg.2
0x5b8c2  ldarg.3
0x5b8c3  ldarg.s  4
0x5b8c5  ldarg.s  5
0x5b8c7  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x5b8cc  ret
```
