# memmove_0

- ea: `0x140001de2`
- end: `0x140001de8`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140007b20`
- `0x140007df8`

## import_xrefs

- `msvcrt!memmove` at `0x140001de2`

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
0x140001de2  jmp     cs:__imp_memmove
```
