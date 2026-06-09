# memcpy_0

- ea: `0x18000caf0`
- end: `0x18000caf6`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x1800094bc`
- `0x18000a004`
- `0x18000a0fc`
- `0x18000ace8`
- `0x18000af04`
- `0x18000b360`
- `0x18000b87c`
- `0x18000bbd0`
- `0x18000c354`
- `0x18000c468`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x18000caf0`

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
0x18000caf0  jmp     cs:__imp_memcpy
```
