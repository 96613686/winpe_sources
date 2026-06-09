# memmove_0

- ea: `0x18000e7f8`
- end: `0x18000e7fe`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18000694c`
- `0x1800071b0`
- `0x18000ac28`
- `0x18000cea0`
- `0x18000d8b8`
- `0x18000db14`
- `0x18000dcc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18000e7f8`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove_0(void *a1, const void *Src, size_t Size)
{
  return memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x18000e7f8  jmp     cs:__imp_memmove
```
