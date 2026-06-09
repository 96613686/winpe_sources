# __scrt_is_ucrt_dll_in_use

- ea: `0x180002580`
- end: `0x18000258c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001e44`
- `0x180001e84`
- `0x180001f1c`
- `0x180001f6c`
- `0x180002000`
- `0x180002134`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002580  xor     eax, eax
0x180002582  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002588  setnz   al
0x18000258b  retn
```
