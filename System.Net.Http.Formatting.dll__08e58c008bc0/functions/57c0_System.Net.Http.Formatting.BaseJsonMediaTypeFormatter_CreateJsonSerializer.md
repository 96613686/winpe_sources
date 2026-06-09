# System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CreateJsonSerializer

- ea: `0x57c0`
- end: `0x57cc`
- name: `System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CreateJsonSerializer`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x5770`

## callees

- `0x5500`

## pseudocode

```c

```

## disassembly

```asm
0x57c0  ldarg.0
0x57c1  call     instance class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::get_SerializerSettings()
0x57c6  call     class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Create(class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings)
0x57cb  ret
```
