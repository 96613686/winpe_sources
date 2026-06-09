# memcpy

- ea: `0x18002cc60`
- end: `0x18002cc66`
- name: `memcpy`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x18000674c`
- `0x18000a210`
- `0x18000ae36`
- `0x18000b590`
- `0x18000ce1e`
- `0x180022062`
- `0x1800224e7`
- `0x1800225f6`
- `0x180024145`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x18002cc60`

## pseudocode

```c
// attributes: thunk
void *__cdecl memcpy(void *a1, const void *Src, size_t Size)
{
  return __imp_memcpy(a1, Src, Size);
}

```

## disassembly

```asm
0x18002cc60  jmp     cs:__imp_memcpy
```
