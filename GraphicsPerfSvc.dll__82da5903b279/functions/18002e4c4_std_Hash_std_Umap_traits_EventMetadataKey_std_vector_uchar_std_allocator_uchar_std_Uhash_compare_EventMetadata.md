# std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<uchar,std::allocator<uchar>>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<uchar,std::allocator<uchar>>>>,0>>::emplace<EventMetadataKey &,std::vector<uchar,std::allocator<uchar>>>(EventMetadataKey &,std::vector<uchar,std::allocator<uchar>> &&)

- ea: `0x18002e4c4`
- end: `0x18002e5b5`
- name: `??$emplace@AEAUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@?$_Hash@V?$_Umap_traits@UEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@V?$_Uhash_compare@UEventMetadataKey@@UEventMetadataKeyHash@@UEventMetadataKeyEqual@@@3@V?$allocator@U?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@std@@@std@@@std@@@std@@_N@1@AEAUEventMetadataKey@@$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z`
- size: `241`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002e664`

## callees

- `0x18000c1b8`
- `0x18002e3d8`
- `0x18002e408`
- `0x18002e488`
- `0x18002e4c4`
- `0x18002e5bc`
- `0x18002ec44`
- `0x18002ec74`
- `0x18002ee90`
- `0x18002eee8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<unsigned char>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<unsigned char>>>,0>>::emplace<EventMetadataKey &,std::vector<unsigned char>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  unsigned __int64 v8; // rbp
  _QWORD *v9; // rcx
  const void *v10; // r8
  _QWORD *v11; // rsi
  __int64 v12; // rcx
  _QWORD v14[2]; // [rsp+20h] [rbp-58h] BYREF
  _OWORD v15[4]; // [rsp+30h] [rbp-48h] BYREF

  v8 = std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>::operator()<EventMetadataKey>(
         (__int64)a1,
         a3);
  std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<unsigned char>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<unsigned char>>>,0>>::_Find_last<EventMetadataKey>(
    v9,
    v15,
    v10,
    v8);
  if ( *((_QWORD *)&v15[0] + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v15[0] + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<unsigned char>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<unsigned char>>>,0>>::_Check_max_size(a1);
    v11 = std::_Allocate<16,std::_Default_allocate_traits>(0x48u);
    std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<EventMetadataKey const,std::vector<unsigned char>>,void *>>>::construct<std::pair<EventMetadataKey const,std::vector<unsigned char>>,EventMetadataKey &,std::vector<unsigned char>>(
      v12,
      v11 + 2,
      a3,
      a4,
      a1 + 1,
      v11);
    if ( (unsigned __int8)std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<unsigned char>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<unsigned char>>>,0>>::_Check_rehash_required_1(a1) )
    {
      std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<unsigned char>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<unsigned char>>>,0>>::_Rehash_for_1(a1);
      v15[0] = *(_OWORD *)std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<unsigned char>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<unsigned char>>>,0>>::_Find_last<EventMetadataKey>(
                            a1,
                            v15,
                            v11 + 2,
                            v8);
    }
    v14[1] = 0;
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<unsigned char>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<unsigned char>>>,0>>::_Insert_new_node_before(
                      a1,
                      v8,
                      *(_QWORD *)&v15[0],
                      v11);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<EventMetadataKey const,std::vector<unsigned char>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<EventMetadataKey const,std::vector<unsigned char>>,void *>>>(v14);
  }
  return a2;
}

