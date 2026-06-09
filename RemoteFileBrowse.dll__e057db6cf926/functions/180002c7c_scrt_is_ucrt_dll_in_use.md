# __scrt_is_ucrt_dll_in_use

- ea: `0x180002c7c`
- end: `0x180002c88`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002100`
- `0x180002140`
- `0x1800021d8`
- `0x180002228`
- `0x1800022bc`
- `0x1800023f0`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002c7c  xor     eax, eax
0x180002c7e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002c84  setnz   al
0x180002c87  retn
```
