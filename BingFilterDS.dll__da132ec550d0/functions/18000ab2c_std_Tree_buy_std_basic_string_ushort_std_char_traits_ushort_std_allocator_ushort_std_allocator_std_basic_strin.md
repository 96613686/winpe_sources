# std::_Tree_buy<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::_Freenode0(std::_Tree_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *> *)

- ea: `0x18000ab2c`
- end: `0x18000ab36`
- name: `?_Freenode0@?$_Tree_buy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXPEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@@Z`
- size: `10`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18000cce4`
- `0x18000cfae`
- `0x18000d06a`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000ab2f`

## pseudocode

```c
void __fastcall std::_Tree_buy<std::wstring>::_Freenode0(__int64 a1, void *a2)
{
  operator delete(a2);
}

```

## disassembly

```asm
0x18000ab2c  mov     rcx, rdx
0x18000ab2f  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
