# memmove

- ea: `0x18000b74f`
- end: `0x18000b755`
- name: `memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18000f628`
- `0x180016780`
- `0x1800169e0`
- `0x18001dd30`
- `0x180024ff8`
- `0x18002ee38`
- `0x180037e10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18000b74f`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
{
  return __imp_memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x18000b74f  jmp     cs:__imp_memmove
```
