# memmove_0

- ea: `0x18005e0d0`
- end: `0x18005e0d6`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18002715c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18005e0d0`

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
0x18005e0d0  jmp     cs:__imp_memmove
```
