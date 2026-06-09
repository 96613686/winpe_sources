# System.Net.Http.Formatting.JsonContractResolver::.ctor

- ea: `0x6950`
- end: `0x6973`
- name: `System.Net.Http.Formatting.JsonContractResolver::.ctor`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x5480`

## callees

- `0x6950`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x6950  ldarg.0
0x6951  call     instance void [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver::.ctor()
0x6956  ldarg.1
0x6957  brtrue.s loc_6964
0x6959  ldstr    aFormatter// "formatter"
0x695e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x6963  throw
0x6964  ldarg.0
0x6965  ldarg.1
0x6966  stfld    class System.Net.Http.Formatting.MediaTypeFormatter System.Net.Http.Formatting.JsonContractResolver::_formatter
0x696b  ldarg.0
0x696c  ldc.i4.0
0x696d  call     instance void [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver::set_IgnoreSerializableAttribute(bool)
0x6972  ret
```
