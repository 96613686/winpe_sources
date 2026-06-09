# memmove

- ea: `0x18002c8d0`
- end: `0x18002c8d6`
- name: `memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `27`
- callee_count: `0`
- tags: ``

## callers

- `0x18000298a`
- `0x180002a3e`
- `0x180002b1a`
- `0x180005340`
- `0x180007206`
- `0x180007be0`
- `0x180007e7c`
- `0x1800083a2`
- `0x180008474`
- `0x18000d6fe`
- `0x18000d91a`
- `0x18000da84`
- `0x18000dc64`
- `0x18000dd0e`
- `0x18000dfc6`
- `0x18000e148`
- `0x18000e1c6`
- `0x180010b7a`
- `0x180012c70`
- `0x180013000`
- `0x180013120`
- `0x180014d50`
- `0x180014e30`
- `0x180022062`
- `0x180023d34`
- `0x180024be2`
- `0x18002604a`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x18002c8d0`

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
0x18002c8d0  jmp     cs:__imp_memmove
```
