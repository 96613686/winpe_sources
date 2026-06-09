# fwrite

- ea: `0x18002cb20`
- end: `0x18002cb26`
- name: `fwrite`
- size: `6`
- prototype: `size_t __cdecl(const void *Buffer, size_t ElementSize, size_t ElementCount, FILE *Stream)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180014450`
- `0x180014530`
- `0x1800145a0`
- `0x180014ba0`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x18002cb20`

## pseudocode

```c
// attributes: thunk
size_t __cdecl fwrite(const void *Buffer, size_t ElementSize, size_t ElementCount, FILE *Stream)
{
  return __imp_fwrite(Buffer, ElementSize, ElementCount, Stream);
}

```

## disassembly

```asm
0x18002cb20  jmp     cs:__imp_fwrite
```
