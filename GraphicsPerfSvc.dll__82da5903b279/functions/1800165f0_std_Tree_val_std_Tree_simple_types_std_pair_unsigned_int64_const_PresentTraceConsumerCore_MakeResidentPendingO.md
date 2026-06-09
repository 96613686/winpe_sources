# std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>> &)

- ea: `0x1800165f0`
- end: `0x180016617`
- name: `??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@@1@@Z`
- size: `39`
- prototype: `void __fastcall(void **, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180016a50`
- `0x180017ed8`
- `0x18001805c`
- `0x180018230`
- `0x18001869c`
- `0x180019ee0`

## callees

- `0x18000b550`
- `0x1800167e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>(
        void **a1,
        __int64 a2)
{
  std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>(
    a1,
    a2,
    *((_QWORD *)*a1 + 1));
  std::_Deallocate<16>(*a1, 0x38u);
}

```

## disassembly

```asm
0x1800165f0  push    rbx
0x1800165f2  sub     rsp, 20h
0x1800165f6  mov     r8, [rcx]
0x1800165f9  mov     rbx, rcx
0x1800165fc  mov     r8, [r8+8]
0x180016600  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *> *)
0x180016605  mov     rcx, [rbx]
0x180016608  mov     edx, 38h ; '8'
0x18001660d  add     rsp, 20h
0x180016611  pop     rbx
0x180016612  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
