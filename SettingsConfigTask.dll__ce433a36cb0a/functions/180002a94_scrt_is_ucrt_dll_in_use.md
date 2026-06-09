# __scrt_is_ucrt_dll_in_use

- ea: `0x180002a94`
- end: `0x180002aa0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000222c`
- `0x18000226c`
- `0x180002304`
- `0x180002354`
- `0x1800023e8`
- `0x18000251c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002a94  xor     eax, eax
0x180002a96  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002a9c  setnz   al
0x180002a9f  retn
```
