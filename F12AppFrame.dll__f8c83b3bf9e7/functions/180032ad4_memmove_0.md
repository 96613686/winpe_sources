# memmove_0

- ea: `0x180032ad4`
- end: `0x180032ada`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800029dc`
- `0x1800045b4`
- `0x180006b40`
- `0x1800124e4`
- `0x18001e704`
- `0x18002b738`
- `0x18002f73c`
- `0x18002f8e4`
- `0x180032234`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180032ad4`

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
0x180032ad4  jmp     cs:__imp_memmove
```
