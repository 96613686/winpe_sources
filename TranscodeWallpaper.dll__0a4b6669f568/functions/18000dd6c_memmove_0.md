# memmove_0

- ea: `0x18000dd6c`
- end: `0x18000dd72`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800093bc`
- `0x18000c630`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18000dd6c`

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
0x18000dd6c  jmp     cs:__imp_memmove
```
