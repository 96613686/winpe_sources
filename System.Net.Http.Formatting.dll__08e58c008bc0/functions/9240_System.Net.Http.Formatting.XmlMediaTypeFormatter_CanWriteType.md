# System.Net.Http.Formatting.XmlMediaTypeFormatter::CanWriteType

- ea: `0x9240`
- end: `0x927a`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::CanWriteType`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x7ff0`
- `0x8000`
- `0x90f0`
- `0x9240`
- `0x9600`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x9240  ldarg.1
0x9241  ldnull
0x9242  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9247  brfalse.s loc_9254
0x9249  ldstr    aType// "type"
0x924e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x9253  throw
0x9254  ldarg.0
0x9255  call     instance bool System.Net.Http.Formatting.XmlMediaTypeFormatter::get_UseXmlSerializer()
0x925a  brfalse.s loc_9266
0x925c  ldarga.s 1
0x925e  call     bool System.Net.Http.Formatting.MediaTypeFormatter::TryGetDelegatingTypeForIEnumerableGenericOrSame(class [mscorlib]System.Type& type)
0x9263  pop
0x9264  br.s     loc_926E
0x9266  ldarga.s 1
0x9268  call     bool System.Net.Http.Formatting.MediaTypeFormatter::TryGetDelegatingTypeForIQueryableGenericOrSame(class [mscorlib]System.Type& type)
0x926d  pop
0x926e  ldarg.0
0x926f  ldarg.1
0x9270  ldc.i4.0
0x9271  call     instance object System.Net.Http.Formatting.XmlMediaTypeFormatter::GetCachedSerializer(class [mscorlib]System.Type type, bool throwOnError)
0x9276  ldnull
0x9277  cgt.un
0x9279  ret
```
