# __scrt_is_ucrt_dll_in_use

- ea: `0x140003434`
- end: `0x140003440`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140002b68`
- `0x140002be8`
- `0x140002d1c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140003434  xor     eax, eax
0x140003436  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x14000343c  setnz   al
0x14000343f  retn
```
