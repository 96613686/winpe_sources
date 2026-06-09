# memmove_0

- ea: `0x180034cb2`
- end: `0x180034cb8`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180005d74`
- `0x180007360`
- `0x180033c5c`

## import_xrefs

- `msvcrt!memmove` at `0x180034cb2`

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
0x180034cb2  jmp     cs:__imp_memmove
```
