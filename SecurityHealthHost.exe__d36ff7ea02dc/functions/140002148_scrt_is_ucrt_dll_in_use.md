# __scrt_is_ucrt_dll_in_use

- ea: `0x140002148`
- end: `0x140002154`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001690`
- `0x140001710`
- `0x140001844`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140002148  xor     eax, eax
0x14000214a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140002150  setnz   al
0x140002153  retn
```
