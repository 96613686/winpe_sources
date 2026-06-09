# std::_Tree_buy<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::_Freenode0(std::_Tree_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *> *)

- ea: `0x18000bed4`
- end: `0x18000bede`
- name: `?_Freenode0@?$_Tree_buy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXPEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@@Z`
- size: `10`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `4`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180010dda`
- `0x180010e00`
- `0x180010e8b`
- `0x180010eb1`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000bed7`

## pseudocode

```c
void __fastcall std::_Tree_buy<std::wstring>::_Freenode0(__int64 a1, void *a2)
{
  operator delete(a2);
}

```

## disassembly

```asm
0x18000bed4  mov     rcx, rdx
0x18000bed7  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
