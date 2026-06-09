# ___scrt_is_ucrt_dll_in_use

- ea: `0x10011376`
- end: `0x10011382`
- name: `___scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x10010d3f`
- `0x10010d71`
- `0x10010dd6`
- `0x10010e0a`
- `0x10010e73`
- `0x10010fac`

## pseudocode

```c
BOOL __scrt_is_ucrt_dll_in_use()
{
  return dword_100353CC != 0;
}

```

## disassembly

```asm
0x10011376  xor     eax, eax
0x10011378  cmp     dword_100353CC, eax
0x1001137e  setnz   al
0x10011381  retn
```
