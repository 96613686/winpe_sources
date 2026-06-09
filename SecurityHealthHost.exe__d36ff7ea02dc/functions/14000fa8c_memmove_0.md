# memmove_0

- ea: `0x14000fa8c`
- end: `0x14000fa92`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x140002ed4`
- `0x140003f18`
- `0x140004350`
- `0x140009a4c`
- `0x14000cdbc`
- `0x14000d224`
- `0x14000d5e8`
- `0x14000e47c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x14000fa8c`

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
0x14000fa8c  jmp     cs:__imp_memmove
```
