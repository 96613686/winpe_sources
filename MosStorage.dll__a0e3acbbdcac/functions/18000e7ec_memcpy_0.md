# memcpy_0

- ea: `0x18000e7ec`
- end: `0x18000e7f2`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180006798`
- `0x18000694c`
- `0x18000764c`
- `0x180007c90`
- `0x180007da8`
- `0x180007ef8`
- `0x180008f10`
- `0x180009510`
- `0x180009790`
- `0x180009cc0`
- `0x18000c860`
- `0x18000d4e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x18000e7ec`

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
0x18000e7ec  jmp     cs:__imp_memcpy
```
