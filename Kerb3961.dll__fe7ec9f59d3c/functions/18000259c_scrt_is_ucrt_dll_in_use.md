# __scrt_is_ucrt_dll_in_use

- ea: `0x18000259c`
- end: `0x1800025a8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001d70`
- `0x180001db0`
- `0x180001e48`
- `0x180001e98`
- `0x180001f2c`
- `0x180002060`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000259c  xor     eax, eax
0x18000259e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800025a4  setnz   al
0x1800025a7  retn
```
