# __scrt_is_ucrt_dll_in_use

- ea: `0x140002c64`
- end: `0x140002c70`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140002464`
- `0x1400024e4`
- `0x140002618`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140002c64  xor     eax, eax
0x140002c66  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140002c6c  setnz   al
0x140002c6f  retn
```
