# __scrt_is_ucrt_dll_in_use

- ea: `0x180002a18`
- end: `0x180002a24`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002088`
- `0x1800020c8`
- `0x180002160`
- `0x1800021b0`
- `0x180002244`
- `0x180002378`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002a18  xor     eax, eax
0x180002a1a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002a20  setnz   al
0x180002a23  retn
```
