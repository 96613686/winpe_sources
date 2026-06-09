# __scrt_is_ucrt_dll_in_use

- ea: `0x18000464c`
- end: `0x180004658`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003ad4`
- `0x180003b14`
- `0x180003bac`
- `0x180003bfc`
- `0x180003c90`
- `0x180003dc4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000464c  xor     eax, eax
0x18000464e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180004654  setnz   al
0x180004657  retn
```
