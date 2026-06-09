# memmove_0

- ea: `0x180003db5`
- end: `0x180003dbb`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800075b0`
- `0x180015e28`
- `0x180016d00`
- `0x18001c870`
- `0x180024e8c`
- `0x180028b14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180003db5`

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
0x180003db5  jmp     cs:__imp_memmove
```
