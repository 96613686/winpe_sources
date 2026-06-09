# __scrt_is_ucrt_dll_in_use

- ea: `0x180003bc8`
- end: `0x180003bd4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000332c`
- `0x18000336c`
- `0x180003404`
- `0x180003454`
- `0x1800034e8`
- `0x18000361c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180003bc8  xor     eax, eax
0x180003bca  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180003bd0  setnz   al
0x180003bd3  retn
```
