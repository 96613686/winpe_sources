# System.Net.Http.Formatting.JsonMediaTypeFormatter::WriteToStream

- ea: `0x7a60`
- end: `0x7aee`
- name: `System.Net.Http.Formatting.JsonMediaTypeFormatter::WriteToStream`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x5840`
- `0x77f0`
- `0x7a60`
- `0x7ba0`
- `0x8000`
- `0x8010`
- `0xb3c0`

## string_xrefs

- `0x7a77`: `writeStream`

## pseudocode

```c

```

## disassembly

```asm
0x7a60  ldarg.1
0x7a61  ldnull
0x7a62  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7a67  brfalse.s loc_7A74
0x7a69  ldstr    aType// "type"
0x7a6e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x7a73  throw
0x7a74  ldarg.3
0x7a75  brtrue.s loc_7A82
0x7a77  ldstr    aWritestream// "writeStream"
0x7a7c  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x7a81  throw
0x7a82  ldarg.s  4
0x7a84  brtrue.s loc_7A91
0x7a86  ldstr    aEffectiveencod// "effectiveEncoding"
0x7a8b  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x7a90  throw
0x7a91  ldarg.0
0x7a92  call     instance bool System.Net.Http.Formatting.JsonMediaTypeFormatter::get_UseDataContractJsonSerializer()
0x7a97  brfalse.s loc_7AE2
0x7a99  ldarga.s 1
0x7a9b  call     bool System.Net.Http.Formatting.MediaTypeFormatter::TryGetDelegatingTypeForIQueryableGenericOrSame(class [mscorlib]System.Type& type)
0x7aa0  brfalse.s loc_7ABC
0x7aa2  ldarg.2
0x7aa3  brfalse.s loc_7ABC
0x7aa5  ldarg.1
0x7aa6  call     class [mscorlib]System.Reflection.ConstructorInfo System.Net.Http.Formatting.MediaTypeFormatter::GetTypeRemappingConstructor(class [mscorlib]System.Type type)
0x7aab  ldc.i4.1
0x7aac  newarr   [mscorlib]System.Object
0x7ab1  dup
0x7ab2  ldc.i4.0
0x7ab3  ldarg.2
0x7ab4  stelem.ref
0x7ab5  callvirt instance object [mscorlib]System.Reflection.ConstructorInfo::Invoke(object[])
0x7aba  starg.s  2
0x7abc  ldarg.0
0x7abd  ldarg.1
0x7abe  call     instance class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer System.Net.Http.Formatting.JsonMediaTypeFormatter::GetDataContractSerializer(class [mscorlib]System.Type type)
0x7ac3  stloc.0
0x7ac4  ldarg.3
0x7ac5  ldarg.s  4
0x7ac7  ldc.i4.0
0x7ac8  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter [System.Runtime.Serialization]System.Runtime.Serialization.Json.JsonReaderWriterFactory::CreateJsonWriter(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding, bool)
0x7acd  stloc.1
0x7ace  ldloc.0
0x7acf  ldloc.1
0x7ad0  ldarg.2
0x7ad1  callvirt instance void [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::WriteObject(class [System.Xml]System.Xml.XmlWriter, object)
0x7ad6  leave.s  loc_7AED
0x7ad8  ldloc.1
0x7ad9  brfalse.s loc_7AE1
0x7adb  ldloc.1
0x7adc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7ae1  endfinally
0x7ae2  ldarg.0
0x7ae3  ldarg.1
0x7ae4  ldarg.2
0x7ae5  ldarg.3
0x7ae6  ldarg.s  4
0x7ae8  call     instance void System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::WriteToStream(class [mscorlib]System.Type type, object value, class [mscorlib]System.IO.Stream writeStream, class [mscorlib]System.Text.Encoding effectiveEncoding)
0x7aed  ret
```
