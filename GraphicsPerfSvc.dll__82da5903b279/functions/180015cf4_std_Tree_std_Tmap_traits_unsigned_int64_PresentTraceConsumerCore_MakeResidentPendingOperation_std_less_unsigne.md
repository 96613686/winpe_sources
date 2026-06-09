# std::_Tree<std::_Tmap_traits<unsigned __int64,PresentTraceConsumerCore::MakeResidentPendingOperation,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>,0>>::_Tree<std::_Tmap_traits<unsigned __int64,PresentTraceConsumerCore::MakeResidentPendingOperation,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>,0>>(std::_Tree<std::_Tmap_traits<unsigned __int64,PresentTraceConsumerCore::MakeResidentPendingOperation,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>,0>> const &,std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>> &&)

- ea: `0x180015cf4`
- end: `0x180015da3`
- name: `??$?0V?$allocator@U?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@@std@@@?$_Tree@V?$_Tmap_traits@_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAA@AEBV01@$$QEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@@1@@Z`
- size: `175`
- prototype: `__int64 *__fastcall(__int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180019ee0`

## callees

- `0x180015cf4`
- `0x180016058`
- `0x180016084`
- `0x18001805c`
- `0x18001bfd4`

## pseudocode

```c
__int64 *__fastcall std::_Tree<std::_Tmap_traits<unsigned __int64,PresentTraceConsumerCore::MakeResidentPendingOperation,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>,0>>::_Tree<std::_Tmap_traits<unsigned __int64,PresentTraceConsumerCore::MakeResidentPendingOperation,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>,0>>(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 ResidentPending; // rax
  __int64 v5; // rax
  __int64 *v6; // r8
  __int64 i; // rcx
  __int64 *v9; // [rsp+20h] [rbp-18h] BYREF
  __int64 *v10; // [rsp+28h] [rbp-10h]

  *a1 = 0;
  a1[1] = 0;
  v9 = a1;
  v10 = a1;
  ResidentPending = std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>(
                      a1,
                      a2);
  *a1 = ResidentPending;
  *(_QWORD *)(*a1 + 8) = std::_Tree<std::_Tmap_traits<unsigned __int64,PresentTraceConsumerCore::MakeResidentPendingOperation,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>,0>>::_Copy_nodes<0>(
                           a1,
                           *(_QWORD *)(*a2 + 8LL),
                           ResidentPending);
  a1[1] = a2[1];
  if ( *(_BYTE *)(*(_QWORD *)(*a1 + 8) + 25LL) )
  {
    *(_QWORD *)*a1 = *a1;
    *(_QWORD *)(*a1 + 16) = *a1;
  }
  else
  {
    v5 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>>::_Min();
    *v6 = v5;
    for ( i = *(_QWORD *)(*a1 + 8); !*(_BYTE *)(*(_QWORD *)(i + 16) + 25LL); i = *(_QWORD *)(i + 16) )
      ;
    *(_QWORD *)(*a1 + 16) = i;
  }
  v10 = 0;
  std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>>(&v9);
  return a1;
}

```

## disassembly

```asm
0x180015cf4  mov     [rsp+arg_0], rbx
0x180015cf9  push    rdi
0x180015cfa  sub     rsp, 30h
0x180015cfe  mov     rbx, rdx
0x180015d01  mov     rdi, rcx
0x180015d04  mov     qword ptr [rcx], 0
0x180015d0b  mov     qword ptr [rcx+8], 0
0x180015d13  mov     [rsp+38h+var_18], rcx
0x180015d18  mov     [rsp+38h+var_10], rcx
0x180015d1d  call    ??$_Buyheadnode@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@SAPEAU01@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@@1@@Z; std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>> &)
0x180015d22  mov     [rdi], rax
0x180015d25  mov     rdx, [rbx]
0x180015d28  mov     r8, rax
0x180015d2b  mov     rdx, [rdx+8]
0x180015d2f  mov     rcx, rdi
0x180015d32  call    ??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@1@PEAU21@0@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,PresentTraceConsumerCore::MakeResidentPendingOperation,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *> *,std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *> *)
0x180015d37  mov     rcx, [rdi]
0x180015d3a  mov     [rcx+8], rax
0x180015d3e  mov     rax, [rbx+8]
0x180015d42  mov     [rdi+8], rax
0x180015d46  mov     r8, [rdi]
0x180015d49  mov     rcx, [r8+8]
0x180015d4d  cmp     byte ptr [rcx+19h], 0
0x180015d51  jnz     short loc_180015D78
0x180015d53  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>::_Min(std::_Tree_node<std::pair<uint const,std::shared_ptr<PresentEvent>>,void *> *)
0x180015d58  mov     [r8], rax
0x180015d5b  mov     rdx, [rdi]
0x180015d5e  mov     rcx, [rdx+8]
0x180015d62  jmp     short loc_180015D68
0x180015d64  mov     rcx, [rcx+10h]
0x180015d68  mov     rax, [rcx+10h]
0x180015d6c  cmp     byte ptr [rax+19h], 0
0x180015d70  jz      short loc_180015D64
0x180015d72  mov     [rdx+10h], rcx
0x180015d76  jmp     short loc_180015D82
0x180015d78  mov     [r8], r8
0x180015d7b  mov     rax, [rdi]
0x180015d7e  mov     [rax+10h], rax
0x180015d82  mov     [rsp+38h+var_10], 0
0x180015d8b  lea     rcx, [rsp+38h+var_18]
0x180015d90  call    ??1?$_Tree_head_scoped_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@@std@@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@@std@@@2@@std@@QEAA@XZ; std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>>(void)
0x180015d95  mov     rax, rdi
0x180015d98  mov     rbx, [rsp+38h+arg_0]
0x180015d9d  add     rsp, 30h
0x180015da1  pop     rdi
0x180015da2  retn
```
