# std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>,0>>::_Try_emplace<ClientsTracker::DataOriginKey const &,>(ClientsTracker::DataOriginKey const &)

- ea: `0x1800085ec`
- end: `0x18000876d`
- name: `??$_Try_emplace@AEBUDataOriginKey@ClientsTracker@@$$V@?$_Hash@V?$_Umap_traits@UDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@V?$_Uhash_compare@UDataOriginKey@ClientsTracker@@UDataOriginKeyHasher@2@U?$equal_to@UDataOriginKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@6@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@PEAX@std@@_N@1@AEBUDataOriginKey@ClientsTracker@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(float *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000a794`

## callees

- `0x1800077e0`
- `0x1800083a4`
- `0x1800085ec`
- `0x180008820`
- `0x180008cbc`
- `0x1800090a8`
- `0x18000aa68`
- `0x18000acf4`
- `0x18000ae9c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000866a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000866a`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,enum MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>,0>>::_Try_emplace<ClientsTracker::DataOriginKey const &,>(
        float *a1,
        __int64 a2,
        unsigned int *a3)
{
  __int64 v6; // r14
  _QWORD *v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  float v11; // xmm0_4
  __int64 v12; // rcx
  float v13; // xmm1_4
  __int64 v14; // rax
  __int64 v15; // rax
  _QWORD *v17; // [rsp+30h] [rbp-20h] BYREF
  _QWORD *v18; // [rsp+38h] [rbp-18h]
  __int128 v19; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v20; // [rsp+70h] [rbp+20h] BYREF

  v20 = (int)a3[1] | ((unsigned __int64)*a3 << 32);
  v6 = std::_Conditionally_enabled_hash<unsigned __int64,1>::operator()((unsigned __int8 *)&v20);
  std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,enum MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>,0>>::_Find_last<ClientsTracker::DataOriginKey>(
    a1,
    &v19,
    a3,
    v6);
  if ( *((_QWORD *)&v19 + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v19 + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( *((_QWORD *)a1 + 2) == 0x7FFFFFFFFFFFFFFLL )
      std::_Xlength_error("unordered_map/set too long");
    v20 = (unsigned __int64)a3;
    v17 = a1 + 2;
    v7 = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
    v18 = v7;
    std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>,void *>>>::construct<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>,std::piecewise_construct_t const &,std::tuple<ClientsTracker::DataOriginKey const &>,std::tuple<>>(
      v8,
      v7 + 2,
      v9,
      &v20);
    v10 = *((_QWORD *)a1 + 2) + 1LL;
    if ( v10 < 0 )
      v11 = (float)(v10 & 1 | (unsigned int)((unsigned __int64)v10 >> 1))
          + (float)(v10 & 1 | (unsigned int)((unsigned __int64)v10 >> 1));
    else
      v11 = (float)(int)v10;
    v12 = *((_QWORD *)a1 + 7);
    if ( v12 < 0 )
    {
      v14 = *((_QWORD *)a1 + 7) & 1LL | ((unsigned __int64)v12 >> 1);
      v13 = (float)(int)v14 + (float)(int)v14;
    }
    else
    {
      v13 = (float)(int)v12;
    }
    if ( (float)(v11 / v13) > *a1 )
    {
      v15 = std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,enum MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>,0>>::_Forced_rehash(
        a1,
        v15);
      v19 = *(_OWORD *)std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,enum MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>,0>>::_Find_last<ClientsTracker::DataOriginKey>(
                         a1,
                         &v19,
                         (_DWORD *)v7 + 4,
                         v6);
    }
    v18 = 0;
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,enum MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>,0>>::_Insert_new_node_before(
                      a1,
                      v6,
                      v19,
                      v7);
    *(_BYTE *)(a2 + 8) = 1;
    std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>,void *>>>(&v17);
  }
  return a2;
}

```

## disassembly

```asm
0x1800085ec  mov     [rsp-18h+arg_8], rbx
0x1800085f1  mov     [rsp-18h+arg_10], rsi
0x1800085f6  push    rbp
0x1800085f7  push    rdi
0x1800085f8  push    r14
0x1800085fa  mov     rbp, rsp
0x1800085fd  sub     rsp, 50h
0x180008601  mov     rsi, r8
0x180008604  mov     rbx, rdx
0x180008607  mov     rdi, rcx
0x18000860a  mov     r9d, [r8]
0x18000860d  shl     r9, 20h
0x180008611  movsxd  rax, dword ptr [r8+4]
0x180008615  or      r9, rax
0x180008618  mov     [rbp+arg_0], r9
0x18000861c  lea     rcx, [rbp+arg_0]; unsigned __int8 *
0x180008620  call    ??R?$_Conditionally_enabled_hash@_K$00@std@@SA_KAEB_K@Z; std::_Conditionally_enabled_hash<unsigned __int64,1>::operator()(unsigned __int64 const &)
0x180008625  mov     r14, rax
0x180008628  mov     r9, rax
0x18000862b  mov     r8, rsi
0x18000862e  lea     rdx, [rbp+var_10]
0x180008632  mov     rcx, rdi
0x180008635  call    ??$_Find_last@UDataOriginKey@ClientsTracker@@@?$_Hash@V?$_Umap_traits@UDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@V?$_Uhash_compare@UDataOriginKey@ClientsTracker@@UDataOriginKeyHasher@2@U?$equal_to@UDataOriginKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@6@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@PEAX@std@@@1@AEBUDataOriginKey@ClientsTracker@@_K@Z; std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>,0>>::_Find_last<ClientsTracker::DataOriginKey>(ClientsTracker::DataOriginKey const &,unsigned __int64)
0x18000863a  mov     rdx, qword ptr [rbp+var_10+8]
0x18000863e  test    rdx, rdx
0x180008641  jz      short loc_18000864F
0x180008643  mov     [rbx], rdx
0x180008646  mov     byte ptr [rbx+8], 0
0x18000864a  jmp     loc_180008755
0x18000864f  lea     rax, [rdi+8]
0x180008653  mov     rcx, 7FFFFFFFFFFFFFFh
0x18000865d  cmp     [rax+8], rcx
0x180008661  jnz     short loc_180008671
0x180008663  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000866a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180008671  mov     [rbp+arg_0], rsi
0x180008675  mov     [rbp+var_20], rax
0x180008679  mov     [rbp+var_18], 0
0x180008681  mov     ecx, 20h ; ' '
0x180008686  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000868b  mov     rsi, rax
0x18000868e  mov     [rbp+var_18], rax
0x180008692  lea     rdx, [rax+10h]
0x180008696  lea     r9, [rbp+arg_0]
0x18000869a  call    ??$construct@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@AEBUpiecewise_construct_t@2@V?$tuple@AEBUDataOriginKey@ClientsTracker@@@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBUDataOriginKey@ClientsTracker@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>,void *>>>::construct<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>,std::piecewise_construct_t const &,std::tuple<ClientsTracker::DataOriginKey const &>,std::tuple<>>(std::allocator<std::_List_node<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>,void *>> &,std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType> * const,std::piecewise_construct_t const &,std::tuple<ClientsTracker::DataOriginKey const &> &&,std::tuple<> &&)
0x18000869f  nop
0x1800086a0  mov     rdx, [rdi+10h]
0x1800086a4  add     rdx, 1
0x1800086a8  xorps   xmm0, xmm0
0x1800086ab  js      short loc_1800086B4
0x1800086ad  cvtsi2ss xmm0, rdx
0x1800086b2  jmp     short loc_1800086CC
0x1800086b4  mov     rcx, rdx
0x1800086b7  shr     rcx, 1
0x1800086ba  mov     rax, rdx
0x1800086bd  and     eax, 1
0x1800086c0  or      rcx, rax
0x1800086c3  cvtsi2ss xmm0, rcx
0x1800086c8  addss   xmm0, xmm0
0x1800086cc  mov     rcx, [rdi+38h]
0x1800086d0  xorps   xmm1, xmm1
0x1800086d3  test    rcx, rcx
0x1800086d6  js      short loc_1800086DF
0x1800086d8  cvtsi2ss xmm1, rcx
0x1800086dd  jmp     short loc_1800086F4
0x1800086df  mov     rax, rcx
0x1800086e2  shr     rax, 1
0x1800086e5  and     ecx, 1
0x1800086e8  or      rax, rcx
0x1800086eb  cvtsi2ss xmm1, rax
0x1800086f0  addss   xmm1, xmm1
0x1800086f4  divss   xmm0, xmm1
0x1800086f8  comiss  xmm0, dword ptr [rdi]
0x1800086fb  jbe     short loc_18000872B
0x1800086fd  mov     rcx, rdi
0x180008700  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180008705  mov     rdx, rax
0x180008708  mov     rcx, rdi
0x18000870b  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@UDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@V?$_Uhash_compare@UDataOriginKey@ClientsTracker@@UDataOriginKeyHasher@2@U?$equal_to@UDataOriginKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@6@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>,0>>::_Forced_rehash(unsigned __int64)
0x180008710  lea     r8, [rsi+10h]
0x180008714  mov     r9, r14
0x180008717  lea     rdx, [rbp+var_10]
0x18000871b  mov     rcx, rdi
0x18000871e  call    ??$_Find_last@UDataOriginKey@ClientsTracker@@@?$_Hash@V?$_Umap_traits@UDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@V?$_Uhash_compare@UDataOriginKey@ClientsTracker@@UDataOriginKeyHasher@2@U?$equal_to@UDataOriginKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@6@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@PEAX@std@@@1@AEBUDataOriginKey@ClientsTracker@@_K@Z; std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>,0>>::_Find_last<ClientsTracker::DataOriginKey>(ClientsTracker::DataOriginKey const &,unsigned __int64)
0x180008723  movups  xmm0, xmmword ptr [rax]
0x180008726  movdqu  [rbp+var_10], xmm0
0x18000872b  mov     [rbp+var_18], 0
0x180008733  mov     r9, rsi
0x180008736  mov     r8, qword ptr [rbp+var_10]
0x18000873a  mov     rdx, r14
0x18000873d  mov     rcx, rdi
0x180008740  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@UDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@V?$_Uhash_compare@UDataOriginKey@ClientsTracker@@UDataOriginKeyHasher@2@U?$equal_to@UDataOriginKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@6@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>,void *> * const,std::_List_node<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>,void *> * const)
0x180008745  mov     [rbx], rax
0x180008748  mov     byte ptr [rbx+8], 1
0x18000874c  lea     rcx, [rbp+var_20]
0x180008750  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>,void *>>>(void)
0x180008755  mov     rax, rbx
0x180008758  lea     r11, [rsp+50h+var_s0]
0x18000875d  mov     rbx, [r11+28h]
0x180008761  mov     rsi, [r11+30h]
0x180008765  mov     rsp, r11
0x180008768  pop     r14
0x18000876a  pop     rdi
0x18000876b  pop     rbp
0x18000876c  retn
```
