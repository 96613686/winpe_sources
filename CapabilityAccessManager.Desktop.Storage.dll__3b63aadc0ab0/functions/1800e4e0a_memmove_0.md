# memmove_0

- ea: `0x1800e4e0a`
- end: `0x1800e4e10`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `24`
- callee_count: `0`
- tags: ``

## callers

- `0x180004ef0`
- `0x180020f20`
- `0x18002b7b0`
- `0x180034e90`
- `0x180035980`
- `0x180035bc0`
- `0x180045650`
- `0x1800459b0`
- `0x1800521f0`
- `0x1800594a0`
- `0x18005a7a0`
- `0x1800af900`
- `0x1800d00c0`
- `0x1800e9c34`
- `0x1800f610c`
- `0x1800f62d8`
- `0x1800f6584`
- `0x180100908`
- `0x180100bec`
- `0x180100d34`
- `0x180107ce8`
- `0x18010819c`
- `0x1801083c4`
- `0x18010a960`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1800e4e0a`

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
0x1800e4e0a  jmp     cs:__imp_memmove
```
