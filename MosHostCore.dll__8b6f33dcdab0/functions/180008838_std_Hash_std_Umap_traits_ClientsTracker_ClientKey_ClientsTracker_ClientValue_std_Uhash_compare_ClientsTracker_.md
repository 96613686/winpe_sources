# std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::emplace<ClientsTracker::ClientKey &,ClientsTracker::ClientValue>(ClientsTracker::ClientKey &,ClientsTracker::ClientValue &&)

- ea: `0x180008838`
- end: `0x180008950`
- name: `??$emplace@AEAUClientKey@ClientsTracker@@UClientValue@2@@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@std@@@std@@@std@@_N@1@AEAUClientKey@ClientsTracker@@$$QEAUClientValue@4@@Z`
- size: `280`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180009128`

## callees

- `0x1800077e0`
- `0x1800083a4`
- `0x180008774`
- `0x180008838`
- `0x180008d80`
- `0x1800090a8`
- `0x18000a9a0`
- `0x18000a9d0`
- `0x18000ae9c`
- `0x18000aef4`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::emplace<ClientsTracker::ClientKey &,ClientsTracker::ClientValue>(
        _QWORD *a1,
        __int64 a2,
        unsigned int *a3,
        __int64 a4)
{
  __int64 v8; // r14
  _QWORD *v9; // rsi
  __int64 v10; // rcx
  _QWORD v12[2]; // [rsp+20h] [rbp-20h] BYREF
  __int128 v13; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int64 v14; // [rsp+70h] [rbp+30h] BYREF

  v14 = *a3 | (unsigned __int64)((__int64)(int)a3[1] << 32);
  v8 = std::_Conditionally_enabled_hash<unsigned __int64,1>::operator()((unsigned __int8 *)&v14);
  std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,enum MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>,0>>::_Find_last<ClientsTracker::DataOriginKey>(
    a1,
    &v13,
    a3,
    v8);
  if ( *((_QWORD *)&v13 + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v13 + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Check_max_size(a1);
    v9 = std::_Allocate<16,std::_Default_allocate_traits>(0x98u);
    std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,void *>>>::construct<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,ClientsTracker::ClientKey &,ClientsTracker::ClientValue>(
      v10,
      v9 + 2,
      a3,
      a4,
      a1 + 1,
      v9);
    if ( (unsigned __int8)std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Check_rehash_required_1(a1) )
    {
      std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Rehash_for_1(a1);
      v13 = *(_OWORD *)std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,enum MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>,0>>::_Find_last<ClientsTracker::DataOriginKey>(
                         a1,
                         &v13,
                         (_DWORD *)v9 + 4,
                         v8);
    }
    v12[1] = 0;
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,enum MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>,0>>::_Insert_new_node_before(
                      a1,
                      v8,
                      v13,
                      v9);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,void *>>>(v12);
  }
  return a2;
}

```

## disassembly

