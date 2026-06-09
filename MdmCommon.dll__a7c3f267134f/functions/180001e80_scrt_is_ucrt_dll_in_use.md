# __scrt_is_ucrt_dll_in_use

- ea: `0x180001e80`
- end: `0x180001e8c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001714`
- `0x180001754`
- `0x1800017ec`
- `0x18000183c`
- `0x1800018d0`
- `0x180001a04`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001e80  xor     eax, eax
0x180001e82  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001e88  setnz   al
0x180001e8b  retn
```
