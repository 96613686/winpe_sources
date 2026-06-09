# std::_Tree_buy<std::pair<ulong const,RootCause *>,std::allocator<std::pair<ulong const,RootCause *>>>::_Freenode0(std::_Tree_node<std::pair<ulong const,RootCause *>,void *> *)

- ea: `0x1800090dc`
- end: `0x1800090e6`
- name: `?_Freenode0@?$_Tree_buy@U?$pair@$$CBKPEAVRootCause@@@std@@V?$allocator@U?$pair@$$CBKPEAVRootCause@@@std@@@2@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBKPEAVRootCause@@@std@@PEAX@2@@Z`
- size: `10`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18000ccb8`
- `0x18000ee54`
- `0x180010d28`
- `0x180010dba`
- `0x18001109d`
- `0x1800110c3`
- `0x1800110ec`
- `0x1800113b9`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800090df`

## pseudocode

```c
void __fastcall std::_Tree_buy<std::pair<unsigned long const,RootCause *>>::_Freenode0(__int64 a1, void *a2)
{
  operator delete(a2);
}

```

## disassembly

```asm
0x1800090dc  mov     rcx, rdx
0x1800090df  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
