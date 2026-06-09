# memmove_0

- ea: `0x18003d4be`
- end: `0x18003d4c4`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180033668`
- `0x18003372c`
- `0x180033a24`
- `0x180033af4`
- `0x180033ea4`

## import_xrefs

- `msvcrt!memmove` at `0x18003d4be`

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
0x18003d4be  jmp     cs:__imp_memmove
```
