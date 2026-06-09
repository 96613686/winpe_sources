# memmove_0

- ea: `0x18001b2fe`
- end: `0x18001b304`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180006d54`
- `0x180006e54`

## import_xrefs

- `msvcrt!memmove` at `0x18001b2fe`

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
0x18001b2fe  jmp     cs:__imp_memmove
```
