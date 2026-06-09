# __scrt_is_ucrt_dll_in_use

- ea: `0x180002088`
- end: `0x180002094`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800019dc`
- `0x180001a1c`
- `0x180001ab4`
- `0x180001b04`
- `0x180001b98`
- `0x180001ccc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002088  xor     eax, eax
0x18000208a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002090  setnz   al
0x180002093  retn
```
