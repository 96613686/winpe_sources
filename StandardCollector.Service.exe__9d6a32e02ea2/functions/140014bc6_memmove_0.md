# memmove_0

- ea: `0x140014bc6`
- end: `0x140014bcc`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x140001388`
- `0x140002114`
- `0x140002688`
- `0x1400086fc`
- `0x140008ef4`
- `0x14000b8fc`
- `0x14000bdc0`
- `0x14000d69c`
- `0x14000d87c`
- `0x14000e54c`
- `0x140012990`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x140014bc6`

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
0x140014bc6  jmp     cs:__imp_memmove
```
