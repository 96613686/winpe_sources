# CreateDecompressor

- ea: `0x1800a033f`
- end: `0x1800a0345`
- name: `CreateDecompressor`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180050a10`

## import_xrefs

- `Cabinet!__imp_CreateDecompressor` at `0x1800a033f`

## pseudocode

```c
// attributes: thunk
__int64 CreateDecompressor()
{
  return __imp_CreateDecompressor();
}

```

## disassembly

```asm
0x1800a033f  jmp     cs:__imp_CreateDecompressor
```
