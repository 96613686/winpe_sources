# __scrt_is_ucrt_dll_in_use

- ea: `0x180003330`
- end: `0x18000333c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002a48`
- `0x180002a88`
- `0x180002b2c`
- `0x180002b94`
- `0x180002c28`
- `0x180002d5c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180003330  xor     eax, eax
0x180003332  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180003338  setnz   al
0x18000333b  retn
```
