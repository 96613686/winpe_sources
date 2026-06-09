# memcpy_0

- ea: `0x18000a4bc`
- end: `0x18000a4c2`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180002e90`
- `0x180007250`
- `0x18000896c`
- `0x180008b90`
- `0x18000941c`
- `0x1800096c0`
- `0x1800097c4`
- `0x180009cfc`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy` at `0x18000a4bc`

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
0x18000a4bc  jmp     cs:__imp_memcpy
```
