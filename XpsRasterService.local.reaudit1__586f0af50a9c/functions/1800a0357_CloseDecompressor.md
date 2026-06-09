# CloseDecompressor

- ea: `0x1800a0357`
- end: `0x1800a035d`
- name: `CloseDecompressor`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180050a10`

## import_xrefs

- `Cabinet!__imp_CloseDecompressor` at `0x1800a0357`

## pseudocode

```c
// attributes: thunk
__int64 CloseDecompressor()
{
  return __imp_CloseDecompressor();
}

```

## disassembly

```asm
0x1800a0357  jmp     cs:__imp_CloseDecompressor
```