```

## disassembly

```asm
0x18002e4c4  push    rbx
0x18002e4c6  push    rbp
0x18002e4c7  push    rsi
0x18002e4c8  push    rdi
0x18002e4c9  push    r14
0x18002e4cb  push    r15
0x18002e4cd  sub     rsp, 48h
0x18002e4d1  mov     r15, r9
0x18002e4d4  mov     r14, r8
0x18002e4d7  mov     rbx, rdx
0x18002e4da  mov     rdi, rcx
0x18002e4dd  mov     rdx, r8
0x18002e4e0  call    ??$?RUEventMetadataKey@@@?$_Uhash_compare@UEventMetadataKey@@UEventMetadataKeyHash@@UEventMetadataKeyEqual@@@std@@QEBA_KAEBUEventMetadataKey@@@Z; std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>::operator()<EventMetadataKey>(EventMetadataKey const &)
0x18002e4e5  mov     rbp, rax
0x18002e4e8  mov     r9, rax
0x18002e4eb  lea     rdx, [rsp+78h+var_48]
0x18002e4f0  call    ??$_Find_last@UEventMetadataKey@@@?$_Hash@V?$_Umap_traits@UEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@V?$_Uhash_compare@UEventMetadataKey@@UEventMetadataKeyHash@@UEventMetadataKeyEqual@@@3@V?$allocator@U?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@std@@PEAX@std@@@1@AEBUEventMetadataKey@@_K@Z; std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<uchar>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<uchar>>>,0>>::_Find_last<EventMetadataKey>(EventMetadataKey const &,unsigned __int64)
0x18002e4f5  mov     rcx, qword ptr [rsp+78h+var_48+8]
0x18002e4fa  test    rcx, rcx
0x18002e4fd  jz      short loc_18002E50B
0x18002e4ff  mov     [rbx], rcx
0x18002e502  mov     byte ptr [rbx+8], 0
0x18002e506  jmp     loc_18002E5A5
0x18002e50b  mov     rcx, rdi
0x18002e50e  call    ?_Check_max_size@?$_Hash@V?$_Umap_traits@UEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@V?$_Uhash_compare@UEventMetadataKey@@UEventMetadataKeyHash@@UEventMetadataKeyEqual@@@3@V?$allocator@U?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@std@@@3@$0A@@std@@@std@@IEBAXXZ; std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<uchar>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<uchar>>>,0>>::_Check_max_size(void)
0x18002e513  lea     rax, [rdi+8]
0x18002e517  mov     [rsp+78h+var_58], rax
0x18002e51c  mov     [rsp+78h+var_50], 0
0x18002e525  mov     ecx, 48h ; 'H'
0x18002e52a  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002e52f  mov     rsi, rax
0x18002e532  mov     [rsp+78h+var_50], rax
0x18002e537  lea     rdx, [rax+10h]
0x18002e53b  mov     r9, r15
0x18002e53e  mov     r8, r14
0x18002e541  call    ??$construct@U?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@std@@AEAUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@2@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@1@AEAUEventMetadataKey@@$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<EventMetadataKey const,std::vector<uchar>>,void *>>>::construct<std::pair<EventMetadataKey const,std::vector<uchar>>,EventMetadataKey &,std::vector<uchar>>(std::allocator<std::_List_node<std::pair<EventMetadataKey const,std::vector<uchar>>,void *>> &,std::pair<EventMetadataKey const,std::vector<uchar>> * const,EventMetadataKey &,std::vector<uchar> &&)
0x18002e546  nop
0x18002e547  mov     rcx, rdi
0x18002e54a  call    ?_Check_rehash_required_1@?$_Hash@V?$_Umap_traits@UEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@V?$_Uhash_compare@UEventMetadataKey@@UEventMetadataKeyHash@@UEventMetadataKeyEqual@@@3@V?$allocator@U?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@std@@@3@$0A@@std@@@std@@IEBA_NXZ; std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<uchar>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<uchar>>>,0>>::_Check_rehash_required_1(void)
0x18002e54f  test    al, al
0x18002e551  jz      short loc_18002E578
0x18002e553  mov     rcx, rdi
0x18002e556  call    ?_Rehash_for_1@?$_Hash@V?$_Umap_traits@UEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@V?$_Uhash_compare@UEventMetadataKey@@UEventMetadataKeyHash@@UEventMetadataKeyEqual@@@3@V?$allocator@U?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@std@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<uchar>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<uchar>>>,0>>::_Rehash_for_1(void)
0x18002e55b  lea     r8, [rsi+10h]
0x18002e55f  mov     r9, rbp
0x18002e562  lea     rdx, [rsp+78h+var_48]
0x18002e567  mov     rcx, rdi
0x18002e56a  call    ??$_Find_last@UEventMetadataKey@@@?$_Hash@V?$_Umap_traits@UEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@V?$_Uhash_compare@UEventMetadataKey@@UEventMetadataKeyHash@@UEventMetadataKeyEqual@@@3@V?$allocator@U?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@std@@PEAX@std@@@1@AEBUEventMetadataKey@@_K@Z; std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<uchar>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<uchar>>>,0>>::_Find_last<EventMetadataKey>(EventMetadataKey const &,unsigned __int64)
0x18002e56f  movups  xmm0, xmmword ptr [rax]
0x18002e572  movdqu  [rsp+78h+var_48], xmm0
0x18002e578  mov     [rsp+78h+var_50], 0
0x18002e581  mov     r9, rsi
0x18002e584  mov     r8, qword ptr [rsp+78h+var_48]
0x18002e589  mov     rdx, rbp
0x18002e58c  mov     rcx, rdi
0x18002e58f  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@UEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@V?$_Uhash_compare@UEventMetadataKey@@UEventMetadataKeyHash@@UEventMetadataKeyEqual@@@3@V?$allocator@U?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@std@@@3@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<uchar>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<uchar>>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<EventMetadataKey const,std::vector<uchar>>,void *> * const,std::_List_node<std::pair<EventMetadataKey const,std::vector<uchar>>,void *> * const)
0x18002e594  mov     [rbx], rax
0x18002e597  mov     byte ptr [rbx+8], 1
0x18002e59b  lea     rcx, [rsp+78h+var_58]
0x18002e5a0  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<EventMetadataKey const,std::vector<uchar>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<EventMetadataKey const,std::vector<uchar>>,void *>>>(void)
0x18002e5a5  mov     rax, rbx
0x18002e5a8  add     rsp, 48h
0x18002e5ac  pop     r15
0x18002e5ae  pop     r14
0x18002e5b0  pop     rdi
0x18002e5b1  pop     rsi
0x18002e5b2  pop     rbp
0x18002e5b3  pop     rbx
0x18002e5b4  retn
```
