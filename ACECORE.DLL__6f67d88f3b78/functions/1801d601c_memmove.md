# memmove

- ea: `0x1801d601c`
- end: `0x1801d6022`
- name: `memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `70`
- callee_count: `0`
- tags: ``

## callers

- `0x1800262a4`
- `0x180035494`
- `0x18003554c`
- `0x180035e00`
- `0x1800431ec`
- `0x18004338c`
- `0x18004f924`
- `0x180054810`
- `0x1800557a8`
- `0x1800558e4`
- `0x1800564b0`
- `0x180056ca0`
- `0x1800605f4`
- `0x18006431c`
- `0x1800670f4`
- `0x18006ff78`
- `0x180070da0`
- `0x1800714e0`
- `0x180071a10`
- `0x18007320c`
- `0x180073538`
- `0x180082ba0`
- `0x180083830`
- `0x180090030`
- `0x180090670`
- `0x18009583c`
- `0x1800975ac`
- `0x1800aa7ac`
- `0x1800bb658`
- `0x1800cbbb0`
- `0x1800cecc4`
- `0x1800cf4b4`
- `0x1800d9af0`
- `0x1800da900`
- `0x1800dc5d8`
- `0x1800dd778`
- `0x1800dde74`
- `0x1800e27c4`
- `0x1800f2af0`
- `0x1800f2c30`
- `0x1800fcdcc`
- `0x180116450`
- `0x18011e3a4`
- `0x180122574`
- `0x180122bb0`
- `0x180122d10`
- `0x1801235f4`
- `0x180126eb0`
- `0x18012f79c`
- `0x18013dd50`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x1801d601c`

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
0x1801d601c  jmp     cs:__imp_memmove
```
