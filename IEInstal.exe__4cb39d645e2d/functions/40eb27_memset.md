# _memset

- ea: `0x40eb27`
- end: `0x40eb2d`
- name: `_memset`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `31`
- callee_count: `0`
- tags: ``

## callers

- `0x40285e`
- `0x402918`
- `0x403291`
- `0x40373b`
- `0x404214`
- `0x4044ae`
- `0x405304`
- `0x406266`
- `0x4063af`
- `0x40663b`
- `0x406c66`
- `0x406e8a`
- `0x406f2f`
- `0x406fdc`
- `0x407142`
- `0x40723a`
- `0x4072e3`
- `0x40784b`
- `0x408fe0`
- `0x409551`
- `0x409a59`
- `0x409b68`
- `0x409c72`
- `0x40a422`
- `0x40acb0`
- `0x40b164`
- `0x40c77f`
- `0x40d1e0`
- `0x40d480`
- `0x40d4b0`
- `0x40de00`

## import_xrefs

- `msvcrt!memset` at `0x40eb27`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset(void *a1, int Val, size_t Size)
{
  return _memset(a1, Val, Size);
}

```

## disassembly

```asm
0x40eb27  jmp     ds:__imp__memset
```
