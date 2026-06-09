# memmove

- ea: `0x1400649fe`
- end: `0x140064a04`
- name: `memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x14000e6e0`
- `0x14000e7a4`
- `0x14000e88c`
- `0x1400169d4`
- `0x140016ab4`
- `0x14001b66c`
- `0x14001b858`
- `0x14001d22c`
- `0x14001d2f8`

## import_xrefs

- `msvcrt!memmove` at `0x1400649fe`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
{
  return __imp_memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x1400649fe  jmp     cs:__imp_memmove
```
