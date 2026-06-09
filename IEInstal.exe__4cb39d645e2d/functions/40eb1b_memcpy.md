# _memcpy

- ea: `0x40eb1b`
- end: `0x40eb21`
- name: `_memcpy`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x40d860`
- `0x40de00`
- `0x40e310`

## import_xrefs

- `msvcrt!memcpy` at `0x40eb1b`

## pseudocode

```c
// attributes: thunk
void *__cdecl memcpy(void *a1, const void *Src, size_t Size)
{
  return _memcpy(a1, Src, Size);
}

```

## disassembly

```asm
0x40eb1b  jmp     ds:__imp__memcpy
```
