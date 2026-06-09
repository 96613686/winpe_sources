# __scrt_is_ucrt_dll_in_use

- ea: `0x1800035c4`
- end: `0x1800035d0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002a2c`
- `0x180002a68`
- `0x180002af4`
- `0x180002b54`
- `0x180002bd4`
- `0x180002cf8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800035c4  xor     eax, eax
0x1800035c6  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800035cc  setnz   al
0x1800035cf  retn
```
