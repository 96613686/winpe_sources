# __scrt_is_ucrt_dll_in_use

- ea: `0x180003f08`
- end: `0x180003f14`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800036c4`
- `0x180003704`
- `0x18000379c`
- `0x1800037ec`
- `0x180003880`
- `0x1800039b4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180003f08  xor     eax, eax
0x180003f0a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180003f10  setnz   al
0x180003f13  retn
```
