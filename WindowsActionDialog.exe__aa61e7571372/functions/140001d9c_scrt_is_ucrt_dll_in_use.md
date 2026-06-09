# __scrt_is_ucrt_dll_in_use

- ea: `0x140001d9c`
- end: `0x140001da8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400014ec`
- `0x14000156c`
- `0x1400016a0`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140001d9c  xor     eax, eax
0x140001d9e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140001da4  setnz   al
0x140001da7  retn
```
