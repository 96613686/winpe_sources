# memmove_0

- ea: `0x18000a0f9`
- end: `0x18000a0ff`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e448`
- `0x1800114f8`
- `0x180011d1c`
- `0x1800174a8`
- `0x18001754c`
- `0x18002ca30`
- `0x180037aac`
- `0x18003b670`
- `0x18003c144`
- `0x18003cae8`
- `0x18003fec8`
- `0x180045668`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18000a0f9`

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
0x18000a0f9  jmp     cs:__imp_memmove
```
