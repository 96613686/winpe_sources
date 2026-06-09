# memmove_0

- ea: `0x18000b3fc`
- end: `0x18000b402`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a328`
- `0x18000a4b8`
- `0x18000a840`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18000b3fc`

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
0x18000b3fc  jmp     cs:__imp_memmove
```
