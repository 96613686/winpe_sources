# memset_0

- ea: `0x180001fde`
- end: `0x180001fe4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x18000240c`
- `0x180002674`
- `0x180002920`
- `0x180002eb8`
- `0x180003804`
- `0x180004970`
- `0x180004b90`
- `0x180005610`
- `0x180005918`
- `0x18000614c`
- `0x180006590`
- `0x1800088c0`
- `0x18000a65c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x180001fde`

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
0x180001fde  jmp     cs:__imp_memset
```
