# __scrt_is_ucrt_dll_in_use

- ea: `0x180002c94`
- end: `0x180002ca0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000238c`
- `0x1800023cc`
- `0x180002464`
- `0x1800024b4`
- `0x180002548`
- `0x18000267c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002c94  xor     eax, eax
0x180002c96  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002c9c  setnz   al
0x180002c9f  retn
```
