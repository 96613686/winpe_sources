# __scrt_is_ucrt_dll_in_use

- ea: `0x180001f08`
- end: `0x180001f14`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800016c4`
- `0x180001704`
- `0x18000179c`
- `0x1800017ec`
- `0x180001880`
- `0x1800019b4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001f08  xor     eax, eax
0x180001f0a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001f10  setnz   al
0x180001f13  retn
```
