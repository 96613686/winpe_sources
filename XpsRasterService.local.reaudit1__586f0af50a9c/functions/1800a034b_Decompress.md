# Decompress

- ea: `0x1800a034b`
- end: `0x1800a0351`
- name: `Decompress`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180050a10`

## import_xrefs

- `Cabinet!__imp_Decompress` at `0x1800a034b`

## pseudocode

```c
// attributes: thunk
__int64 Decompress()
{
  return __imp_Decompress();
}

```

## disassembly

```asm
0x1800a034b  jmp     cs:__imp_Decompress
```
