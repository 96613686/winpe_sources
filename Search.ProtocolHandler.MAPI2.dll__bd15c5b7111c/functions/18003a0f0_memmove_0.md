# memmove_0

- ea: `0x18003a0f0`
- end: `0x18003a0f6`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180007bc8`
- `0x1800122d8`
- `0x180017810`
- `0x1800379b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18003a0f0`

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
0x18003a0f0  jmp     cs:__imp_memmove
```
