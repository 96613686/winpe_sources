# System.Net.Http.Formatting.JsonMediaTypeFormatter::CanWriteType

- ea: `0x7930`
- end: `0x7978`
- name: `System.Net.Http.Formatting.JsonMediaTypeFormatter::CanWriteType`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x55b0`
- `0x77f0`
- `0x7930`
- `0x8000`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x7930  ldarg.1
0x7931  ldnull
0x7932  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7937  brfalse.s loc_7944
0x7939  ldstr    aType// "type"
0x793e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x7943  throw
0x7944  ldarg.0
0x7945  call     instance bool System.Net.Http.Formatting.JsonMediaTypeFormatter::get_UseDataContractJsonSerializer()
0x794a  brfalse.s loc_7970
0x794c  ldarga.s 1
0x794e  call     bool System.Net.Http.Formatting.MediaTypeFormatter::TryGetDelegatingTypeForIQueryableGenericOrSame(class [mscorlib]System.Type& type)
0x7953  pop
0x7954  ldarg.0
0x7955  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer> System.Net.Http.Formatting.JsonMediaTypeFormatter::_dataContractSerializerCache
0x795a  ldarg.1
0x795b  ldarg.0
0x795c  ldftn    instance class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer System.Net.Http.Formatting.JsonMediaTypeFormatter::<CanWriteType>b__21_0(class [mscorlib]System.Type t)
0x7962  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Type, class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer>::.ctor(object, native int)
0x7967  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer>::GetOrAdd(void, var<u1>)
0x796c  ldnull
0x796d  cgt.un
0x796f  ret
0x7970  ldarg.0
0x7971  ldarg.1
0x7972  call     instance bool System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CanWriteType(class [mscorlib]System.Type type)
0x7977  ret
```
