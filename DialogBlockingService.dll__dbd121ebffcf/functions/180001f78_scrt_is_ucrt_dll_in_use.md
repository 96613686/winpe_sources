# __scrt_is_ucrt_dll_in_use

- ea: `0x180001f78`
- end: `0x180001f84`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001694`
- `0x1800016d4`
- `0x18000176c`
- `0x1800017bc`
- `0x180001850`
- `0x180001984`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001f78  xor     eax, eax
0x180001f7a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001f80  setnz   al
0x180001f83  retn
```
