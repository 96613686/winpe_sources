# __scrt_is_ucrt_dll_in_use

- ea: `0x180003fac`
- end: `0x180003fb8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000367c`
- `0x1800036bc`
- `0x180003754`
- `0x1800037a4`
- `0x180003838`
- `0x18000396c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180003fac  xor     eax, eax
0x180003fae  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180003fb4  setnz   al
0x180003fb7  retn
```
