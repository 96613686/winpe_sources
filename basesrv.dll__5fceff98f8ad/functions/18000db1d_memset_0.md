# memset_0

- ea: `0x18000db1d`
- end: `0x18000db23`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `10`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180007c84`
- `0x180007d90`
- `0x1800087b0`
- `0x180008808`
- `0x1800088b0`
- `0x180008938`
- `0x180009c98`
- `0x180009d44`
- `0x180009de8`
- `0x18000bcf8`

## import_xrefs

- `ntdll!memset` at `0x18000db1d`

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
0x18000db1d  jmp     cs:__imp_memset
```
