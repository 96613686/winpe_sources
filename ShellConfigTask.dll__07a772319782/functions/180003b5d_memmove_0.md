# memmove_0

- ea: `0x180003b5d`
- end: `0x180003b63`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180009704`
- `0x18000f350`
- `0x18000f4e0`
- `0x18000f670`
- `0x18000f92c`
- `0x18000f964`
- `0x18000fce4`
- `0x1800253a8`
- `0x180025f28`
- `0x180027560`
- `0x180028c60`
- `0x18002dd04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180003b5d`

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
0x180003b5d  jmp     cs:__imp_memmove
```
