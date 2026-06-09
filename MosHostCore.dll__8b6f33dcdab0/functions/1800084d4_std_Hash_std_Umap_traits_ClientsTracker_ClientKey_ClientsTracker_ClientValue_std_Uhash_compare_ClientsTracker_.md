# std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Try_emplace<ClientsTracker::ClientKey const &,>(ClientsTracker::ClientKey const &)

- ea: `0x1800084d4`
- end: `0x1800085e3`
- name: `??$_Try_emplace@AEBUClientKey@ClientsTracker@@$$V@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@PEAX@std@@_N@1@AEBUClientKey@ClientsTracker@@@Z`
- size: `271`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned int *)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180009128`
- `0x18000a198`
- `0x18000a838`

## callees

- `0x1800077e0`
- `0x1800083a4`
- `0x1800084d4`
- `0x180008808`
- `0x180008d80`
- `0x1800090a8`
- `0x18000a9a0`
- `0x18000a9d0`
- `0x18000ae9c`
- `0x18000aef4`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Try_emplace<ClientsTracker::ClientKey const &,>(
        _QWORD *a1,
        __int64 a2,
        unsigned int *a3)
{
  __int64 v6; // r14
  _QWORD *v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // r8
  _QWORD *v11; // [rsp+30h] [rbp-20h] BYREF
  _QWORD *v12; // [rsp+38h] [rbp-18h]
  __int128 v13; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v14; // [rsp+70h] [rbp+20h] BYREF

  v14 = *a3 | (unsigned __int64)((__int64)(int)a3[1] << 32);
  v6 = std::_Conditionally_enabled_hash<unsigned __int64,1>::operator()((unsigned __int8 *)&v14);
  std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,enum MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>,0>>::_Find_last<ClientsTracker::DataOriginKey>(
    a1,
    &v13,
    a3,
    v6);
  if ( *((_QWORD *)&v13 + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v13 + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Check_max_size(a1);
    v14 = (unsigned __int64)a3;
    v11 = a1 + 1;
    v7 = std::_Allocate<16,std::_Default_allocate_traits>(0x98u);
    v12 = v7;
    std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,void *>>>::construct<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,std::piecewise_construct_t const &,std::tuple<ClientsTracker::ClientKey const &>,std::tuple<>>(
      v8,
      v7 + 2,
      v9,
      &v14);
    if ( (unsigned __int8)std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Check_rehash_required_1(a1) )
    {
      std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Rehash_for_1(a1);
      v13 = *(_OWORD *)std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,enum MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>,0>>::_Find_last<ClientsTracker::DataOriginKey>(
                         a1,
                         &v13,
                         (_DWORD *)v7 + 4,
                         v6);
    }
    v12 = 0;
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,enum MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>,0>>::_Insert_new_node_before(
                      a1,
                      v6,
                      v13,
                      v7);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,void *>>>(&v11);
  }
  return a2;
}

```

## disassembly

