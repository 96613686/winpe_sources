# __scrt_is_ucrt_dll_in_use

- ea: `0x14000647c`
- end: `0x140006488`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140005b40`
- `0x140005bc8`
- `0x140005cec`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x14000647c  xor     eax, eax
0x14000647e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140006484  setnz   al
0x140006487  retn
```
