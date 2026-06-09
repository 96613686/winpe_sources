# __scrt_is_ucrt_dll_in_use

- ea: `0x18000277c`
- end: `0x180002788`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001f7c`
- `0x180001fbc`
- `0x180002054`
- `0x1800020a4`
- `0x180002138`
- `0x18000226c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000277c  xor     eax, eax
0x18000277e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002784  setnz   al
0x180002787  retn
```
