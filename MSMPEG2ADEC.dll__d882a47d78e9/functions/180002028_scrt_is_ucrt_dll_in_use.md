# __scrt_is_ucrt_dll_in_use

- ea: `0x180002028`
- end: `0x180002034`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800017d4`
- `0x180001814`
- `0x1800018ac`
- `0x1800018fc`
- `0x180001990`
- `0x180001ac4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002028  xor     eax, eax
0x18000202a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002030  setnz   al
0x180002033  retn
```
