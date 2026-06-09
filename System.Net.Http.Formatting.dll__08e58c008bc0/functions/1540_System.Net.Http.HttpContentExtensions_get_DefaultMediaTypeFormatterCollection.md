# System.Net.Http.HttpContentExtensions::get_DefaultMediaTypeFormatterCollection

- ea: `0x1540`
- end: `0x1557`
- name: `System.Net.Http.HttpContentExtensions::get_DefaultMediaTypeFormatterCollection`
- size: `23`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1560`
- `0x1570`
- `0x15c0`
- `0x15d0`

## callees

- `0x1540`
- `0x8270`

## pseudocode

```c

```

## disassembly

```asm
0x1540  ldsfld   class System.Net.Http.Formatting.MediaTypeFormatterCollection System.Net.Http.HttpContentExtensions::_defaultMediaTypeFormatterCollection
0x1545  brtrue.s loc_1551
0x1547  newobj   instance void System.Net.Http.Formatting.MediaTypeFormatterCollection::.ctor()
0x154c  stsfld   class System.Net.Http.Formatting.MediaTypeFormatterCollection System.Net.Http.HttpContentExtensions::_defaultMediaTypeFormatterCollection
0x1551  ldsfld   class System.Net.Http.Formatting.MediaTypeFormatterCollection System.Net.Http.HttpContentExtensions::_defaultMediaTypeFormatterCollection
0x1556  ret
```
