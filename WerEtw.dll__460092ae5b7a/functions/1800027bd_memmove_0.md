# memmove_0

- ea: `0x1800027bd`
- end: `0x1800027c3`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180007da8`
- `0x18000cb90`
- `0x18000d144`
- `0x18000d294`
- `0x18000f5dc`
- `0x180011820`
- `0x1800127d0`
- `0x1800150b8`
- `0x180018228`
- `0x18001a3c8`
- `0x18001a93c`
- `0x18001aac0`
- `0x18001da60`
- `0x180024dcc`
- `0x180025508`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1800027bd`

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
0x1800027bd  jmp     cs:__imp_memmove
```
