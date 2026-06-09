# memmove_0

- ea: `0x140010df8`
- end: `0x140010dfe`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x140002d70`
- `0x140002f18`
- `0x140006eb0`
- `0x140008a78`
- `0x140009994`
- `0x14000dfc4`
- `0x14000e694`
- `0x14000e908`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x140010df8`

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
0x140010df8  jmp     cs:__imp_memmove
```
