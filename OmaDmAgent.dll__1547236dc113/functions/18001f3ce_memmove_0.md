# memmove_0

- ea: `0x18001f3ce`
- end: `0x18001f3d4`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180006870`
- `0x180006a80`

## import_xrefs

- `msvcrt!memmove` at `0x18001f3ce`

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
0x18001f3ce  jmp     cs:__imp_memmove
```
