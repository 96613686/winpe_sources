# __scrt_is_ucrt_dll_in_use

- ea: `0x180013818`
- end: `0x180013824`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180012e38`
- `0x180012e78`
- `0x180012f10`
- `0x180012f60`
- `0x180012ff4`
- `0x180013128`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180013818  xor     eax, eax
0x18001381a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180013820  setnz   al
0x180013823  retn
```
