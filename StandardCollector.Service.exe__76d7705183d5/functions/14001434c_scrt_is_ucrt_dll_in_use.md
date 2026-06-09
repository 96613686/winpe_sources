# __scrt_is_ucrt_dll_in_use

- ea: `0x14001434c`
- end: `0x140014358`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140013994`
- `0x140013a0c`
- `0x140013b30`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x14001434c  xor     eax, eax
0x14001434e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140014354  setnz   al
0x140014357  retn
```
