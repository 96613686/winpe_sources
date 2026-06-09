# __scrt_is_ucrt_dll_in_use

- ea: `0x180002058`
- end: `0x180002064`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800019ac`
- `0x1800019ec`
- `0x180001a84`
- `0x180001ad4`
- `0x180001b68`
- `0x180001c9c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002058  xor     eax, eax
0x18000205a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002060  setnz   al
0x180002063  retn
```
