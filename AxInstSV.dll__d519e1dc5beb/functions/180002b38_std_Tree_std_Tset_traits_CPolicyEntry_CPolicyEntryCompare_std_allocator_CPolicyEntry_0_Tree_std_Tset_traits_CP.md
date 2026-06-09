# std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::~_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>(void)

- ea: `0x180002b38`
- end: `0x180002b62`
- name: `??1?$_Tree@V?$_Tset_traits@PEAVCPolicyEntry@@UCPolicyEntryCompare@@V?$allocator@PEAVCPolicyEntry@@@std@@$0A@@std@@@std@@QEAA@XZ`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002b78`

## callees

- `0x180002774`
- `0x180002898`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::~_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>(
        _QWORD *a1)
{
  std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>::_Erase_tree<std::allocator<std::_Tree_node<CPolicyEntry *,void *>>>(
    a1,
    a1,
    *(_QWORD *)(*a1 + 8LL));
  return std::_Deallocate<16>(*a1, 40);
}

```

## disassembly

```asm
0x180002b38  push    rbx
0x180002b3a  sub     rsp, 20h
0x180002b3e  mov     r8, [rcx]
0x180002b41  mov     rdx, rcx
0x180002b44  mov     rbx, rcx
0x180002b47  mov     r8, [r8+8]
0x180002b4b  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@PEAVCPolicyEntry@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@PEAVCPolicyEntry@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@PEAVCPolicyEntry@@PEAX@std@@@1@PEAU?$_Tree_node@PEAVCPolicyEntry@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>::_Erase_tree<std::allocator<std::_Tree_node<CPolicyEntry *,void *>>>(std::allocator<std::_Tree_node<CPolicyEntry *,void *>> &,std::_Tree_node<CPolicyEntry *,void *> *)
0x180002b50  mov     rcx, [rbx]
0x180002b53  mov     edx, 28h ; '('
0x180002b58  add     rsp, 20h
0x180002b5c  pop     rbx
0x180002b5d  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
