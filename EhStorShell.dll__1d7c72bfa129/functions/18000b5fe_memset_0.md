# memset_0

- ea: `0x18000b5fe`
- end: `0x18000b604`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002610`
- `0x180007f20`
- `0x1800097f8`
- `0x18000a568`

## import_xrefs

- `msvcrt!memset` at `0x18000b5fe`

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
0x18000b5fe  jmp     cs:__imp_memset
```
