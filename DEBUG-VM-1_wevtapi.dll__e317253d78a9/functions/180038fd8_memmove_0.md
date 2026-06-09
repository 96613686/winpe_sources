# memmove_0

- ea: `0x180038fd8`
- end: `0x180038fde`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000bf84`
- `0x18000c034`
- `0x180020b50`
- `0x180028130`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180038fd8`

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
0x180038fd8  jmp     cs:__imp_memmove
```
