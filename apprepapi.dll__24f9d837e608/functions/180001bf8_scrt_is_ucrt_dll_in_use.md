# __scrt_is_ucrt_dll_in_use

- ea: `0x180001bf8`
- end: `0x180001c04`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001558`
- `0x180001598`
- `0x180001630`
- `0x180001680`
- `0x180001714`
- `0x180001848`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001bf8  xor     eax, eax
0x180001bfa  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001c00  setnz   al
0x180001c03  retn
```
