# memmove_0

- ea: `0x1800127fe`
- end: `0x180012804`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d694`

## import_xrefs

- `msvcrt!memmove` at `0x1800127fe`

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
0x1800127fe  jmp     cs:__imp_memmove
```
