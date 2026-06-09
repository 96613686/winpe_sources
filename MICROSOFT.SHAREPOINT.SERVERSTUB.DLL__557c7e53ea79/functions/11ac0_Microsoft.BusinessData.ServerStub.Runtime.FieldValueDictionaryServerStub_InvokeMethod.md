# Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::InvokeMethod

- ea: `0x11ac0`
- end: `0x11c70`
- name: `Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::InvokeMethod`
- size: `432`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x119c0`
- `0x119e0`
- `0x119f0`
- `0x11a20`
- `0x11a50`
- `0x11a70`
- `0x11aa0`
- `0x11ac0`

## string_xrefs

- `0x11b1f`: `CreateInstance`
- `0x11bd8`: `CreateInstance`
- `0x11b2b`: `CreateCollectionInstance`
- `0x11bf4`: `CreateCollectionInstance`
- `0x11b07`: `FromXml`
- `0x11ba1`: `FromXml`
- `0x11b13`: `ToXml`
- `0x11bbd`: `ToXml`

## pseudocode

```c

```

## disassembly

```asm
0x11ac0  ldarg.s  4
0x11ac2  brtrue.s loc_11ACF
0x11ac4  ldstr    aProxycontext// "proxyContext"
0x11ac9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11ace  throw
0x11acf  ldarg.1
0x11ad0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.FieldValueDictionary
0x11ad5  stloc.0
0x11ad6  ldloc.0
0x11ad7  brtrue.s loc_11AE4
0x11ad9  ldstr    aTarget// "target"
0x11ade  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11ae3  throw
0x11ae4  ldarg.0
0x11ae5  ldarg.2
0x11ae6  ldarg.s  4
0x11ae8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11aed  starg.s  2
0x11aef  ldarg.2
0x11af0  dup
0x11af1  stloc.1
0x11af2  brfalse  loc_11C62
0x11af7  volatile.
0x11af9  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60002ee-1
0x11afe  brtrue.s loc_11B61
0x11b00  ldc.i4.7
0x11b01  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x11b06  dup
0x11b07  ldstr    aFromxml// "FromXml"
0x11b0c  ldc.i4.0
0x11b0d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11b12  dup
0x11b13  ldstr    aToxml// "ToXml"
0x11b18  ldc.i4.1
0x11b19  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11b1e  dup
0x11b1f  ldstr    aCreateinstance// "CreateInstance"
0x11b24  ldc.i4.2
0x11b25  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11b2a  dup
0x11b2b  ldstr    aCreatecollecti// "CreateCollectionInstance"
0x11b30  ldc.i4.3
0x11b31  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11b36  dup
0x11b37  ldstr    aGetcollections// "GetCollectionSize"
0x11b3c  ldc.i4.4
0x11b3d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11b42  dup
0x11b43  ldstr    aSetfieldvalue// "SetFieldValue"
0x11b48  ldc.i4.5
0x11b49  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11b4e  dup
0x11b4f  ldstr    aGetfieldvalue// "GetFieldValue"
0x11b54  ldc.i4.6
0x11b55  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11b5a  volatile.
0x11b5c  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60002ee-1
0x11b61  volatile.
0x11b63  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60002ee-1
0x11b68  ldloc.1
0x11b69  ldloca.s 2
0x11b6b  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x11b70  brfalse  loc_11C62
0x11b75  ldloc.2
0x11b76  switch   loc_11B9C, loc_11BB8, loc_11BD3, loc_11BEF, loc_11C0B, loc_11C2B, loc_11C47
0x11b97  br       loc_11C62
0x11b9c  ldarg.s  5
0x11b9e  ldc.i4.1
0x11b9f  stind.i1
0x11ba0  ldarg.0
0x11ba1  ldstr    aFromxml// "FromXml"
0x11ba6  ldarg.s  4
0x11ba8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11bad  ldloc.0
0x11bae  ldarg.3
0x11baf  ldarg.s  4
0x11bb1  call     void Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::FromXml_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.FieldValueDictionary target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11bb6  ldnull
0x11bb7  ret
0x11bb8  ldarg.s  5
0x11bba  ldc.i4.0
0x11bbb  stind.i1
0x11bbc  ldarg.0
0x11bbd  ldstr    aToxml// "ToXml"
0x11bc2  ldarg.s  4
0x11bc4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11bc9  ldloc.0
0x11bca  ldarg.3
0x11bcb  ldarg.s  4
0x11bcd  call     string Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::ToXml_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.FieldValueDictionary target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11bd2  ret
0x11bd3  ldarg.s  5
0x11bd5  ldc.i4.1
0x11bd6  stind.i1
0x11bd7  ldarg.0
0x11bd8  ldstr    aCreateinstance// "CreateInstance"
0x11bdd  ldarg.s  4
0x11bdf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11be4  ldloc.0
0x11be5  ldarg.3
0x11be6  ldarg.s  4
0x11be8  call     void Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::CreateInstance_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.FieldValueDictionary target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11bed  ldnull
0x11bee  ret
0x11bef  ldarg.s  5
0x11bf1  ldc.i4.1
0x11bf2  stind.i1
0x11bf3  ldarg.0
0x11bf4  ldstr    aCreatecollecti// "CreateCollectionInstance"
0x11bf9  ldarg.s  4
0x11bfb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11c00  ldloc.0
0x11c01  ldarg.3
0x11c02  ldarg.s  4
0x11c04  call     void Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::CreateCollectionInstance_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.FieldValueDictionary target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11c09  ldnull
0x11c0a  ret
0x11c0b  ldarg.s  5
0x11c0d  ldc.i4.0
0x11c0e  stind.i1
0x11c0f  ldarg.0
0x11c10  ldstr    aGetcollections// "GetCollectionSize"
0x11c15  ldarg.s  4
0x11c17  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11c1c  ldloc.0
0x11c1d  ldarg.3
0x11c1e  ldarg.s  4
0x11c20  call     int32 Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::GetCollectionSize_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.FieldValueDictionary target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11c25  box      [mscorlib]System.Int32
0x11c2a  ret
0x11c2b  ldarg.s  5
0x11c2d  ldc.i4.1
0x11c2e  stind.i1
0x11c2f  ldarg.0
0x11c30  ldstr    aSetfieldvalue// "SetFieldValue"
0x11c35  ldarg.s  4
0x11c37  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11c3c  ldloc.0
0x11c3d  ldarg.3
0x11c3e  ldarg.s  4
0x11c40  call     void Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::SetFieldValue_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.FieldValueDictionary target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11c45  ldnull
0x11c46  ret
0x11c47  ldarg.s  5
0x11c49  ldc.i4.0
0x11c4a  stind.i1
0x11c4b  ldarg.0
0x11c4c  ldstr    aGetfieldvalue// "GetFieldValue"
0x11c51  ldarg.s  4
0x11c53  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11c58  ldloc.0
0x11c59  ldarg.3
0x11c5a  ldarg.s  4
0x11c5c  call     object Microsoft.BusinessData.ServerStub.Runtime.FieldValueDictionaryServerStub::GetFieldValue_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.Runtime.FieldValueDictionary target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11c61  ret
0x11c62  ldarg.0
0x11c63  ldarg.1
0x11c64  ldarg.2
0x11c65  ldarg.3
0x11c66  ldarg.s  4
0x11c68  ldarg.s  5
0x11c6a  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x11c6f  ret
```
