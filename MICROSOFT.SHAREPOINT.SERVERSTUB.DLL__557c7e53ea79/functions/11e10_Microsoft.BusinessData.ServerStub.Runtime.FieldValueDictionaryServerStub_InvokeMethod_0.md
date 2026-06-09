# Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::InvokeMethod_0

- ea: `0x11e10`
- end: `0x11fc0`
- name: `Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::InvokeMethod_0`
- size: `432`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x11d10`
- `0x11d30`
- `0x11d40`
- `0x11d70`
- `0x11da0`
- `0x11dc0`
- `0x11df0`
- `0x11e10`

## string_xrefs

- `0x11e6f`: `CreateInstance`
- `0x11f28`: `CreateInstance`
- `0x11e7b`: `CreateCollectionInstance`
- `0x11f44`: `CreateCollectionInstance`
- `0x11e57`: `FromXml`
- `0x11ef1`: `FromXml`
- `0x11e63`: `ToXml`
- `0x11f0d`: `ToXml`

## pseudocode

```c

```

## disassembly

```asm
0x11e10  ldarg.s  4
0x11e12  brtrue.s loc_11E1F
0x11e14  ldstr    aProxycontext// "proxyContext"
0x11e19  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11e1e  throw
0x11e1f  ldarg.1
0x11e20  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.FieldValueDictionary
0x11e25  stloc.0
0x11e26  ldloc.0
0x11e27  brtrue.s loc_11E34
0x11e29  ldstr    aTarget// "target"
0x11e2e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11e33  throw
0x11e34  ldarg.0
0x11e35  ldarg.2
0x11e36  ldarg.s  4
0x11e38  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11e3d  starg.s  2
0x11e3f  ldarg.2
0x11e40  dup
0x11e41  stloc.1
0x11e42  brfalse  loc_11FB2
0x11e47  volatile.
0x11e49  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60002fb-1
0x11e4e  brtrue.s loc_11EB1
0x11e50  ldc.i4.7
0x11e51  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x11e56  dup
0x11e57  ldstr    aFromxml// "FromXml"
0x11e5c  ldc.i4.0
0x11e5d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11e62  dup
0x11e63  ldstr    aToxml// "ToXml"
0x11e68  ldc.i4.1
0x11e69  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11e6e  dup
0x11e6f  ldstr    aCreateinstance// "CreateInstance"
0x11e74  ldc.i4.2
0x11e75  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11e7a  dup
0x11e7b  ldstr    aCreatecollecti// "CreateCollectionInstance"
0x11e80  ldc.i4.3
0x11e81  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11e86  dup
0x11e87  ldstr    aGetcollections// "GetCollectionSize"
0x11e8c  ldc.i4.4
0x11e8d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11e92  dup
0x11e93  ldstr    aSetfieldvalue// "SetFieldValue"
0x11e98  ldc.i4.5
0x11e99  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11e9e  dup
0x11e9f  ldstr    aGetfieldvalue// "GetFieldValue"
0x11ea4  ldc.i4.6
0x11ea5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11eaa  volatile.
0x11eac  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60002fb-1
0x11eb1  volatile.
0x11eb3  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60002fb-1
0x11eb8  ldloc.1
0x11eb9  ldloca.s 2
0x11ebb  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x11ec0  brfalse  loc_11FB2
0x11ec5  ldloc.2
0x11ec6  switch   loc_11EEC, loc_11F08, loc_11F23, loc_11F3F, loc_11F5B, loc_11F7B, loc_11F97
0x11ee7  br       loc_11FB2
0x11eec  ldarg.s  5
0x11eee  ldc.i4.1
0x11eef  stind.i1
0x11ef0  ldarg.0
0x11ef1  ldstr    aFromxml// "FromXml"
0x11ef6  ldarg.s  4
0x11ef8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11efd  ldloc.0
0x11efe  ldarg.3
0x11eff  ldarg.s  4
0x11f01  call     void Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::FromXml_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.FieldValueDictionary target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11f06  ldnull
0x11f07  ret
0x11f08  ldarg.s  5
0x11f0a  ldc.i4.0
0x11f0b  stind.i1
0x11f0c  ldarg.0
0x11f0d  ldstr    aToxml// "ToXml"
0x11f12  ldarg.s  4
0x11f14  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11f19  ldloc.0
0x11f1a  ldarg.3
0x11f1b  ldarg.s  4
0x11f1d  call     string Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::ToXml_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.FieldValueDictionary target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11f22  ret
0x11f23  ldarg.s  5
0x11f25  ldc.i4.1
0x11f26  stind.i1
0x11f27  ldarg.0
0x11f28  ldstr    aCreateinstance// "CreateInstance"
0x11f2d  ldarg.s  4
0x11f2f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11f34  ldloc.0
0x11f35  ldarg.3
0x11f36  ldarg.s  4
0x11f38  call     void Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::CreateInstance_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.FieldValueDictionary target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11f3d  ldnull
0x11f3e  ret
0x11f3f  ldarg.s  5
0x11f41  ldc.i4.1
0x11f42  stind.i1
0x11f43  ldarg.0
0x11f44  ldstr    aCreatecollecti// "CreateCollectionInstance"
0x11f49  ldarg.s  4
0x11f4b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11f50  ldloc.0
0x11f51  ldarg.3
0x11f52  ldarg.s  4
0x11f54  call     void Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::CreateCollectionInstance_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.FieldValueDictionary target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11f59  ldnull
0x11f5a  ret
0x11f5b  ldarg.s  5
0x11f5d  ldc.i4.0
0x11f5e  stind.i1
0x11f5f  ldarg.0
0x11f60  ldstr    aGetcollections// "GetCollectionSize"
0x11f65  ldarg.s  4
0x11f67  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11f6c  ldloc.0
0x11f6d  ldarg.3
0x11f6e  ldarg.s  4
0x11f70  call     int32 Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::GetCollectionSize_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.FieldValueDictionary target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11f75  box      [mscorlib]System.Int32
0x11f7a  ret
0x11f7b  ldarg.s  5
0x11f7d  ldc.i4.1
0x11f7e  stind.i1
0x11f7f  ldarg.0
0x11f80  ldstr    aSetfieldvalue// "SetFieldValue"
0x11f85  ldarg.s  4
0x11f87  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11f8c  ldloc.0
0x11f8d  ldarg.3
0x11f8e  ldarg.s  4
0x11f90  call     void Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::SetFieldValue_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.FieldValueDictionary target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11f95  ldnull
0x11f96  ret
0x11f97  ldarg.s  5
0x11f99  ldc.i4.0
0x11f9a  stind.i1
0x11f9b  ldarg.0
0x11f9c  ldstr    aGetfieldvalue// "GetFieldValue"
0x11fa1  ldarg.s  4
0x11fa3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11fa8  ldloc.0
0x11fa9  ldarg.3
0x11faa  ldarg.s  4
0x11fac  call     object Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::GetFieldValue_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.FieldValueDictionary target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11fb1  ret
0x11fb2  ldarg.0
0x11fb3  ldarg.1
0x11fb4  ldarg.2
0x11fb5  ldarg.3
0x11fb6  ldarg.s  4
0x11fb8  ldarg.s  5
0x11fba  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x11fbf  ret
```
