# __scrt_is_ucrt_dll_in_use

- ea: `0x1400032d4`
- end: `0x1400032e0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140002a74`
- `0x140002af4`
- `0x140002c28`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1400032d4  xor     eax, eax
0x1400032d6  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1400032dc  setnz   al
0x1400032df  retn
```
