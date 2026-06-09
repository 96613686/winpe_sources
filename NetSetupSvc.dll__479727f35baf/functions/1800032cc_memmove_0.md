# memmove_0

- ea: `0x1800032cc`
- end: `0x1800032d2`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x180006dfc`
- `0x18000bfd0`
- `0x18000e91c`
- `0x18000ea48`
- `0x1800177d0`
- `0x180017adc`
- `0x1800182f4`
- `0x180019b6c`
- `0x18001c4b8`
- `0x18002650c`
- `0x180029de0`
- `0x18002a6c4`
- `0x18002a760`
- `0x18002a7c4`
- `0x18002a838`
- `0x18002af20`
- `0x18002b0cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1800032cc`

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
0x1800032cc  jmp     cs:__imp_memmove
```
