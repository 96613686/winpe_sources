# __scrt_is_ucrt_dll_in_use

- ea: `0x180002720`
- end: `0x18000272c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001e68`
- `0x180001ea8`
- `0x180001f40`
- `0x180001f90`
- `0x180002024`
- `0x180002158`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002720  xor     eax, eax
0x180002722  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002728  setnz   al
0x18000272b  retn
```
