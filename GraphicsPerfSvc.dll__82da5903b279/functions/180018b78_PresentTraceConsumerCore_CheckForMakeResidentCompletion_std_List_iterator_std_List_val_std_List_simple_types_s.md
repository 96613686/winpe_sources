# PresentTraceConsumerCore::CheckForMakeResidentCompletion(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>>> &,__int64,unsigned __int64)

- ea: `0x180018b78`
- end: `0x180018c35`
- name: `?CheckForMakeResidentCompletion@PresentTraceConsumerCore@@AEAAXAEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@std@@@std@@@std@@_J_K@Z`
- size: `189`
- prototype: `void __fastcall(PresentTraceConsumerCore *this, __int64 *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019ee0`

## callees

- `0x18000b550`
- `0x180017634`
- `0x180018810`
- `0x180018b78`
- `0x18001aab8`
- `0x18001b858`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PresentTraceConsumerCore::CheckForMakeResidentCompletion(
        PresentTraceConsumerCore *this,
        __int64 *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  __int64 v4; // rdi
  __int64 **v9; // rsi
  __int64 i; // rbx
  __int64 *v11; // rax
  __int64 v12; // [rsp+68h] [rbp+10h] BYREF

  v4 = *a2;
  v9 = (__int64 **)(*a2 + 40);
  for ( i = **v9; (__int64 *)i != *v9 && a4 >= *(_QWORD *)(i + 32); i = v12 )
  {
    PresentTraceConsumerCore::PushMakeResidentForCompletion(
      this,
      (struct PresentTraceConsumerCore::TrackedSyncObject *)(v4 + 24),
      (const struct PresentTraceConsumerCore::MakeResidentPendingOperation *)(i + 40),
      a3,
      a4,
      1);
    v12 = i;
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>>,std::_Iterator_base0>::operator++(&v12);
    v11 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>::_Extract(
            v9,
            i);
    std::_Deallocate<16>(v11, 0x38u);
  }
  if ( !*(_DWORD *)(v4 + 24) && !*(_QWORD *)(v4 + 48) )
    std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>>>,0>(
      (_QWORD *)this + 90,
      &v12,
      *a2);
}

```

## disassembly

```asm
0x180018b78  mov     [rsp+arg_0], rbx
0x180018b7d  mov     [rsp+arg_10], rbp
0x180018b82  push    rsi
0x180018b83  push    rdi
0x180018b84  push    r12
0x180018b86  push    r14
0x180018b88  push    r15
0x180018b8a  sub     rsp, 30h
0x180018b8e  mov     rdi, [rdx]
0x180018b91  mov     r15, r9
0x180018b94  mov     r12, r8
0x180018b97  mov     r14, rdx
0x180018b9a  mov     rbp, rcx
0x180018b9d  lea     rsi, [rdi+28h]
0x180018ba1  mov     rbx, [rsi]
0x180018ba4  mov     rbx, [rbx]
0x180018ba7  cmp     rbx, [rsi]
0x180018baa  jz      short loc_180018BFD
0x180018bac  cmp     r15, [rbx+20h]
0x180018bb0  jb      short loc_180018BFD
0x180018bb2  lea     r8, [rbx+28h]; struct PresentTraceConsumerCore::MakeResidentPendingOperation *
0x180018bb6  mov     [rsp+58h+var_30], 1; bool
0x180018bbb  mov     r9, r12; __int64
0x180018bbe  mov     [rsp+58h+var_38], r15; unsigned __int64
0x180018bc3  lea     rdx, [rdi+18h]; struct PresentTraceConsumerCore::TrackedSyncObject *
0x180018bc7  mov     rcx, rbp; this
0x180018bca  call    ?PushMakeResidentForCompletion@PresentTraceConsumerCore@@AEAAXAEAUTrackedSyncObject@1@AEBUMakeResidentPendingOperation@1@_J_K_N@Z; PresentTraceConsumerCore::PushMakeResidentForCompletion(PresentTraceConsumerCore::TrackedSyncObject &,PresentTraceConsumerCore::MakeResidentPendingOperation const &,__int64,unsigned __int64,bool)
0x180018bcf  lea     rcx, [rsp+58h+arg_8]
0x180018bd4  mov     [rsp+58h+arg_8], rbx
0x180018bd9  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>>>,std::_Iterator_base0>::operator++(void)
0x180018bde  mov     rdx, rbx
0x180018be1  mov     rcx, rsi
0x180018be4  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>,std::_Iterator_base0>)
0x180018be9  mov     edx, 38h ; '8'
0x180018bee  mov     rcx, rax
0x180018bf1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180018bf6  mov     rbx, [rsp+58h+arg_8]
0x180018bfb  jmp     short loc_180018BA7
0x180018bfd  cmp     dword ptr [rdi+18h], 0
0x180018c01  ja      short loc_180018C1E
0x180018c03  cmp     qword ptr [rdi+30h], 0
0x180018c08  jnz     short loc_180018C1E
0x180018c0a  mov     r8, [r14]
0x180018c0d  lea     rcx, [rbp+2D0h]
0x180018c14  lea     rdx, [rsp+58h+arg_8]
0x180018c19  call    ??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@std@@@std@@@1@V21@@Z; std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>>>,0>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>>>)
0x180018c1e  mov     rbx, [rsp+58h+arg_0]
0x180018c23  mov     rbp, [rsp+58h+arg_10]
0x180018c28  add     rsp, 30h
0x180018c2c  pop     r15
0x180018c2e  pop     r14
0x180018c30  pop     r12
0x180018c32  pop     rdi
0x180018c33  pop     rsi
0x180018c34  retn
```
