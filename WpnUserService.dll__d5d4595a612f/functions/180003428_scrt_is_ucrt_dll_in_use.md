# __scrt_is_ucrt_dll_in_use

- ea: `0x180003428`
- end: `0x180003434`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002be4`
- `0x180002c24`
- `0x180002cbc`
- `0x180002d0c`
- `0x180002da0`
- `0x180002ed4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180003428  xor     eax, eax
0x18000342a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180003430  setnz   al
0x180003433  retn
```
