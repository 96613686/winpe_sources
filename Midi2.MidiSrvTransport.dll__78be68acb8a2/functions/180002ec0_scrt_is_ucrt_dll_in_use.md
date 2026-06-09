# __scrt_is_ucrt_dll_in_use

- ea: `0x180002ec0`
- end: `0x180002ecc`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002504`
- `0x180002544`
- `0x1800025dc`
- `0x18000262c`
- `0x1800026c0`
- `0x1800027f4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002ec0  xor     eax, eax
0x180002ec2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002ec8  setnz   al
0x180002ecb  retn
```
