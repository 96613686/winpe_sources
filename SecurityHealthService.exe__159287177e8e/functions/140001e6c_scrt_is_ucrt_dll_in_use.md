# __scrt_is_ucrt_dll_in_use

- ea: `0x140001e6c`
- end: `0x140001e78`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001650`
- `0x1400016d0`
- `0x140001804`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140001e6c  xor     eax, eax
0x140001e6e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140001e74  setnz   al
0x140001e77  retn
```
