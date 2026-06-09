# System.Net.Http.Formatting.JsonMediaTypeFormatter::CreateJsonReader

- ea: `0x7860`
- end: `0x789d`
- name: `System.Net.Http.Formatting.JsonMediaTypeFormatter::CreateJsonReader`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x7860`
- `0xb3c0`

## string_xrefs

- `0x7877`: `readStream`

## pseudocode

```c

```

## disassembly

```asm
0x7860  ldarg.1
0x7861  ldnull
0x7862  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7867  brfalse.s loc_7874
0x7869  ldstr    aType// "type"
0x786e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x7873  throw
0x7874  ldarg.2
0x7875  brtrue.s loc_7882
0x7877  ldstr    aReadstream// "readStream"
0x787c  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x7881  throw
0x7882  ldarg.3
0x7883  brtrue.s loc_7890
0x7885  ldstr    aEffectiveencod// "effectiveEncoding"
0x788a  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x788f  throw
0x7890  ldarg.2
0x7891  ldarg.3
0x7892  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding)
0x7897  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader::.ctor(class [mscorlib]System.IO.TextReader)
0x789c  ret
```
