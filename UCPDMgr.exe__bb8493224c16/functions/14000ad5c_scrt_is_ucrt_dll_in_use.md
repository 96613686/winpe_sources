# __scrt_is_ucrt_dll_in_use

- ea: `0x14000ad5c`
- end: `0x14000ad68`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x14000a3b4`
- `0x14000a434`
- `0x14000a568`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x14000ad5c  xor     eax, eax
0x14000ad5e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x14000ad64  setnz   al
0x14000ad67  retn
```
