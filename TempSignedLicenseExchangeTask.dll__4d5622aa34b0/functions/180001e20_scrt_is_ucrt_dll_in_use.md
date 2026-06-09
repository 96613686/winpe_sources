# __scrt_is_ucrt_dll_in_use

- ea: `0x180001e20`
- end: `0x180001e2c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000157c`
- `0x1800015bc`
- `0x180001654`
- `0x1800016a4`
- `0x180001738`
- `0x18000186c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001e20  xor     eax, eax
0x180001e22  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001e28  setnz   al
0x180001e2b  retn
```
