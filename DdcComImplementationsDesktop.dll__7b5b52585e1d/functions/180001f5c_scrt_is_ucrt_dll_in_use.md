# __scrt_is_ucrt_dll_in_use

- ea: `0x180001f5c`
- end: `0x180001f68`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000180c`
- `0x18000184c`
- `0x1800018e4`
- `0x180001934`
- `0x1800019c8`
- `0x180001afc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001f5c  xor     eax, eax
0x180001f5e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001f64  setnz   al
0x180001f67  retn
```