```asm
0x180008838  mov     [rsp-28h+arg_8], rbx
0x18000883d  mov     [rsp-28h+arg_10], rsi
0x180008842  push    rbp
0x180008843  push    rdi
0x180008844  push    r12
0x180008846  push    r14
0x180008848  push    r15
0x18000884a  mov     rbp, rsp
0x18000884d  sub     rsp, 40h
0x180008851  mov     r12, r9
0x180008854  mov     r15, r8
0x180008857  mov     rbx, rdx
0x18000885a  mov     rdi, rcx
0x18000885d  movsxd  r10, dword ptr [r8+4]
0x180008861  shl     r10, 20h
0x180008865  mov     eax, [r8]
0x180008868  or      r10, rax
0x18000886b  mov     [rbp+arg_0], r10
0x18000886f  lea     rcx, [rbp+arg_0]; unsigned __int8 *
0x180008873  call    ??R?$_Conditionally_enabled_hash@_K$00@std@@SA_KAEB_K@Z; std::_Conditionally_enabled_hash<unsigned __int64,1>::operator()(unsigned __int64 const &)
0x180008878  mov     r14, rax
0x18000887b  mov     r9, rax
0x18000887e  mov     r8, r15
0x180008881  lea     rdx, [rbp+var_10]
0x180008885  mov     rcx, rdi
0x180008888  call    ??$_Find_last@UDataOriginKey@ClientsTracker@@@?$_Hash@V?$_Umap_traits@UDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@V?$_Uhash_compare@UDataOriginKey@ClientsTracker@@UDataOriginKeyHasher@2@U?$equal_to@UDataOriginKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@6@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@PEAX@std@@@1@AEBUDataOriginKey@ClientsTracker@@_K@Z; std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>,0>>::_Find_last<ClientsTracker::DataOriginKey>(ClientsTracker::DataOriginKey const &,unsigned __int64)
0x18000888d  mov     rdx, qword ptr [rbp+var_10+8]
0x180008891  test    rdx, rdx
0x180008894  jz      short loc_1800088A2
0x180008896  mov     [rbx], rdx
0x180008899  mov     byte ptr [rbx+8], 0
0x18000889d  jmp     loc_180008934
0x1800088a2  mov     rcx, rdi
0x1800088a5  call    ?_Check_max_size@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@IEBAXXZ; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Check_max_size(void)
0x1800088aa  lea     rax, [rdi+8]
0x1800088ae  mov     [rbp+var_20], rax
0x1800088b2  mov     [rbp+var_18], 0
0x1800088ba  mov     ecx, 98h
0x1800088bf  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800088c4  mov     rsi, rax
0x1800088c7  mov     [rbp+var_18], rax
0x1800088cb  lea     rdx, [rax+10h]
0x1800088cf  mov     r9, r12
0x1800088d2  mov     r8, r15
0x1800088d5  call    ??$construct@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@AEAUClientKey@ClientsTracker@@UClientValue@4@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@PEAX@std@@@1@QEAU?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@1@AEAUClientKey@ClientsTracker@@$$QEAUClientValue@5@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,void *>>>::construct<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,ClientsTracker::ClientKey &,ClientsTracker::ClientValue>(std::allocator<std::_List_node<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,void *>> &,std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue> * const,ClientsTracker::ClientKey &,ClientsTracker::ClientValue &&)
0x1800088da  nop
0x1800088db  mov     rcx, rdi
0x1800088de  call    ?_Check_rehash_required_1@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@IEBA_NXZ; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Check_rehash_required_1(void)
0x1800088e3  test    al, al
0x1800088e5  jz      short loc_18000890A
0x1800088e7  mov     rcx, rdi
0x1800088ea  call    ?_Rehash_for_1@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Rehash_for_1(void)
0x1800088ef  lea     r8, [rsi+10h]
0x1800088f3  mov     r9, r14
0x1800088f6  lea     rdx, [rbp+var_10]
0x1800088fa  mov     rcx, rdi
0x1800088fd  call    ??$_Find_last@UDataOriginKey@ClientsTracker@@@?$_Hash@V?$_Umap_traits@UDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@V?$_Uhash_compare@UDataOriginKey@ClientsTracker@@UDataOriginKeyHasher@2@U?$equal_to@UDataOriginKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@6@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@PEAX@std@@@1@AEBUDataOriginKey@ClientsTracker@@_K@Z; std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>,0>>::_Find_last<ClientsTracker::DataOriginKey>(ClientsTracker::DataOriginKey const &,unsigned __int64)
0x180008902  movups  xmm0, xmmword ptr [rax]
0x180008905  movdqu  [rbp+var_10], xmm0
0x18000890a  mov     [rbp+var_18], 0
0x180008912  mov     r9, rsi
0x180008915  mov     r8, qword ptr [rbp+var_10]
0x180008919  mov     rdx, r14
0x18000891c  mov     rcx, rdi
0x18000891f  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@UDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@V?$_Uhash_compare@UDataOriginKey@ClientsTracker@@UDataOriginKeyHasher@2@U?$equal_to@UDataOriginKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@6@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>,void *> * const,std::_List_node<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>,void *> * const)
0x180008924  mov     [rbx], rax
0x180008927  mov     byte ptr [rbx+8], 1
0x18000892b  lea     rcx, [rbp+var_20]
0x18000892f  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,void *>>>(void)
0x180008934  mov     rax, rbx
0x180008937  lea     r11, [rsp+40h+var_s0]
0x18000893c  mov     rbx, [r11+38h]
0x180008940  mov     rsi, [r11+40h]
0x180008944  mov     rsp, r11
0x180008947  pop     r15
0x180008949  pop     r14
0x18000894b  pop     r12
0x18000894d  pop     rdi
0x18000894e  pop     rbp
0x18000894f  retn
```
