# __scrt_is_ucrt_dll_in_use

- ea: `0x180001d9c`
- end: `0x180001da8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000169c`
- `0x1800016dc`
- `0x180001774`
- `0x1800017c4`
- `0x180001858`
- `0x18000198c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001d9c  xor     eax, eax
0x180001d9e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001da4  setnz   al
0x180001da7  retn
```
