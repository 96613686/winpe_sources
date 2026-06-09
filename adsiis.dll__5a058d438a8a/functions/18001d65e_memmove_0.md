# memmove_0

- ea: `0x18001d65e`
- end: `0x18001d664`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18001c5f0`
- `0x18001c8b0`
- `0x18001cc10`
- `0x18001cd48`

## import_xrefs

- `msvcrt!memmove` at `0x18001d65e`

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
0x18001d65e  jmp     cs:__imp_memmove
```
