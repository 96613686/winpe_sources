# System.Net.Http.Formatting.JsonMediaTypeFormatter::CreateDataContractSerializer_0

- ea: `0x7b80`
- end: `0x7b9b`
- name: `System.Net.Http.Formatting.JsonMediaTypeFormatter::CreateDataContractSerializer_0`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x7af0`

## callees

- `0x7b80`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x7b80  ldarg.1
0x7b81  ldnull
0x7b82  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7b87  brfalse.s loc_7B94
0x7b89  ldstr    aType// "type"
0x7b8e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x7b93  throw
0x7b94  ldarg.1
0x7b95  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer::.ctor(class [mscorlib]System.Type)
0x7b9a  ret
```
