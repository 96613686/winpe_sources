# __scrt_is_ucrt_dll_in_use

- ea: `0x180002978`
- end: `0x180002984`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800020e4`
- `0x180002124`
- `0x1800021bc`
- `0x18000220c`
- `0x1800022a0`
- `0x1800023d4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002978  xor     eax, eax
0x18000297a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002980  setnz   al
0x180002983  retn
```
