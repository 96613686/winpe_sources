# System.Net.Http.Formatting.MediaTypeHeaderValueExtensions::IsSubsetOf

- ea: `0x5ce0`
- end: `0x5cea`
- name: `System.Net.Http.Formatting.MediaTypeHeaderValueExtensions::IsSubsetOf`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x7240`
- `0x83f0`
- `0x8490`

## callees

- `0x5cf0`

## pseudocode

```c

```

## disassembly

```asm
0x5ce0  ldarg.0
0x5ce1  ldarg.1
0x5ce2  ldloca.s 0
0x5ce4  call     bool System.Net.Http.Formatting.MediaTypeHeaderValueExtensions::IsSubsetOf(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaType1, class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaType2, [out] valuetype System.Net.Http.Formatting.MediaTypeHeaderValueRange& mediaType2Range)
0x5ce9  ret
```
