# System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::set_SerializerSettings

- ea: `0x5510`
- end: `0x5526`
- name: `System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::set_SerializerSettings`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x54d0`

## callees

- `0x5510`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x5510  ldarg.1
0x5511  brtrue.s loc_551E
0x5513  ldstr    aValue// "value"
0x5518  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x551d  throw
0x551e  ldarg.0
0x551f  ldarg.1
0x5520  stfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::_jsonSerializerSettings
0x5525  ret
```
