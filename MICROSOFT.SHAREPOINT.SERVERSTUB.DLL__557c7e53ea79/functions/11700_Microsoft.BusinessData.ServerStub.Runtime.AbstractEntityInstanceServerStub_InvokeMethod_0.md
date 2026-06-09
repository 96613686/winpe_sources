# Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::InvokeMethod_0

- ea: `0x11700`
- end: `0x11904`
- name: `Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::InvokeMethod_0`
- size: `516`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x115f0`
- `0x11620`
- `0x11650`
- `0x11680`
- `0x11690`
- `0x116a0`
- `0x116b0`
- `0x116d0`
- `0x116e0`
- `0x11700`

## string_xrefs

- `0x11784`: `Update`
- `0x1188d`: `Update`
- `0x11778`: `DeleteObject`
- `0x11871`: `DeleteObject`
- `0x11754`: `CreateInstance`
- `0x1181e`: `CreateInstance`
- `0x11760`: `CreateCollectionInstance`
- `0x1183a`: `CreateCollectionInstance`
- `0x11790`: `FromXml`
- `0x118a9`: `FromXml`
- `0x1179c`: `ToXml`
- `0x118c5`: `ToXml`

## pseudocode

```c

```

## disassembly

```asm
0x11700  ldarg.s  4
0x11702  brtrue.s loc_1170F
0x11704  ldstr    aProxycontext// "proxyContext"
0x11709  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1170e  throw
0x1170f  ldarg.1
0x11710  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance
0x11715  stloc.0
0x11716  ldloc.0
0x11717  brtrue.s loc_11724
0x11719  ldstr    aTarget// "target"
0x1171e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11723  throw
0x11724  ldarg.0
0x11725  ldarg.2
0x11726  ldarg.s  4
0x11728  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1172d  starg.s  2
0x1172f  ldarg.2
0x11730  dup
0x11731  stloc.1
0x11732  brfalse  loc_118F6
0x11737  volatile.
0x11739  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60002df-1
0x1173e  brtrue.s loc_117BA
0x11740  ldc.i4.s 9
0x11742  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x11747  dup
0x11748  ldstr    aSetfieldvalue// "SetFieldValue"
0x1174d  ldc.i4.0
0x1174e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11753  dup
0x11754  ldstr    aCreateinstance// "CreateInstance"
0x11759  ldc.i4.1
0x1175a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1175f  dup
0x11760  ldstr    aCreatecollecti// "CreateCollectionInstance"
0x11765  ldc.i4.2
0x11766  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1176b  dup
0x1176c  ldstr    aGetidentity// "GetIdentity"
0x11771  ldc.i4.3
0x11772  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11777  dup
0x11778  ldstr    aDeleteobject// "DeleteObject"
0x1177d  ldc.i4.4
0x1177e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11783  dup
0x11784  ldstr    aUpdate// "Update"
0x11789  ldc.i4.5
0x1178a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1178f  dup
0x11790  ldstr    aFromxml// "FromXml"
0x11795  ldc.i4.6
0x11796  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1179b  dup
0x1179c  ldstr    aToxml// "ToXml"
0x117a1  ldc.i4.7
0x117a2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x117a7  dup
0x117a8  ldstr    aGetfieldvalue// "GetFieldValue"
0x117ad  ldc.i4.8
0x117ae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x117b3  volatile.
0x117b5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60002df-1
0x117ba  volatile.
0x117bc  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60002df-1
0x117c1  ldloc.1
0x117c2  ldloca.s 2
0x117c4  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x117c9  brfalse  loc_118F6
0x117ce  ldloc.2
0x117cf  switch   loc_117FD, loc_11819, loc_11835, loc_11851, loc_1186C, loc_11888, loc_118A4, loc_118C0, loc_118DB
0x117f8  br       loc_118F6
0x117fd  ldarg.s  5
0x117ff  ldc.i4.1
0x11800  stind.i1
0x11801  ldarg.0
0x11802  ldstr    aSetfieldvalue// "SetFieldValue"
0x11807  ldarg.s  4
0x11809  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1180e  ldloc.0
0x1180f  ldarg.3
0x11810  ldarg.s  4
0x11812  call     void Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::SetFieldValue_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11817  ldnull
0x11818  ret
0x11819  ldarg.s  5
0x1181b  ldc.i4.1
0x1181c  stind.i1
0x1181d  ldarg.0
0x1181e  ldstr    aCreateinstance// "CreateInstance"
0x11823  ldarg.s  4
0x11825  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1182a  ldloc.0
0x1182b  ldarg.3
0x1182c  ldarg.s  4
0x1182e  call     void Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::CreateInstance_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11833  ldnull
0x11834  ret
0x11835  ldarg.s  5
0x11837  ldc.i4.1
0x11838  stind.i1
0x11839  ldarg.0
0x1183a  ldstr    aCreatecollecti// "CreateCollectionInstance"
0x1183f  ldarg.s  4
0x11841  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11846  ldloc.0
0x11847  ldarg.3
0x11848  ldarg.s  4
0x1184a  call     void Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::CreateCollectionInstance_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1184f  ldnull
0x11850  ret
0x11851  ldarg.s  5
0x11853  ldc.i4.0
0x11854  stind.i1
0x11855  ldarg.0
0x11856  ldstr    aGetidentity// "GetIdentity"
0x1185b  ldarg.s  4
0x1185d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11862  ldloc.0
0x11863  ldarg.3
0x11864  ldarg.s  4
0x11866  call     class [Microsoft.BusinessData]Microsoft.BusinessData.Runtime.Identity Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::GetIdentity_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1186b  ret
0x1186c  ldarg.s  5
0x1186e  ldc.i4.1
0x1186f  stind.i1
0x11870  ldarg.0
0x11871  ldstr    aDeleteobject// "DeleteObject"
0x11876  ldarg.s  4
0x11878  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1187d  ldloc.0
0x1187e  ldarg.3
0x1187f  ldarg.s  4
0x11881  call     void Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::DeleteObject_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11886  ldnull
0x11887  ret
0x11888  ldarg.s  5
0x1188a  ldc.i4.1
0x1188b  stind.i1
0x1188c  ldarg.0
0x1188d  ldstr    aUpdate// "Update"
0x11892  ldarg.s  4
0x11894  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11899  ldloc.0
0x1189a  ldarg.3
0x1189b  ldarg.s  4
0x1189d  call     void Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::Update_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x118a2  ldnull
0x118a3  ret
0x118a4  ldarg.s  5
0x118a6  ldc.i4.1
0x118a7  stind.i1
0x118a8  ldarg.0
0x118a9  ldstr    aFromxml// "FromXml"
0x118ae  ldarg.s  4
0x118b0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x118b5  ldloc.0
0x118b6  ldarg.3
0x118b7  ldarg.s  4
0x118b9  call     void Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::FromXml_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x118be  ldnull
0x118bf  ret
0x118c0  ldarg.s  5
0x118c2  ldc.i4.0
0x118c3  stind.i1
0x118c4  ldarg.0
0x118c5  ldstr    aToxml// "ToXml"
0x118ca  ldarg.s  4
0x118cc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x118d1  ldloc.0
0x118d2  ldarg.3
0x118d3  ldarg.s  4
0x118d5  call     string Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::ToXml_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x118da  ret
0x118db  ldarg.s  5
0x118dd  ldc.i4.0
0x118de  stind.i1
0x118df  ldarg.0
0x118e0  ldstr    aGetfieldvalue// "GetFieldValue"
0x118e5  ldarg.s  4
0x118e7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x118ec  ldloc.0
0x118ed  ldarg.3
0x118ee  ldarg.s  4
0x118f0  call     object Microsoft.BusinessData.ServerStub.Runtime.AbstractEntityInstanceServerStub::GetFieldValue_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x118f5  ret
0x118f6  ldarg.0
0x118f7  ldarg.1
0x118f8  ldarg.2
0x118f9  ldarg.3
0x118fa  ldarg.s  4
0x118fc  ldarg.s  5
0x118fe  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x11903  ret
```
