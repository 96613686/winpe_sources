# memmove_0

- ea: `0x180002ee2`
- end: `0x180002ee8`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000720c`
- `0x180007290`
- `0x18000a080`
- `0x18000bc38`

## import_xrefs

- `msvcrt!memmove` at `0x180002ee2`

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
0x180002ee2  jmp     cs:__imp_memmove
```
