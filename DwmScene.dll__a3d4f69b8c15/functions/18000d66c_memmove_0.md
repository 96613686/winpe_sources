# memmove_0

- ea: `0x18000d66c`
- end: `0x18000d672`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `29`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c370`
- `0x18001437c`
- `0x180017b04`
- `0x180017b68`
- `0x180017ba0`
- `0x18001c790`
- `0x18001cb2c`
- `0x18001d11c`
- `0x18001e4c4`
- `0x18001e720`
- `0x18001e790`
- `0x18001e960`
- `0x18002f730`
- `0x18006d0d4`
- `0x180073938`
- `0x180078580`
- `0x18007acc0`
- `0x180084cf0`
- `0x18008955c`
- `0x180089660`
- `0x18008997c`
- `0x180089de0`
- `0x180089e98`
- `0x180089f50`
- `0x18008a000`
- `0x18008a0b8`
- `0x18008a140`
- `0x180095604`
- `0x1800bc7c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18000d66c`

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
0x18000d66c  jmp     cs:__imp_memmove
```
