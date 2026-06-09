# __scrt_is_ucrt_dll_in_use

- ea: `0x18000212c`
- end: `0x180002138`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000181c`
- `0x18000185c`
- `0x1800018f4`
- `0x180001944`
- `0x1800019d8`
- `0x180001b0c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000212c  xor     eax, eax
0x18000212e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002134  setnz   al
0x180002137  retn
```
