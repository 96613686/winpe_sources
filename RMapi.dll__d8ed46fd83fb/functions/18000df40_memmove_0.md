# memmove_0

- ea: `0x18000df40`
- end: `0x18000df46`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x1800093c4`
- `0x18000a89c`
- `0x18000b090`
- `0x180014a60`
- `0x18001914c`
- `0x1800192a8`
- `0x180019f0c`
- `0x18001d408`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18000df40`

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
0x18000df40  jmp     cs:__imp_memmove
```
