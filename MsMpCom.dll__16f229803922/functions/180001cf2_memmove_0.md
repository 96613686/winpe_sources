# memmove_0

- ea: `0x180001cf2`
- end: `0x180001cf8`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002b54`
- `0x180002c08`
- `0x180007d9c`
- `0x180008690`

## import_xrefs

- `msvcrt!memmove` at `0x180001cf2`

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
0x180001cf2  jmp     cs:__imp_memmove
```
