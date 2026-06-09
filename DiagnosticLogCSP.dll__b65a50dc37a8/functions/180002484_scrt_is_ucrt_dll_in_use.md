# __scrt_is_ucrt_dll_in_use

- ea: `0x180002484`
- end: `0x180002490`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001d0c`
- `0x180001d4c`
- `0x180001de4`
- `0x180001e34`
- `0x180001ec8`
- `0x180001ffc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002484  xor     eax, eax
0x180002486  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000248c  setnz   al
0x18000248f  retn
```
