# memmove_0

- ea: `0x18002af9c`
- end: `0x18002afa2`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180016f6c`
- `0x180017164`
- `0x18001ec30`
- `0x18001f964`
- `0x18001f9c8`
- `0x180023cf0`
- `0x180023e3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18002af9c`

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
0x18002af9c  jmp     cs:__imp_memmove
```
