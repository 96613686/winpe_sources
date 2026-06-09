# memmove_0

- ea: `0x180007b2c`
- end: `0x180007b32`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180012ca4`
- `0x18001a25c`
- `0x18001c298`
- `0x180021f78`
- `0x180022fe0`
- `0x180023174`
- `0x18002511c`
- `0x18002971c`
- `0x18002d7e4`
- `0x18002e258`
- `0x180031e74`
- `0x180038de4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180007b2c`

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
0x180007b2c  jmp     cs:__imp_memmove
```
