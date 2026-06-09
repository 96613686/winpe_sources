# memcpy

- ea: `0x18004d8d0`
- end: `0x18004d8d6`
- name: `memcpy`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `134`
- callee_count: `0`
- tags: ``

## callers

- `0x180001ef0`
- `0x180003880`
- `0x1800054a8`
- `0x1800057b0`
- `0x18000653c`
- `0x18000681c`
- `0x180009ecc`
- `0x18000a210`
- `0x18000b7bc`
- `0x18000bb10`
- `0x18000d844`
- `0x18000d894`
- `0x18000f1f0`
- `0x18000f9bc`
- `0x180010540`
- `0x180011ce4`
- `0x180012024`
- `0x1800122e4`
- `0x180012370`
- `0x180012470`
- `0x180013cc8`
- `0x180014384`
- `0x18001633c`
- `0x1800174b0`
- `0x18001aee0`
- `0x18001afc0`
- `0x18001b740`
- `0x18001c390`
- `0x1800209a0`
- `0x180023010`
- `0x1800232d8`
- `0x180025510`
- `0x180025b10`
- `0x180027a24`
- `0x180027b50`
- `0x1800282c8`
- `0x180029950`
- `0x18002ce3c`
- `0x18002d404`
- `0x18002dde8`
- `0x18002e260`
- `0x18002f3d0`
- `0x18002f744`
- `0x1800302b0`
- `0x1800306a0`
- `0x180030d90`
- `0x180032fa0`
- `0x180034398`
- `0x1800352f0`
- `0x180036700`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x18004d8d0`

## pseudocode

```c
// attributes: thunk
void *__cdecl memcpy(void *a1, const void *Src, size_t Size)
{
  return __imp_memcpy(a1, Src, Size);
}

```

## disassembly

```asm
0x18004d8d0  jmp     cs:__imp_memcpy
```
