# System.Net.Http.Formatting.JsonMediaTypeFormatter::ReadFromStream

- ea: `0x7980`
- end: `0x79f6`
- name: `System.Net.Http.Formatting.JsonMediaTypeFormatter::ReadFromStream`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x5220`
- `0x5680`
- `0x77f0`
- `0x7980`
- `0x7ba0`
- `0xb3c0`

## string_xrefs

- `0x7997`: `readStream`

## pseudocode

```c

```

## disassembly

```asm
0x7980  ldarg.1
0x7981  ldnull
0x7982  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7987  brfalse.s loc_7994
0x7989  ldstr    aType// "type"
0x798e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x7993  throw
0x7994  ldarg.2
0x7995  brtrue.s loc_79A2
0x7997  ldstr    aReadstream// "readStream"
0x799c  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x79a1  throw
0x79a2  ldarg.3
0x79a3  brtrue.s loc_79B0
0x79a5  ldstr    aEffectiveencod// "effectiveEncoding"
0x79aa  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x79af  throw
0x79b0  ldarg.0
0x79b1  call     instance bool System.Net.Http.Formatting.JsonMediaTypeFormatter::get_UseDataContractJsonSerializer()
0x79b6  brfalse.s loc_79E8
0x79b8  ldarg.0
0x79b9  ldarg.1
0x79ba  call     instance class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer System.Net.Http.Formatting.JsonMediaTypeFormatter::GetDataContractSerializer(class [mscorlib]System.Type type)
0x79bf  stloc.0
0x79c0  ldarg.2
0x79c1  newobj   instance void System.Net.Http.Internal.NonClosingDelegatingStream::.ctor(class [mscorlib]System.IO.Stream innerStream)
0x79c6  ldarg.3
0x79c7  ldarg.0
0x79c8  ldfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas System.Net.Http.Formatting.JsonMediaTypeFormatter::_readerQuotas
0x79cd  ldnull
0x79ce  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryReader [System.Runtime.Serialization]System.Runtime.Serialization.Json.JsonReaderWriterFactory::CreateJsonReader(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding, class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas, class [System.Runtime.Serialization]System.Xml.OnXmlDictionaryReaderClose)
0x79d3  stloc.1
0x79d4  ldloc.0
0x79d5  ldloc.1
0x79d6  callvirt instance object [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::ReadObject(class [System.Xml]System.Xml.XmlReader)
0x79db  stloc.2
0x79dc  leave.s  loc_79F4
0x79de  ldloc.1
0x79df  brfalse.s loc_79E7
0x79e1  ldloc.1
0x79e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x79e7  endfinally
0x79e8  ldarg.0
0x79e9  ldarg.1
0x79ea  ldarg.2
0x79eb  ldarg.3
0x79ec  ldarg.s  4
0x79ee  call     instance object System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::ReadFromStream(class [mscorlib]System.Type type, class [mscorlib]System.IO.Stream readStream, class [mscorlib]System.Text.Encoding effectiveEncoding, class System.Net.Http.Formatting.IFormatterLogger formatterLogger)
0x79f3  ret
0x79f4  ldloc.2
0x79f5  ret
```
