# __scrt_is_ucrt_dll_in_use

- ea: `0x1800042e4`
- end: `0x1800042f0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003a68`
- `0x180003aa4`
- `0x180003b30`
- `0x180003b90`
- `0x180003c20`
- `0x180003d44`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800042e4  xor     eax, eax
0x1800042e6  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800042ec  setnz   al
0x1800042ef  retn
```
