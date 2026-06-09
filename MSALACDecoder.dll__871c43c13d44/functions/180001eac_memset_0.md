# memset_0

- ea: `0x180001eac`
- end: `0x180001eb2`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800023b0`
- `0x180003e54`
- `0x180003f08`
- `0x18000462c`
- `0x180007274`
- `0x180007798`
- `0x180008f24`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x180001eac`

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
0x180001eac  jmp     cs:__imp_memset
```
