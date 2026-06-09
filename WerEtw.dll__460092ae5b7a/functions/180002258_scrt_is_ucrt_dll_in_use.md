# __scrt_is_ucrt_dll_in_use

- ea: `0x180002258`
- end: `0x180002264`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800019c0`
- `0x180001a00`
- `0x180001a98`
- `0x180001ae8`
- `0x180001b7c`
- `0x180001cb0`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002258  xor     eax, eax
0x18000225a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002260  setnz   al
0x180002263  retn
```
