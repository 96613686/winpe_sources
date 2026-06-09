# __scrt_is_ucrt_dll_in_use

- ea: `0x14000ad24`
- end: `0x14000ad30`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x14000a208`
- `0x14000a280`
- `0x14000a3a4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return dword_14003EDA0 != 0;
}

```

## disassembly

```asm
0x14000ad24  xor     eax, eax
0x14000ad26  cmp     cs:dword_14003EDA0, eax
0x14000ad2c  setnz   al
0x14000ad2f  retn
```
