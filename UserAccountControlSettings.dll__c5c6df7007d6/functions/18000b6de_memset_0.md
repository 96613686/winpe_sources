# memset_0

- ea: `0x18000b6de`
- end: `0x18000b6e4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x1800034f8`
- `0x1800040c0`
- `0x180004520`
- `0x1800045d4`
- `0x180004870`
- `0x1800053f4`
- `0x1800061a0`
- `0x18000684c`
- `0x180006ee8`
- `0x18000a8e0`

## import_xrefs

- `msvcrt!memset` at `0x18000b6de`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset_0(void *a1, int Val, size_t Size)
{
  return memset(a1, Val, Size);
}

```

## disassembly

```asm
0x18000b6de  jmp     cs:__imp_memset
```
