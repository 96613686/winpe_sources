# memset_0

- ea: `0x180009efe`
- end: `0x180009f04`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x1800022f4`
- `0x180002698`
- `0x180002758`
- `0x180002a18`
- `0x1800038f4`
- `0x1800046f4`
- `0x180004e6c`
- `0x180004fb8`
- `0x180005780`
- `0x1800074dc`
- `0x180008680`
- `0x180008830`
- `0x180008bc0`
- `0x180008e10`
- `0x180009a60`

## import_xrefs

- `msvcrt!memset` at `0x180009efe`

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
0x180009efe  jmp     cs:__imp_memset
```
