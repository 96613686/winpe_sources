# memmove

- ea: `0x18006cc70`
- end: `0x18006cc76`
- name: `memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x1800216bc`
- `0x180022300`
- `0x180022fb4`
- `0x1800339b4`
- `0x180034e40`
- `0x180034f54`
- `0x180035308`
- `0x18003ad60`
- `0x180040760`
- `0x180041b68`
- `0x180048d80`
- `0x18005bcd8`
- `0x18005be50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18006cc70`

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
0x18006cc70  jmp     cs:__imp_memmove
```
