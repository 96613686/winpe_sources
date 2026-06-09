# __scrt_is_ucrt_dll_in_use

- ea: `0x14000315c`
- end: `0x140003168`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140002934`
- `0x1400029b4`
- `0x140002ae8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x14000315c  xor     eax, eax
0x14000315e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140003164  setnz   al
0x140003167  retn
```
