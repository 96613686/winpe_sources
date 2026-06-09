# __scrt_is_ucrt_dll_in_use

- ea: `0x1400022d4`
- end: `0x1400022e0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001020`
- `0x14000105c`
- `0x140002248`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1400022d4  xor     eax, eax
0x1400022d6  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1400022dc  setnz   al
0x1400022df  retn
```
