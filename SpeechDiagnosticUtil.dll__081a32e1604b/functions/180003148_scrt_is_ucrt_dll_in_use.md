# __scrt_is_ucrt_dll_in_use

- ea: `0x180003148`
- end: `0x180003154`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002934`
- `0x180002974`
- `0x180002a0c`
- `0x180002a5c`
- `0x180002af0`
- `0x180002c24`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180003148  xor     eax, eax
0x18000314a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180003150  setnz   al
0x180003153  retn
```
