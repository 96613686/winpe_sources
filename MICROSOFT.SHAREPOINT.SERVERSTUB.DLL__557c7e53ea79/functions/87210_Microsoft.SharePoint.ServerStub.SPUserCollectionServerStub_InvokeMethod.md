# Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::InvokeMethod

- ea: `0x87210`
- end: `0x87411`
- name: `Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::InvokeMethod`
- size: `513`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x870f0`
- `0x87110`
- `0x87130`
- `0x87150`
- `0x87170`
- `0x87190`
- `0x871b0`
- `0x871d0`
- `0x871f0`
- `0x87210`

## string_xrefs

- `0x872ac`: `Create`
- `0x873d2`: `Create`
- `0x87288`: `Remove`
- `0x87380`: `Remove`
- `0x8727c`: `RemoveById`
- `0x87364`: `RemoveById`
- `0x87270`: `RemoveByLoginName`
- `0x87348`: `RemoveByLoginName`

## pseudocode

```c

```

## disassembly

```asm
0x87210  ldarg.s  4
0x87212  brtrue.s loc_8721F
0x87214  ldstr    aProxycontext// "proxyContext"
0x87219  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8721e  throw
0x8721f  ldarg.1
0x87220  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection
0x87225  stloc.0
0x87226  ldloc.0
0x87227  brtrue.s loc_87234
0x87229  ldstr    aTarget// "target"
0x8722e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x87233  throw
0x87234  ldarg.0
0x87235  ldarg.2
0x87236  ldarg.s  4
0x87238  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8723d  starg.s  2
0x8723f  ldarg.2
0x87240  dup
0x87241  stloc.1
0x87242  brfalse  loc_87403
0x87247  volatile.
0x87249  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600169b-1
0x8724e  brtrue.s loc_872CA
0x87250  ldc.i4.s 9
0x87252  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x87257  dup
0x87258  ldstr    aGetbyid// "GetById"
0x8725d  ldc.i4.0
0x8725e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x87263  dup
0x87264  ldstr    aGetbyemail// "GetByEmail"
0x87269  ldc.i4.1
0x8726a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8726f  dup
0x87270  ldstr    aRemovebyloginn// "RemoveByLoginName"
0x87275  ldc.i4.2
0x87276  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8727b  dup
0x8727c  ldstr    aRemovebyid// "RemoveById"
0x87281  ldc.i4.3
0x87282  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x87287  dup
0x87288  ldstr    aRemove// "Remove"
0x8728d  ldc.i4.4
0x8728e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x87293  dup
0x87294  ldstr    aAdd// "Add"
0x87299  ldc.i4.5
0x8729a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8729f  dup
0x872a0  ldstr    aAdduser// "AddUser"
0x872a5  ldc.i4.6
0x872a6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x872ab  dup
0x872ac  ldstr    aCreate// "Create"
0x872b1  ldc.i4.7
0x872b2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x872b7  dup
0x872b8  ldstr    aGetbyloginname// "GetByLoginName"
0x872bd  ldc.i4.8
0x872be  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x872c3  volatile.
0x872c5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600169b-1
0x872ca  volatile.
0x872cc  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600169b-1
0x872d1  ldloc.1
0x872d2  ldloca.s 2
0x872d4  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x872d9  brfalse  loc_87403
0x872de  ldloc.2
0x872df  switch   loc_8730D, loc_87328, loc_87343, loc_8735F, loc_8737B, loc_87397, loc_873B2, loc_873CD, loc_873E8
0x87308  br       loc_87403
0x8730d  ldarg.s  5
0x8730f  ldc.i4.0
0x87310  stind.i1
0x87311  ldarg.0
0x87312  ldstr    aGetbyid// "GetById"
0x87317  ldarg.s  4
0x87319  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8731e  ldloc.0
0x8731f  ldarg.3
0x87320  ldarg.s  4
0x87322  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::GetById_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x87327  ret
0x87328  ldarg.s  5
0x8732a  ldc.i4.0
0x8732b  stind.i1
0x8732c  ldarg.0
0x8732d  ldstr    aGetbyemail// "GetByEmail"
0x87332  ldarg.s  4
0x87334  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x87339  ldloc.0
0x8733a  ldarg.3
0x8733b  ldarg.s  4
0x8733d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::GetByEmail_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x87342  ret
0x87343  ldarg.s  5
0x87345  ldc.i4.1
0x87346  stind.i1
0x87347  ldarg.0
0x87348  ldstr    aRemovebyloginn// "RemoveByLoginName"
0x8734d  ldarg.s  4
0x8734f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x87354  ldloc.0
0x87355  ldarg.3
0x87356  ldarg.s  4
0x87358  call     void Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::RemoveByLoginName_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8735d  ldnull
0x8735e  ret
0x8735f  ldarg.s  5
0x87361  ldc.i4.1
0x87362  stind.i1
0x87363  ldarg.0
0x87364  ldstr    aRemovebyid// "RemoveById"
0x87369  ldarg.s  4
0x8736b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x87370  ldloc.0
0x87371  ldarg.3
0x87372  ldarg.s  4
0x87374  call     void Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::RemoveById_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x87379  ldnull
0x8737a  ret
0x8737b  ldarg.s  5
0x8737d  ldc.i4.1
0x8737e  stind.i1
0x8737f  ldarg.0
0x87380  ldstr    aRemove// "Remove"
0x87385  ldarg.s  4
0x87387  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8738c  ldloc.0
0x8738d  ldarg.3
0x8738e  ldarg.s  4
0x87390  call     void Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::Remove_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x87395  ldnull
0x87396  ret
0x87397  ldarg.s  5
0x87399  ldc.i4.0
0x8739a  stind.i1
0x8739b  ldarg.0
0x8739c  ldstr    aAdd// "Add"
0x873a1  ldarg.s  4
0x873a3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x873a8  ldloc.0
0x873a9  ldarg.3
0x873aa  ldarg.s  4
0x873ac  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::Add_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x873b1  ret
0x873b2  ldarg.s  5
0x873b4  ldc.i4.0
0x873b5  stind.i1
0x873b6  ldarg.0
0x873b7  ldstr    aAdduser// "AddUser"
0x873bc  ldarg.s  4
0x873be  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x873c3  ldloc.0
0x873c4  ldarg.3
0x873c5  ldarg.s  4
0x873c7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::AddUser_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x873cc  ret
0x873cd  ldarg.s  5
0x873cf  ldc.i4.0
0x873d0  stind.i1
0x873d1  ldarg.0
0x873d2  ldstr    aCreate// "Create"
0x873d7  ldarg.s  4
0x873d9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x873de  ldloc.0
0x873df  ldarg.3
0x873e0  ldarg.s  4
0x873e2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::Create_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x873e7  ret
0x873e8  ldarg.s  5
0x873ea  ldc.i4.0
0x873eb  stind.i1
0x873ec  ldarg.0
0x873ed  ldstr    aGetbyloginname// "GetByLoginName"
0x873f2  ldarg.s  4
0x873f4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x873f9  ldloc.0
0x873fa  ldarg.3
0x873fb  ldarg.s  4
0x873fd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::GetByLoginName_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x87402  ret
0x87403  ldarg.0
0x87404  ldarg.1
0x87405  ldarg.2
0x87406  ldarg.3
0x87407  ldarg.s  4
0x87409  ldarg.s  5
0x8740b  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x87410  ret
```
