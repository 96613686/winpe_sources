# memmove_0

- ea: `0x140004ab1`
- end: `0x140004ab7`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140018e8c`
- `0x1400206a4`
- `0x140020720`
- `0x14002d24c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x140004ab1`

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
0x140004ab1  jmp     cs:__imp_memmove
```
