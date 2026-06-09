# __scrt_is_ucrt_dll_in_use

- ea: `0x180004018`
- end: `0x180004024`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003464`
- `0x1800034a4`
- `0x18000353c`
- `0x18000358c`
- `0x180003620`
- `0x180003754`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180004018  xor     eax, eax
0x18000401a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180004020  setnz   al
0x180004023  retn
```
