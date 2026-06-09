# __scrt_is_ucrt_dll_in_use

- ea: `0x18000eed0`
- end: `0x18000eedc`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000e848`
- `0x18000e888`
- `0x18000e920`
- `0x18000e970`
- `0x18000ea04`
- `0x18000eb38`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000eed0  xor     eax, eax
0x18000eed2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000eed8  setnz   al
0x18000eedb  retn
```
