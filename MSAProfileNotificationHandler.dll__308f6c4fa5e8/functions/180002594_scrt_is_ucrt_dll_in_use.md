# __scrt_is_ucrt_dll_in_use

- ea: `0x180002594`
- end: `0x1800025a0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001e30`
- `0x180001e70`
- `0x180001f08`
- `0x180001f58`
- `0x180001fec`
- `0x180002120`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002594  xor     eax, eax
0x180002596  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000259c  setnz   al
0x18000259f  retn
```
