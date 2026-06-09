# memset

- ea: `0x180005df8`
- end: `0x180005dfe`
- name: `memset`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x1800038a0`
- `0x18000645c`
- `0x18000651c`
- `0x1800067c8`
- `0x180007304`
- `0x180007df8`
- `0x180008500`
- `0x18000863c`
- `0x180008df8`
- `0x1800093f8`
- `0x180009c08`
- `0x180009db4`
- `0x180009e4c`
- `0x18000a124`
- `0x18000a284`
- `0x18000ebd4`
- `0x1800105b8`
- `0x180010f0c`
- `0x1800118b4`
- `0x180012324`
- `0x180012ab4`
- `0x1800134b0`
- `0x18001447c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x180005df8`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset(void *a1, int Val, size_t Size)
{
  return __imp_memset(a1, Val, Size);
}

```

## disassembly

```asm
0x180005df8  jmp     cs:__imp_memset
```
