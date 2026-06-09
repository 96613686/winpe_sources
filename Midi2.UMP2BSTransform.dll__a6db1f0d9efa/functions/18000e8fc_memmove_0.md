# memmove_0

- ea: `0x18000e8fc`
- end: `0x18000e902`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a4f0`
- `0x18000c2c0`
- `0x18000e1ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18000e8fc`

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
0x18000e8fc  jmp     cs:__imp_memmove
```
