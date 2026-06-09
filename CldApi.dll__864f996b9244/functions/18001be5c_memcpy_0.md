# memcpy_0

- ea: `0x18001be5c`
- end: `0x18001be62`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180004ac0`
- `0x180006060`
- `0x1800073b0`
- `0x1800087f8`
- `0x180008c64`
- `0x180009114`
- `0x18000b284`
- `0x18000d560`
- `0x18000e610`
- `0x180010958`
- `0x180018ce0`
- `0x180019c8c`
- `0x180019f50`
- `0x18001a7ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x18001be5c`

## pseudocode

```c
// attributes: thunk
void *__cdecl memcpy_0(void *a1, const void *Src, size_t Size)
{
  return memcpy(a1, Src, Size);
}

```

## disassembly

```asm
0x18001be5c  jmp     cs:__imp_memcpy
```
