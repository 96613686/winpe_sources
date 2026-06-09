# __scrt_is_ucrt_dll_in_use

- ea: `0x180003f4c`
- end: `0x180003f58`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800036b4`
- `0x1800036f4`
- `0x18000378c`
- `0x1800037dc`
- `0x180003870`
- `0x1800039a4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180003f4c  xor     eax, eax
0x180003f4e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180003f54  setnz   al
0x180003f57  retn
```
