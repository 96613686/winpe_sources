# __scrt_is_ucrt_dll_in_use

- ea: `0x18002b298`
- end: `0x18002b2a4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18002abf8`
- `0x18002ac38`
- `0x18002acd0`
- `0x18002ad20`
- `0x18002adb4`
- `0x18002aee8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18002b298  xor     eax, eax
0x18002b29a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18002b2a0  setnz   al
0x18002b2a3  retn
```
