# __scrt_is_ucrt_dll_in_use

- ea: `0x18000224c`
- end: `0x180002258`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001bac`
- `0x180001bec`
- `0x180001c84`
- `0x180001cd4`
- `0x180001d68`
- `0x180001e9c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000224c  xor     eax, eax
0x18000224e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002254  setnz   al
0x180002257  retn
```
