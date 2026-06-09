# __scrt_is_ucrt_dll_in_use

- ea: `0x180002628`
- end: `0x180002634`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001d54`
- `0x180001d94`
- `0x180001e2c`
- `0x180001e7c`
- `0x180001f10`
- `0x180002044`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002628  xor     eax, eax
0x18000262a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002630  setnz   al
0x180002633  retn
```
