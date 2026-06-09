# memmove_0

- ea: `0x1800af62c`
- end: `0x1800af632`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x180039798`
- `0x18003b5f8`
- `0x18003b900`
- `0x18003d990`
- `0x18003eda4`
- `0x1800531e0`
- `0x180053770`
- `0x180058ce8`
- `0x180064d3c`
- `0x180069b2c`
- `0x1800808a0`
- `0x1800828bc`
- `0x180082a14`
- `0x180082cc4`
- `0x180082d94`
- `0x180084230`
- `0x18008d078`
- `0x1800a4688`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1800af62c`

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
0x1800af62c  jmp     cs:__imp_memmove
```
