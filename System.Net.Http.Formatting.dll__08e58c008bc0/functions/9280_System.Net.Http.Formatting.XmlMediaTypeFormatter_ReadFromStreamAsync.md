# System.Net.Http.Formatting.XmlMediaTypeFormatter::ReadFromStreamAsync

- ea: `0x9280`
- end: `0x92c0`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::ReadFromStreamAsync`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x9280`
- `0x92c0`
- `0xb3c0`

## string_xrefs

- `0x9297`: `readStream`

## pseudocode

```c

```

## disassembly

```asm
0x9280  ldarg.1
0x9281  ldnull
0x9282  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9287  brfalse.s loc_9294
0x9289  ldstr    aType// "type"
0x928e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x9293  throw
0x9294  ldarg.2
0x9295  brtrue.s loc_92A2
0x9297  ldstr    aReadstream// "readStream"
0x929c  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x92a1  throw
0x92a2  nop
0x92a3  ldarg.0
0x92a4  ldarg.1
0x92a5  ldarg.2
0x92a6  ldarg.3
0x92a7  ldarg.s  4
0x92a9  call     instance object System.Net.Http.Formatting.XmlMediaTypeFormatter::ReadFromStream(class [mscorlib]System.Type type, class [mscorlib]System.IO.Stream readStream, class [System.Net.Http]System.Net.Http.HttpContent content, class System.Net.Http.Formatting.IFormatterLogger formatterLogger)
0x92ae  call     T0x2B000041
0x92b3  stloc.0
0x92b4  leave.s  loc_92BE
0x92b6  call     T0x2B000042
0x92bb  stloc.0
0x92bc  leave.s  loc_92BE
0x92be  ldloc.0
0x92bf  ret
```
