# System.Net.Http.Formatting.XmlMediaTypeFormatter::CanReadType

- ea: `0x9220`
- end: `0x9240`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::CanReadType`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x9220`
- `0x9600`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x9220  ldarg.1
0x9221  ldnull
0x9222  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9227  brfalse.s loc_9234
0x9229  ldstr    aType// "type"
0x922e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x9233  throw
0x9234  ldarg.0
0x9235  ldarg.1
0x9236  ldc.i4.0
0x9237  call     instance object System.Net.Http.Formatting.XmlMediaTypeFormatter::GetCachedSerializer(class [mscorlib]System.Type type, bool throwOnError)
0x923c  ldnull
0x923d  cgt.un
0x923f  ret
```
