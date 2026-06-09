# System.Net.Http.Formatting.BsonMediaTypeFormatter::CreateJsonWriter

- ea: `0x5c50`
- end: `0x5c8d`
- name: `System.Net.Http.Formatting.BsonMediaTypeFormatter::CreateJsonWriter`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x5c50`
- `0xb3c0`

## string_xrefs

- `0x5c67`: `writeStream`

## pseudocode

```c

```

## disassembly

```asm
0x5c50  ldarg.1
0x5c51  ldnull
0x5c52  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5c57  brfalse.s loc_5C64
0x5c59  ldstr    aType// "type"
0x5c5e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x5c63  throw
0x5c64  ldarg.2
0x5c65  brtrue.s loc_5C72
0x5c67  ldstr    aWritestream// "writeStream"
0x5c6c  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x5c71  throw
0x5c72  ldarg.3
0x5c73  brtrue.s loc_5C80
0x5c75  ldstr    aEffectiveencod// "effectiveEncoding"
0x5c7a  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x5c7f  throw
0x5c80  ldarg.2
0x5c81  ldarg.3
0x5c82  newobj   instance void [mscorlib]System.IO.BinaryWriter::.ctor(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding)
0x5c87  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Bson.BsonWriter::.ctor(class [mscorlib]System.IO.BinaryWriter)
0x5c8c  ret
```
