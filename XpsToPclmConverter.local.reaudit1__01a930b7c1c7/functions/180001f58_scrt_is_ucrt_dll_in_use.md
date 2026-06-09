# __scrt_is_ucrt_dll_in_use

- ea: `0x180001f58`
- end: `0x180001f64`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800016e4`
- `0x180001724`
- `0x1800017bc`
- `0x18000180c`
- `0x1800018a0`
- `0x1800019d4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001f58  xor     eax, eax
0x180001f5a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001f60  setnz   al
0x180001f63  retn
```
