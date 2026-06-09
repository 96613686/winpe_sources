# memmove_0

- ea: `0x18001cf88`
- end: `0x18001cf8e`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180003108`
- `0x180003174`
- `0x180011574`
- `0x180012068`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18001cf88`

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
0x18001cf88  jmp     cs:__imp_memmove
```
