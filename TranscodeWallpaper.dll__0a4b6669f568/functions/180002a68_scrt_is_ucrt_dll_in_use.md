# __scrt_is_ucrt_dll_in_use

- ea: `0x180002a68`
- end: `0x180002a74`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002194`
- `0x1800021d4`
- `0x18000226c`
- `0x1800022bc`
- `0x180002350`
- `0x180002484`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002a68  xor     eax, eax
0x180002a6a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002a70  setnz   al
0x180002a73  retn
```
