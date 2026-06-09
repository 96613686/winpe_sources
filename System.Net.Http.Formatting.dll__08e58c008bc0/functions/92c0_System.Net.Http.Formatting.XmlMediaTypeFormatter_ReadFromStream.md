# System.Net.Http.Formatting.XmlMediaTypeFormatter::ReadFromStream

- ea: `0x92c0`
- end: `0x936f`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::ReadFromStream`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x9280`

## callees

- `0x6910`
- `0x81f0`
- `0x92c0`
- `0x9370`
- `0x9380`
- `0x96f0`

## string_xrefs

- `0x932b`: `GetDeserializer`

## pseudocode

```c

```

## disassembly

```asm
0x92c0  ldarg.3
0x92c1  brfalse.s loc_92CB
0x92c3  ldarg.3
0x92c4  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x92c9  br.s     loc_92CC
0x92cb  ldnull
0x92cc  stloc.0
0x92cd  ldloc.0
0x92ce  brfalse.s loc_92F5
0x92d0  ldloc.0
0x92d1  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentLength()
0x92d6  stloc.2
0x92d7  ldc.i4.0
0x92d8  conv.i8
0x92d9  stloc.3
0x92da  ldloca.s 2
0x92dc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::GetValueOrDefault()
0x92e1  ldloc.3
0x92e2  ceq
0x92e4  ldloca.s 2
0x92e6  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x92eb  and
0x92ec  brfalse.s loc_92F5
0x92ee  ldarg.1
0x92ef  call     object System.Net.Http.Formatting.MediaTypeFormatter::GetDefaultValueForType(class [mscorlib]System.Type type)
0x92f4  ret
0x92f5  ldarg.0
0x92f6  ldarg.1
0x92f7  ldarg.3
0x92f8  callvirt instance object System.Net.Http.Formatting.XmlMediaTypeFormatter::GetDeserializer(class [mscorlib]System.Type type, class [System.Net.Http]System.Net.Http.HttpContent content)
0x92fd  stloc.1
0x92fe  ldarg.0
0x92ff  ldarg.2
0x9300  ldarg.3
0x9301  callvirt instance class [System.Xml]System.Xml.XmlReader System.Net.Http.Formatting.XmlMediaTypeFormatter::CreateXmlReader(class [mscorlib]System.IO.Stream readStream, class [System.Net.Http]System.Net.Http.HttpContent content)
0x9306  stloc.s  4
0x9308  ldloc.1
0x9309  isinst   [System.Xml]System.Xml.Serialization.XmlSerializer
0x930e  stloc.s  5
0x9310  ldloc.s  5
0x9312  brfalse.s loc_9321
0x9314  ldloc.s  5
0x9316  ldloc.s  4
0x9318  callvirt instance object [System.Xml]System.Xml.Serialization.XmlSerializer::Deserialize(class [System.Xml]System.Xml.XmlReader)
0x931d  stloc.s  6
0x931f  leave.s  loc_936C
0x9321  ldloc.1
0x9322  isinst   [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer
0x9327  dup
0x9328  brtrue.s loc_9335
0x932a  ldloc.1
0x932b  ldstr    aGetdeserialize// "GetDeserializer"
0x9330  call     void System.Net.Http.Formatting.XmlMediaTypeFormatter::ThrowInvalidSerializerException(object serializer, string getSerializerMethodName)
0x9335  ldloc.s  4
0x9337  callvirt instance object [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::ReadObject(class [System.Xml]System.Xml.XmlReader)
0x933c  stloc.s  6
0x933e  leave.s  loc_936C
0x9340  ldloc.s  4
0x9342  brfalse.s loc_934B
0x9344  ldloc.s  4
0x9346  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x934b  endfinally
0x934c  stloc.s  7
0x934e  ldarg.s  4
0x9350  brtrue.s loc_9354
0x9352  rethrow
0x9354  ldarg.s  4
0x9356  ldsfld   string [mscorlib]System.String::Empty
0x935b  ldloc.s  7
0x935d  callvirt instance void System.Net.Http.Formatting.IFormatterLogger::LogError(string errorPath, class [mscorlib]System.Exception exception)
0x9362  ldarg.1
0x9363  call     object System.Net.Http.Formatting.MediaTypeFormatter::GetDefaultValueForType(class [mscorlib]System.Type type)
0x9368  stloc.s  6
0x936a  leave.s  loc_936C
0x936c  ldloc.s  6
0x936e  ret
```
