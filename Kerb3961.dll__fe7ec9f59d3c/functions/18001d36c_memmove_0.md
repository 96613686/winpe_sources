# memmove_0

- ea: `0x18001d36c`
- end: `0x18001d372`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800071e0`
- `0x18000e05c`
- `0x1800126e0`
- `0x1800130b0`
- `0x180015994`
- `0x180018180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18001d36c`

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
0x18001d36c  jmp     cs:__imp_memmove
```
