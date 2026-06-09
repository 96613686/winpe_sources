# memset

- ea: `0x18002c8e0`
- end: `0x18002c8e6`
- name: `memset`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `31`
- callee_count: `0`
- tags: ``

## callers

- `0x18000233b`
- `0x180002ebf`
- `0x180003f93`
- `0x180005de0`
- `0x180008826`
- `0x180009536`
- `0x18000ce1e`
- `0x18000da84`
- `0x180015646`
- `0x180015d96`
- `0x180016516`
- `0x180016c36`
- `0x180017356`
- `0x180017a66`
- `0x180018716`
- `0x180018f76`
- `0x180019806`
- `0x18001a036`
- `0x18001a866`
- `0x18001b0a6`
- `0x18001b566`
- `0x18001ba26`
- `0x180020a00`
- `0x180021086`
- `0x1800227f0`
- `0x180022ca2`
- `0x180023a10`
- `0x180024fad`
- `0x180025750`
- `0x180026630`
- `0x18002bd66`

## import_xrefs

- `VCRUNTIME140!memset` at `0x18002c8e0`

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
0x18002c8e0  jmp     cs:__imp_memset
```
