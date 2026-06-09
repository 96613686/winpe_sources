# System.Net.Http.Formatting.XmlMediaTypeFormatter::WriteToStream

- ea: `0x9400`
- end: `0x948a`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::WriteToStream`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x93b0`

## callees

- `0x7ff0`
- `0x8000`
- `0x8010`
- `0x90f0`
- `0x9400`
- `0x9490`
- `0x94a0`
- `0x96f0`

## pseudocode

```c

```

## disassembly

```asm
0x9400  ldc.i4.0
0x9401  stloc.0
0x9402  ldarg.0
0x9403  call     instance bool System.Net.Http.Formatting.XmlMediaTypeFormatter::get_UseXmlSerializer()
0x9408  brfalse.s loc_9414
0x940a  ldarga.s 1
0x940c  call     bool System.Net.Http.Formatting.MediaTypeFormatter::TryGetDelegatingTypeForIEnumerableGenericOrSame(class [mscorlib]System.Type& type)
0x9411  stloc.0
0x9412  br.s     loc_941C
0x9414  ldarga.s 1
0x9416  call     bool System.Net.Http.Formatting.MediaTypeFormatter::TryGetDelegatingTypeForIQueryableGenericOrSame(class [mscorlib]System.Type& type)
0x941b  stloc.0
0x941c  ldloc.0
0x941d  brfalse.s loc_9439
0x941f  ldarg.2
0x9420  brfalse.s loc_9439
0x9422  ldarg.1
0x9423  call     class [mscorlib]System.Reflection.ConstructorInfo System.Net.Http.Formatting.MediaTypeFormatter::GetTypeRemappingConstructor(class [mscorlib]System.Type type)
0x9428  ldc.i4.1
0x9429  newarr   [mscorlib]System.Object
0x942e  dup
0x942f  ldc.i4.0
0x9430  ldarg.2
0x9431  stelem.ref
0x9432  callvirt instance object [mscorlib]System.Reflection.ConstructorInfo::Invoke(object[])
0x9437  starg.s  2
0x9439  ldarg.0
0x943a  ldarg.1
0x943b  ldarg.2
0x943c  ldarg.s  4
0x943e  callvirt instance object System.Net.Http.Formatting.XmlMediaTypeFormatter::GetSerializer(class [mscorlib]System.Type type, object value, class [System.Net.Http]System.Net.Http.HttpContent content)
0x9443  stloc.1
0x9444  ldarg.0
0x9445  ldarg.3
0x9446  ldarg.s  4
0x9448  callvirt instance class [System.Xml]System.Xml.XmlWriter System.Net.Http.Formatting.XmlMediaTypeFormatter::CreateXmlWriter(class [mscorlib]System.IO.Stream writeStream, class [System.Net.Http]System.Net.Http.HttpContent content)
0x944d  stloc.2
0x944e  ldloc.1
0x944f  isinst   [System.Xml]System.Xml.Serialization.XmlSerializer
0x9454  stloc.3
0x9455  ldloc.3
0x9456  brfalse.s loc_9462
0x9458  ldloc.3
0x9459  ldloc.2
0x945a  ldarg.2
0x945b  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [System.Xml]System.Xml.XmlWriter, object)
0x9460  leave.s  loc_9489
0x9462  ldloc.1
0x9463  isinst   [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer
0x9468  dup
0x9469  brtrue.s loc_9476
0x946b  ldloc.1
0x946c  ldstr    aGetserializer// "GetSerializer"
0x9471  call     void System.Net.Http.Formatting.XmlMediaTypeFormatter::ThrowInvalidSerializerException(object serializer, string getSerializerMethodName)
0x9476  ldloc.2
0x9477  ldarg.2
0x9478  callvirt instance void [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::WriteObject(class [System.Xml]System.Xml.XmlWriter, object)
0x947d  leave.s  loc_9489
0x947f  ldloc.2
0x9480  brfalse.s loc_9488
0x9482  ldloc.2
0x9483  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9488  endfinally
0x9489  ret
```
