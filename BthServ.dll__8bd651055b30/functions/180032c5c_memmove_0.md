# memmove_0

- ea: `0x180032c5c`
- end: `0x180032c62`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180006fe8`
- `0x180013644`
- `0x180013970`
- `0x180013bd4`
- `0x18002afc4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180032c5c`

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
0x180032c5c  jmp     cs:__imp_memmove
```
