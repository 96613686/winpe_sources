# __scrt_is_ucrt_dll_in_use

- ea: `0x180001f00`
- end: `0x180001f0c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800016cc`
- `0x18000170c`
- `0x1800017a4`
- `0x1800017f4`
- `0x180001888`
- `0x1800019bc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001f00  xor     eax, eax
0x180001f02  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001f08  setnz   al
0x180001f0b  retn
```
