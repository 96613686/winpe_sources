# __scrt_is_ucrt_dll_in_use

- ea: `0x1400089dc`
- end: `0x1400089e8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140008218`
- `0x1400082a0`
- `0x14000841c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return dword_140012020 != 0;
}

```

## disassembly

```asm
0x1400089dc  xor     eax, eax
0x1400089de  cmp     cs:dword_140012020, eax
0x1400089e4  setnz   al
0x1400089e7  retn
```
