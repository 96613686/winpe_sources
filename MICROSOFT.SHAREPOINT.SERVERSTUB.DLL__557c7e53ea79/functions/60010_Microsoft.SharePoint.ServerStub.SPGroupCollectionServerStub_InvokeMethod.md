# Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::InvokeMethod

- ea: `0x60010`
- end: `0x601ba`
- name: `Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::InvokeMethod`
- size: `426`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x5ff30`
- `0x5ff50`
- `0x5ff70`
- `0x5ff90`
- `0x5ffb0`
- `0x5ffd0`
- `0x5fff0`
- `0x60010`

## string_xrefs

- `0x6007b`: `Create`
- `0x60142`: `Create`
- `0x6009f`: `Remove`
- `0x60195`: `Remove`
- `0x60093`: `RemoveById`
- `0x60179`: `RemoveById`
- `0x60087`: `RemoveByLoginName`
- `0x6015d`: `RemoveByLoginName`

## pseudocode

```c

```

## disassembly

```asm
0x60010  ldarg.s  4
0x60012  brtrue.s loc_6001F
0x60014  ldstr    aProxycontext// "proxyContext"
0x60019  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6001e  throw
0x6001f  ldarg.1
0x60020  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupCollection
0x60025  stloc.0
0x60026  ldloc.0
0x60027  brtrue.s loc_60034
0x60029  ldstr    aTarget// "target"
0x6002e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x60033  throw
0x60034  ldarg.0
0x60035  ldarg.2
0x60036  ldarg.s  4
0x60038  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6003d  starg.s  2
0x6003f  ldarg.2
0x60040  dup
0x60041  stloc.1
0x60042  brfalse  loc_601AC
0x60047  volatile.
0x60049  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001114-1
0x6004e  brtrue.s loc_600B1
0x60050  ldc.i4.7
0x60051  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x60056  dup
0x60057  ldstr    aGetbyname// "GetByName"
0x6005c  ldc.i4.0
0x6005d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x60062  dup
0x60063  ldstr    aGetbyid// "GetById"
0x60068  ldc.i4.1
0x60069  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6006e  dup
0x6006f  ldstr    aAdd// "Add"
0x60074  ldc.i4.2
0x60075  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6007a  dup
0x6007b  ldstr    aCreate// "Create"
0x60080  ldc.i4.3
0x60081  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x60086  dup
0x60087  ldstr    aRemovebyloginn// "RemoveByLoginName"
0x6008c  ldc.i4.4
0x6008d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x60092  dup
0x60093  ldstr    aRemovebyid// "RemoveById"
0x60098  ldc.i4.5
0x60099  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6009e  dup
0x6009f  ldstr    aRemove// "Remove"
0x600a4  ldc.i4.6
0x600a5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x600aa  volatile.
0x600ac  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001114-1
0x600b1  volatile.
0x600b3  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001114-1
0x600b8  ldloc.1
0x600b9  ldloca.s 2
0x600bb  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x600c0  brfalse  loc_601AC
0x600c5  ldloc.2
0x600c6  switch   loc_600EC, loc_60107, loc_60122, loc_6013D, loc_60158, loc_60174, loc_60190
0x600e7  br       loc_601AC
0x600ec  ldarg.s  5
0x600ee  ldc.i4.0
0x600ef  stind.i1
0x600f0  ldarg.0
0x600f1  ldstr    aGetbyname// "GetByName"
0x600f6  ldarg.s  4
0x600f8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x600fd  ldloc.0
0x600fe  ldarg.3
0x600ff  ldarg.s  4
0x60101  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroup Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::GetByName_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x60106  ret
0x60107  ldarg.s  5
0x60109  ldc.i4.0
0x6010a  stind.i1
0x6010b  ldarg.0
0x6010c  ldstr    aGetbyid// "GetById"
0x60111  ldarg.s  4
0x60113  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x60118  ldloc.0
0x60119  ldarg.3
0x6011a  ldarg.s  4
0x6011c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroup Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::GetById_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x60121  ret
0x60122  ldarg.s  5
0x60124  ldc.i4.0
0x60125  stind.i1
0x60126  ldarg.0
0x60127  ldstr    aAdd// "Add"
0x6012c  ldarg.s  4
0x6012e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x60133  ldloc.0
0x60134  ldarg.3
0x60135  ldarg.s  4
0x60137  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroup Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::Add_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6013c  ret
0x6013d  ldarg.s  5
0x6013f  ldc.i4.0
0x60140  stind.i1
0x60141  ldarg.0
0x60142  ldstr    aCreate// "Create"
0x60147  ldarg.s  4
0x60149  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6014e  ldloc.0
0x6014f  ldarg.3
0x60150  ldarg.s  4
0x60152  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroup Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::Create_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x60157  ret
0x60158  ldarg.s  5
0x6015a  ldc.i4.1
0x6015b  stind.i1
0x6015c  ldarg.0
0x6015d  ldstr    aRemovebyloginn// "RemoveByLoginName"
0x60162  ldarg.s  4
0x60164  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x60169  ldloc.0
0x6016a  ldarg.3
0x6016b  ldarg.s  4
0x6016d  call     void Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::RemoveByLoginName_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x60172  ldnull
0x60173  ret
0x60174  ldarg.s  5
0x60176  ldc.i4.1
0x60177  stind.i1
0x60178  ldarg.0
0x60179  ldstr    aRemovebyid// "RemoveById"
0x6017e  ldarg.s  4
0x60180  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x60185  ldloc.0
0x60186  ldarg.3
0x60187  ldarg.s  4
0x60189  call     void Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::RemoveById_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6018e  ldnull
0x6018f  ret
0x60190  ldarg.s  5
0x60192  ldc.i4.1
0x60193  stind.i1
0x60194  ldarg.0
0x60195  ldstr    aRemove// "Remove"
0x6019a  ldarg.s  4
0x6019c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x601a1  ldloc.0
0x601a2  ldarg.3
0x601a3  ldarg.s  4
0x601a5  call     void Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::Remove_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x601aa  ldnull
0x601ab  ret
0x601ac  ldarg.0
0x601ad  ldarg.1
0x601ae  ldarg.2
0x601af  ldarg.3
0x601b0  ldarg.s  4
0x601b2  ldarg.s  5
0x601b4  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x601b9  ret
```
