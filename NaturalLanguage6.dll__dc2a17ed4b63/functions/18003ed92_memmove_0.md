# memmove_0

- ea: `0x18003ed92`
- end: `0x18003ed98`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `33`
- callee_count: `0`
- tags: ``

## callers

- `0x180002778`
- `0x1800107c0`
- `0x180012fb0`
- `0x180013b80`
- `0x180013dd8`
- `0x180023550`
- `0x180025370`
- `0x18002bfb0`
- `0x180034e14`
- `0x180034ed4`
- `0x180034f98`
- `0x180035054`
- `0x180035290`
- `0x1800354c0`
- `0x180035580`
- `0x18003b710`
- `0x18003dc1c`
- `0x1800403f0`
- `0x18004c71c`
- `0x1800543d8`
- `0x180054478`
- `0x18005470c`
- `0x18006e930`
- `0x18006e9e4`
- `0x180077b5c`
- `0x180077d20`
- `0x18007c66c`
- `0x18007ca88`
- `0x18007e6d4`
- `0x180081fd0`
- `0x180085950`
- `0x18008e6d4`
- `0x18008e7a0`

## import_xrefs

- `msvcrt!memmove` at `0x18003ed92`

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
0x18003ed92  jmp     cs:__imp_memmove
```
