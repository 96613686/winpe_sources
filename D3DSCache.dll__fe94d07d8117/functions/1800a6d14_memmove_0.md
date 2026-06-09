# memmove_0

- ea: `0x1800a6d14`
- end: `0x1800a6d1a`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x18003fec0`
- `0x18004c678`
- `0x180056a68`
- `0x18005c658`
- `0x18005cf40`
- `0x18005d32c`
- `0x180062ab0`
- `0x1800638ac`
- `0x180063b24`
- `0x1800658ac`
- `0x180065a04`
- `0x180065c34`
- `0x180065d04`
- `0x1800671c0`
- `0x18006d810`
- `0x180072428`
- `0x1800733d8`
- `0x18008df4c`
- `0x1800a217c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1800a6d14`

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
0x1800a6d14  jmp     cs:__imp_memmove
```
