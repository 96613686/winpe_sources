# __scrt_is_ucrt_dll_in_use

- ea: `0x140001cfc`
- end: `0x140001d08`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400014e4`
- `0x140001564`
- `0x140001698`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140001cfc  xor     eax, eax
0x140001cfe  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140001d04  setnz   al
0x140001d07  retn
```
