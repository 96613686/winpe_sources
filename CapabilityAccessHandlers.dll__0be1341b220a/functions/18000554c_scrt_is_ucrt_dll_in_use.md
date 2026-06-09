# __scrt_is_ucrt_dll_in_use

- ea: `0x18000554c`
- end: `0x180005558`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180004cb8`
- `0x180004cf8`
- `0x180004d90`
- `0x180004de0`
- `0x180004e74`
- `0x180004fa8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000554c  xor     eax, eax
0x18000554e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180005554  setnz   al
0x180005557  retn
```
