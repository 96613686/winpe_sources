# __scrt_is_ucrt_dll_in_use

- ea: `0x140002040`
- end: `0x14000204c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001714`
- `0x140001794`
- `0x1400018c8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140002040  xor     eax, eax
0x140002042  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140002048  setnz   al
0x14000204b  retn
```
