# std::_Ref_count_base::_Get_deleter(type_info const &)

- ea: `0x18000bf10`
- end: `0x18000bf13`
- name: `?_Get_deleter@_Ref_count_base@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `3`
- prototype: `void *__fastcall(std::_Ref_count_base *__hidden this, const struct type_info *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void *__fastcall std::_Ref_count_base::_Get_deleter(std::_Ref_count_base *this, const struct type_info *a2)
{
  return 0;
}

```

## disassembly

```asm
0x18000bf10  xor     eax, eax
0x18000bf12  retn
```
