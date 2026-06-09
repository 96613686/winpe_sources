# memmove_0

- ea: `0x180008df1`
- end: `0x180008df7`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180006120`
- `0x180007ec0`
- `0x180008010`
- `0x18000dca0`
- `0x1800147d0`
- `0x180014860`
- `0x1800148f0`
- `0x180022ce0`
- `0x180023c0c`
- `0x180023d08`
- `0x180027560`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180008df1`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove_0(void *a1, const void *Src, size_t Size)
{
  return memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x180008df1  jmp     cs:__imp_memmove
```
