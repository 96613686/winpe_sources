# memmove_0

- ea: `0x180001bc2`
- end: `0x180001bc8`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180005b7c`
- `0x1800063f4`
- `0x180007ae4`
- `0x180008190`
- `0x18000822c`

## import_xrefs

- `msvcrt!memmove` at `0x180001bc2`

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
0x180001bc2  jmp     cs:__imp_memmove
```
