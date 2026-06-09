# memmove_0

- ea: `0x14001bba8`
- end: `0x14001bbae`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x140011558`
- `0x1400141a4`
- `0x140014420`
- `0x1400146ac`
- `0x140015c00`
- `0x140016270`
- `0x140016dc0`
- `0x14001747c`
- `0x1400177a0`
- `0x14001a344`
- `0x14001a60c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x14001bba8`

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
0x14001bba8  jmp     cs:__imp_memmove
```
