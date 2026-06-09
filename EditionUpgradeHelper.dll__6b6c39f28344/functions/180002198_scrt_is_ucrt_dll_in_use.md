# __scrt_is_ucrt_dll_in_use

- ea: `0x180002198`
- end: `0x1800021a4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001904`
- `0x180001944`
- `0x1800019dc`
- `0x180001a2c`
- `0x180001ac0`
- `0x180001bf4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002198  xor     eax, eax
0x18000219a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800021a0  setnz   al
0x1800021a3  retn
```
