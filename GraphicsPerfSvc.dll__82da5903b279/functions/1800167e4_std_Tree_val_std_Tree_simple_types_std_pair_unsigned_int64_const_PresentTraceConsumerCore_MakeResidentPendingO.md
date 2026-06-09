# std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *> *)

- ea: `0x1800167e4`
- end: `0x180016838`
- name: `??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@1@@Z`
- size: `84`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800165f0`
- `0x1800167e4`
- `0x180017ce4`
- `0x180017fcc`

## callees

- `0x18000b550`
- `0x1800167e4`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v3; // rbx
  void *v6; // rcx

  v3 = (_QWORD *)a3;
  if ( !*(_BYTE *)(a3 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>(
        a1,
        a2,
        v3[2]);
      v6 = v3;
      v3 = (_QWORD *)*v3;
      std::_Deallocate<16>(v6, 0x38u);
    }
    while ( !*((_BYTE *)v3 + 25) );
  }
}

```

## disassembly

```asm
0x1800167e4  mov     [rsp+arg_0], rbx
0x1800167e9  mov     [rsp+arg_8], rsi
0x1800167ee  push    rdi
0x1800167ef  sub     rsp, 20h
0x1800167f3  cmp     byte ptr [r8+19h], 0
0x1800167f8  mov     rbx, r8
0x1800167fb  mov     rdi, rdx
0x1800167fe  mov     rsi, rcx
0x180016801  jnz     short loc_180016828
0x180016803  mov     r8, [rbx+10h]
0x180016807  mov     rdx, rdi
0x18001680a  mov     rcx, rsi
0x18001680d  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *> *)
0x180016812  mov     rcx, rbx
0x180016815  mov     edx, 38h ; '8'
0x18001681a  mov     rbx, [rbx]
0x18001681d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180016822  cmp     byte ptr [rbx+19h], 0
0x180016826  jz      short loc_180016803
0x180016828  mov     rbx, [rsp+28h+arg_0]
0x18001682d  mov     rsi, [rsp+28h+arg_8]
0x180016832  add     rsp, 20h
0x180016836  pop     rdi
0x180016837  retn
```
