# System.Net.Http.Formatting.BsonMediaTypeFormatter::CreateJsonReader

- ea: `0x5b30`
- end: `0x5ba8`
- name: `System.Net.Http.Formatting.BsonMediaTypeFormatter::CreateJsonReader`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x5b30`
- `0xb3c0`

## string_xrefs

- `0x5b47`: `readStream`

## pseudocode

```c

```

## disassembly

```asm
0x5b30  ldarg.1
0x5b31  ldnull
0x5b32  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5b37  brfalse.s loc_5B44
0x5b39  ldstr    aType// "type"
0x5b3e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x5b43  throw
0x5b44  ldarg.2
0x5b45  brtrue.s loc_5B52
0x5b47  ldstr    aReadstream// "readStream"
0x5b4c  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x5b51  throw
0x5b52  ldarg.3
0x5b53  brtrue.s loc_5B60
0x5b55  ldstr    aEffectiveencod// "effectiveEncoding"
0x5b5a  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x5b5f  throw
0x5b60  ldarg.2
0x5b61  ldarg.3
0x5b62  newobj   instance void [mscorlib]System.IO.BinaryReader::.ctor(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding)
0x5b67  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Bson.BsonReader::.ctor(class [mscorlib]System.IO.BinaryReader)
0x5b6c  stloc.0
0x5b6d  ldloc.0
0x5b6e  ldtoken  [mscorlib]System.Collections.IEnumerable
0x5b73  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5b78  ldarg.1
0x5b79  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x5b7e  brfalse.s loc_5B95
0x5b80  ldtoken  [mscorlib]System.Collections.IDictionary
0x5b85  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5b8a  ldarg.1
0x5b8b  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x5b90  ldc.i4.0
0x5b91  ceq
0x5b93  br.s     loc_5B96
0x5b95  ldc.i4.0
0x5b96  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Bson.BsonReader::set_ReadRootValueAsArray(bool)
0x5b9b  leave.s  loc_5BA6
0x5b9d  pop
0x5b9e  ldloc.0
0x5b9f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ba4  rethrow
0x5ba6  ldloc.0
0x5ba7  ret
```
