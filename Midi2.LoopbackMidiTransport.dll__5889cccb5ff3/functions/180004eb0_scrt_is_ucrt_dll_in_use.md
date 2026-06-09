# __scrt_is_ucrt_dll_in_use

- ea: `0x180004eb0`
- end: `0x180004ebc`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800042e4`
- `0x180004324`
- `0x1800043bc`
- `0x18000440c`
- `0x1800044a0`
- `0x1800045d4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180004eb0  xor     eax, eax
0x180004eb2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180004eb8  setnz   al
0x180004ebb  retn
```
