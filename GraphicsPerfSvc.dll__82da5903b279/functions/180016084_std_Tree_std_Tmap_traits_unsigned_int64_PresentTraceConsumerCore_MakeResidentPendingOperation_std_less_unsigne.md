# std::_Tree<std::_Tmap_traits<unsigned __int64,PresentTraceConsumerCore::MakeResidentPendingOperation,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *> *,std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *> *)

- ea: `0x180016084`
- end: `0x180016159`
- name: `??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@1@PEAU21@0@Z`
- size: `213`
- prototype: `_OWORD *__fastcall(__int64 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180015cf4`
- `0x180016084`

## callees

- `0x180003ebc`
- `0x180016084`
- `0x180017c9c`
- `0x180017ce4`

## pseudocode

```c
_OWORD *__fastcall std::_Tree<std::_Tmap_traits<unsigned __int64,PresentTraceConsumerCore::MakeResidentPendingOperation,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>,0>>::_Copy_nodes<0>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbp
  _OWORD *v7; // rbx
  __int64 *v9; // [rsp+20h] [rbp-48h] BYREF
  __int64 *v10; // [rsp+28h] [rbp-40h]
  _OWORD *v11; // [rsp+30h] [rbp-38h]

  v6 = *a1;
  if ( *(_BYTE *)(a2 + 25) )
    return (_OWORD *)*a1;
  v9 = a1;
  v10 = 0;
  v7 = operator new(0x38u);
  v7[2] = *(_OWORD *)(a2 + 32);
  *((_QWORD *)v7 + 6) = *(_QWORD *)(a2 + 48);
  *(_QWORD *)v7 = v6;
  *((_QWORD *)v7 + 1) = v6;
  *((_QWORD *)v7 + 2) = v6;
  *((_WORD *)v7 + 12) = 0;
  v10 = 0;
  std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>,void *>>>(&v9);
  *((_QWORD *)v7 + 1) = a3;
  *((_BYTE *)v7 + 24) = *(_BYTE *)(a2 + 24);
  v9 = a1;
  v10 = a1;
  v11 = v7;
  *(_QWORD *)v7 = std::_Tree<std::_Tmap_traits<unsigned __int64,PresentTraceConsumerCore::MakeResidentPendingOperation,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>,0>>::_Copy_nodes<0>(
                    a1,
                    *(_QWORD *)a2,
                    v7);
  *((_QWORD *)v7 + 2) = std::_Tree<std::_Tmap_traits<unsigned __int64,PresentTraceConsumerCore::MakeResidentPendingOperation,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>,0>>::_Copy_nodes<0>(
                          a1,
                          *(_QWORD *)(a2 + 16),
                          v7);
  v9 = 0;
  std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>::_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>::~_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>(&v9);
  return v7;
}

```

## disassembly

```asm
0x180016084  push    rbx
0x180016086  push    rbp
0x180016087  push    rsi
0x180016088  push    rdi
0x180016089  push    r14
0x18001608b  sub     rsp, 40h
0x18001608f  mov     r14, r8
0x180016092  mov     rdi, rdx
0x180016095  mov     rsi, rcx
0x180016098  mov     rbp, [rcx]
0x18001609b  cmp     byte ptr [rdx+19h], 0
0x18001609f  jnz     loc_180016148
0x1800160a5  mov     [rsp+68h+var_48], rcx
0x1800160aa  mov     [rsp+68h+var_40], 0
0x1800160b3  mov     ecx, 38h ; '8'; Size
0x1800160b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800160bd  mov     rbx, rax
0x1800160c0  movups  xmm0, xmmword ptr [rdi+20h]
0x1800160c4  movups  xmmword ptr [rax+20h], xmm0
0x1800160c8  movsd   xmm1, qword ptr [rdi+30h]
0x1800160cd  movsd   qword ptr [rax+30h], xmm1
0x1800160d2  mov     [rax], rbp
0x1800160d5  mov     [rax+8], rbp
0x1800160d9  mov     [rax+10h], rbp
0x1800160dd  mov     word ptr [rax+18h], 0
0x1800160e3  mov     [rsp+68h+var_40], 0
0x1800160ec  lea     rcx, [rsp+68h+var_48]
0x1800160f1  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>,void *>>>(void)
0x1800160f6  mov     [rbx+8], r14
0x1800160fa  mov     al, [rdi+18h]
0x1800160fd  mov     [rbx+18h], al
0x180016100  mov     [rsp+68h+var_48], rsi
0x180016105  mov     [rsp+68h+var_40], rsi
0x18001610a  mov     [rsp+68h+var_38], rbx
0x18001610f  mov     r8, rbx
0x180016112  mov     rdx, [rdi]
0x180016115  mov     rcx, rsi
0x180016118  call    ??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@1@PEAU21@0@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,PresentTraceConsumerCore::MakeResidentPendingOperation,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *> *,std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *> *)
0x18001611d  mov     [rbx], rax
0x180016120  mov     r8, rbx
0x180016123  mov     rdx, [rdi+10h]
0x180016127  mov     rcx, rsi
0x18001612a  call    ??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@1@PEAU21@0@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,PresentTraceConsumerCore::MakeResidentPendingOperation,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *> *,std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *> *)
0x18001612f  mov     [rbx+10h], rax
0x180016133  mov     [rsp+68h+var_48], 0
0x18001613c  lea     rcx, [rsp+68h+var_48]
0x180016141  call    ??1?$_Erase_tree_and_orphan_guard@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@@std@@@std@@QEAA@XZ; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>::_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>::~_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>(void)
0x180016146  jmp     short loc_18001614B
0x180016148  mov     rbx, rbp
0x18001614b  mov     rax, rbx
0x18001614e  add     rsp, 40h
0x180016152  pop     r14
0x180016154  pop     rdi
0x180016155  pop     rsi
0x180016156  pop     rbp
0x180016157  pop     rbx
0x180016158  retn
```
