# memmove_0

- ea: `0x18000fba2`
- end: `0x18000fba8`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180004490`
- `0x180005000`
- `0x180006260`
- `0x18000c040`
- `0x1800123c0`

## import_xrefs

- `msvcrt!memmove` at `0x18000fba2`

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
0x18000fba2  jmp     cs:__imp_memmove
```
