# memmove_0

- ea: `0x1800586ba`
- end: `0x1800586c0`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `20`
- callee_count: `0`
- tags: ``

## callers

- `0x180009070`
- `0x18000aaf0`
- `0x18000ad28`
- `0x18000adc0`
- `0x18000b718`
- `0x18000d900`
- `0x180011240`
- `0x18001a5ec`
- `0x18001a8dc`
- `0x18001d008`
- `0x180020248`
- `0x1800209f4`
- `0x18002754c`
- `0x1800380d4`
- `0x180039afc`
- `0x180039eac`
- `0x18003df90`
- `0x1800403b4`
- `0x180053f20`
- `0x180057068`

## import_xrefs

- `msvcrt!memmove` at `0x1800586ba`

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
0x1800586ba  jmp     cs:__imp_memmove
```
