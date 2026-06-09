# System.Net.Http.Formatting.JsonMediaTypeFormatter::CanReadType

- ea: `0x78f0`
- end: `0x7930`
- name: `System.Net.Http.Formatting.JsonMediaTypeFormatter::CanReadType`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x5590`
- `0x77f0`
- `0x78f0`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x78f0  ldarg.1
0x78f1  ldnull
0x78f2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x78f7  brfalse.s loc_7904
0x78f9  ldstr    aType// "type"
0x78fe  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x7903  throw
0x7904  ldarg.0
0x7905  call     instance bool System.Net.Http.Formatting.JsonMediaTypeFormatter::get_UseDataContractJsonSerializer()
0x790a  brfalse.s loc_7928
0x790c  ldarg.0
0x790d  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer> System.Net.Http.Formatting.JsonMediaTypeFormatter::_dataContractSerializerCache
0x7912  ldarg.1
0x7913  ldarg.0
0x7914  ldftn    instance class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer System.Net.Http.Formatting.JsonMediaTypeFormatter::<CanReadType>b__20_0(class [mscorlib]System.Type t)
0x791a  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Type, class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer>::.ctor(object, native int)
0x791f  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer>::GetOrAdd(void, var<u1>)
0x7924  ldnull
0x7925  cgt.un
0x7927  ret
0x7928  ldarg.0
0x7929  ldarg.1
0x792a  call     instance bool System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CanReadType(class [mscorlib]System.Type type)
0x792f  ret
```
