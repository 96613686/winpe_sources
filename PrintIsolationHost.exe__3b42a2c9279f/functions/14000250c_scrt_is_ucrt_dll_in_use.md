# __scrt_is_ucrt_dll_in_use

- ea: `0x14000250c`
- end: `0x140002518`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001cf4`
- `0x140001d74`
- `0x140001ea8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x14000250c  xor     eax, eax
0x14000250e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140002514  setnz   al
0x140002517  retn
```