```asm
0x1800084d4  mov     [rsp-18h+arg_8], rbx
0x1800084d9  mov     [rsp-18h+arg_10], rsi
0x1800084de  push    rbp
0x1800084df  push    rdi
0x1800084e0  push    r14
0x1800084e2  mov     rbp, rsp
0x1800084e5  sub     rsp, 50h
0x1800084e9  mov     rsi, r8
0x1800084ec  mov     rbx, rdx
0x1800084ef  mov     rdi, rcx
0x1800084f2  movsxd  r9, dword ptr [r8+4]
0x1800084f6  shl     r9, 20h
0x1800084fa  mov     eax, [r8]
0x1800084fd  or      r9, rax
0x180008500  mov     [rbp+arg_0], r9
0x180008504  lea     rcx, [rbp+arg_0]; unsigned __int8 *
0x180008508  call    ??R?$_Conditionally_enabled_hash@_K$00@std@@SA_KAEB_K@Z; std::_Conditionally_enabled_hash<unsigned __int64,1>::operator()(unsigned __int64 const &)
0x18000850d  mov     r14, rax
0x180008510  mov     r9, rax
0x180008513  mov     r8, rsi
0x180008516  lea     rdx, [rbp+var_10]
0x18000851a  mov     rcx, rdi
0x18000851d  call    ??$_Find_last@UDataOriginKey@ClientsTracker@@@?$_Hash@V?$_Umap_traits@UDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@V?$_Uhash_compare@UDataOriginKey@ClientsTracker@@UDataOriginKeyHasher@2@U?$equal_to@UDataOriginKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@6@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@PEAX@std@@@1@AEBUDataOriginKey@ClientsTracker@@_K@Z; std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>,0>>::_Find_last<ClientsTracker::DataOriginKey>(ClientsTracker::DataOriginKey const &,unsigned __int64)
0x180008522  mov     rdx, qword ptr [rbp+var_10+8]
0x180008526  test    rdx, rdx
0x180008529  jz      short loc_180008537
0x18000852b  mov     [rbx], rdx
0x18000852e  mov     byte ptr [rbx+8], 0
0x180008532  jmp     loc_1800085CB
0x180008537  mov     rcx, rdi
0x18000853a  call    ?_Check_max_size@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@IEBAXXZ; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Check_max_size(void)
0x18000853f  mov     [rbp+arg_0], rsi
0x180008543  lea     rax, [rdi+8]
0x180008547  mov     [rbp+var_20], rax
0x18000854b  mov     [rbp+var_18], 0
0x180008553  mov     ecx, 98h
0x180008558  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000855d  mov     rsi, rax
0x180008560  mov     [rbp+var_18], rax
0x180008564  lea     rdx, [rax+10h]
0x180008568  lea     r9, [rbp+arg_0]
0x18000856c  call    ??$construct@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@AEBUpiecewise_construct_t@2@V?$tuple@AEBUClientKey@ClientsTracker@@@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@PEAX@std@@@1@QEAU?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBUClientKey@ClientsTracker@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,void *>>>::construct<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,std::piecewise_construct_t const &,std::tuple<ClientsTracker::ClientKey const &>,std::tuple<>>(std::allocator<std::_List_node<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,void *>> &,std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue> * const,std::piecewise_construct_t const &,std::tuple<ClientsTracker::ClientKey const &> &&,std::tuple<> &&)
0x180008571  nop
0x180008572  mov     rcx, rdi
0x180008575  call    ?_Check_rehash_required_1@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@IEBA_NXZ; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Check_rehash_required_1(void)
0x18000857a  test    al, al
0x18000857c  jz      short loc_1800085A1
0x18000857e  mov     rcx, rdi
0x180008581  call    ?_Rehash_for_1@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Rehash_for_1(void)
0x180008586  lea     r8, [rsi+10h]
0x18000858a  mov     r9, r14
0x18000858d  lea     rdx, [rbp+var_10]
0x180008591  mov     rcx, rdi
0x180008594  call    ??$_Find_last@UDataOriginKey@ClientsTracker@@@?$_Hash@V?$_Umap_traits@UDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@V?$_Uhash_compare@UDataOriginKey@ClientsTracker@@UDataOriginKeyHasher@2@U?$equal_to@UDataOriginKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@6@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@PEAX@std@@@1@AEBUDataOriginKey@ClientsTracker@@_K@Z; std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>,0>>::_Find_last<ClientsTracker::DataOriginKey>(ClientsTracker::DataOriginKey const &,unsigned __int64)
0x180008599  movups  xmm0, xmmword ptr [rax]
0x18000859c  movdqu  [rbp+var_10], xmm0
0x1800085a1  mov     [rbp+var_18], 0
0x1800085a9  mov     r9, rsi
0x1800085ac  mov     r8, qword ptr [rbp+var_10]
0x1800085b0  mov     rdx, r14
0x1800085b3  mov     rcx, rdi
0x1800085b6  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@UDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@V?$_Uhash_compare@UDataOriginKey@ClientsTracker@@UDataOriginKeyHasher@2@U?$equal_to@UDataOriginKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@6@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>,void *> * const,std::_List_node<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>,void *> * const)
0x1800085bb  mov     [rbx], rax
0x1800085be  mov     byte ptr [rbx+8], 1
0x1800085c2  lea     rcx, [rbp+var_20]
0x1800085c6  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>,void *>>>(void)
0x1800085cb  mov     rax, rbx
0x1800085ce  lea     r11, [rsp+50h+var_s0]
0x1800085d3  mov     rbx, [r11+28h]
0x1800085d7  mov     rsi, [r11+30h]
0x1800085db  mov     rsp, r11
0x1800085de  pop     r14
0x1800085e0  pop     rdi
0x1800085e1  pop     rbp
0x1800085e2  retn
```
