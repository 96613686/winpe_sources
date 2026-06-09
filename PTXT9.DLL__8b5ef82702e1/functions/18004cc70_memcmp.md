# memcmp

- ea: `0x18004cc70`
- end: `0x18004cc76`
- name: `memcmp`
- size: `6`
- prototype: `int __cdecl(const void *Buf1, const void *Buf2, size_t Size)`
- caller_count: `27`
- callee_count: `0`
- tags: ``

## callers

- `0x1800057b0`
- `0x18000feec`
- `0x180011ce4`
- `0x180024f54`
- `0x1800282c8`
- `0x18002ef90`
- `0x18002f3d0`
- `0x180032360`
- `0x1800352f0`
- `0x180036700`
- `0x180037c20`
- `0x180037e40`
- `0x180038e20`
- `0x180039bf8`
- `0x180039d00`
- `0x180073cf0`
- `0x18007b8e0`
- `0x18007c900`
- `0x18008757c`
- `0x180087edc`
- `0x18008c040`
- `0x180091df4`
- `0x1800925b0`
- `0x1800a21e0`
- `0x1800a865c`
- `0x1800aa504`
- `0x1800ac570`

## import_xrefs

- `VCRUNTIME140!memcmp` at `0x18004cc70`

## pseudocode

```c
// attributes: thunk
int __cdecl memcmp(const void *Buf1, const void *Buf2, size_t Size)
{
  return __imp_memcmp(Buf1, Buf2, Size);
}

```

## disassembly

```asm
0x18004cc70  jmp     cs:__imp_memcmp
```
