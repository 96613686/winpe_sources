# __scrt_is_ucrt_dll_in_use

- ea: `0x180001df4`
- end: `0x180001e00`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800015f4`
- `0x180001634`
- `0x1800016cc`
- `0x18000171c`
- `0x1800017b0`
- `0x1800018e4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001df4  xor     eax, eax
0x180001df6  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001dfc  setnz   al
0x180001dff  retn
```
