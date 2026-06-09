# __scrt_is_ucrt_dll_in_use

- ea: `0x140001da0`
- end: `0x140001dac`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001370`
- `0x1400013e8`
- `0x14000150c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return dword_14001AC88 != 0;
}

```

## disassembly

```asm
0x140001da0  xor     eax, eax
0x140001da2  cmp     cs:dword_14001AC88, eax
0x140001da8  setnz   al
0x140001dab  retn
```
