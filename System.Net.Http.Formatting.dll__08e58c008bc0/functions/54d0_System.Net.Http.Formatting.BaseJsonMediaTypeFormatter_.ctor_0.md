# System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::.ctor_0

- ea: `0x54d0`
- end: `0x54fb`
- name: `System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::.ctor_0`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x5920`
- `0x77a0`

## callees

- `0x5500`
- `0x5510`
- `0x5540`
- `0x7da0`

## pseudocode

```c

```

## disassembly

```asm
0x54d0  ldarg.0
0x54d1  ldc.i4   0x100
0x54d6  stfld    int32 System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::_maxDepth
0x54db  ldarg.0
0x54dc  ldarg.1
0x54dd  call     instance void System.Net.Http.Formatting.MediaTypeFormatter::.ctor(class System.Net.Http.Formatting.MediaTypeFormatter formatter)
0x54e2  ldarg.0
0x54e3  ldarg.1
0x54e4  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::get_SerializerSettings()
0x54e9  call     instance void System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::set_SerializerSettings(class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings value)
0x54ee  ldarg.0
0x54ef  ldarg.1
0x54f0  ldfld    int32 System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::_maxDepth
0x54f5  callvirt instance void System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::set_MaxDepth(int32 value)
0x54fa  ret
```
