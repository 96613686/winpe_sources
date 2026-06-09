# __scrt_is_ucrt_dll_in_use

- ea: `0x180002934`
- end: `0x180002940`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002094`
- `0x1800020d4`
- `0x18000216c`
- `0x1800021bc`
- `0x180002250`
- `0x180002384`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002934  xor     eax, eax
0x180002936  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000293c  setnz   al
0x18000293f  retn
```
