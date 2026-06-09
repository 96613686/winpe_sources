# memmove_0

- ea: `0x140003aac`
- end: `0x140003ab2`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140004e1c`
- `0x140009ae0`
- `0x14000f7ec`
- `0x140013310`
- `0x140015b70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x140003aac`

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
0x140003aac  jmp     cs:__imp_memmove
```
