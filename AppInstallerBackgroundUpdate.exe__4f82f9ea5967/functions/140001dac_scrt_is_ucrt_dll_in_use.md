# __scrt_is_ucrt_dll_in_use

- ea: `0x140001dac`
- end: `0x140001db8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001554`
- `0x1400015d4`
- `0x140001708`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140001dac  xor     eax, eax
0x140001dae  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140001db4  setnz   al
0x140001db7  retn
```
