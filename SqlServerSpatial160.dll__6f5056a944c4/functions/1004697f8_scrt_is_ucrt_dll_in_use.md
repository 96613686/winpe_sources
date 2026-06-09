# __scrt_is_ucrt_dll_in_use

- ea: `0x1004697f8`
- end: `0x100469804`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x100468f30`
- `0x100468f70`
- `0x100469014`
- `0x10046907c`
- `0x100469120`
- `0x100469254`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1004697f8  xor     eax, eax
0x1004697fa  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x100469800  setnz   al
0x100469803  retn
```
