# memmove_0

- ea: `0x140013ac3`
- end: `0x140013ac9`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x14000865c`
- `0x140008948`
- `0x14000fb58`
- `0x1400109d4`
- `0x140010b2c`

## import_xrefs

- `msvcrt!memmove` at `0x140013ac3`

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
0x140013ac3  jmp     cs:__imp_memmove
```
