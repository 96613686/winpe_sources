# std::_Hash<std::_Umap_traits<uint,std::shared_ptr<OdmlMapDataPackage>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<OdmlMapDataPackage>>>,0>>::_Try_emplace<uint,>(uint &&)

- ea: `0x18000e2b0`
- end: `0x18000e41e`
- name: `??$_Try_emplace@I$$V@?$_Hash@V?$_Umap_traits@IV?$shared_ptr@VOdmlMapDataPackage@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VOdmlMapDataPackage@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBIV?$shared_ptr@VOdmlMapDataPackage@@@std@@@std@@PEAX@std@@_N@1@$$QEAI@Z`
- size: `366`
- prototype: `__int64 __fastcall(float *, __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800105a0`

## callees

- `0x1800077e0`
- `0x18000aa68`
- `0x18000ae9c`
- `0x18000da10`
- `0x18000e2b0`
- `0x18000e464`
- `0x18000e748`
- `0x18000ea1c`
- `0x180010f4c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000e31b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000e31b`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<OdmlMapDataPackage>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<OdmlMapDataPackage>>>,0>>::_Try_emplace<unsigned int,>(
        float *a1,
        __int64 a2,
        unsigned __int8 *a3)
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
  unsigned __int8 *v20; // [rsp+70h] [rbp+20h] BYREF

  v6 = std::_Conditionally_enabled_hash<unsigned int,1>::operator()(a3);
  std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<OdmlMapDataPackage>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<OdmlMapDataPackage>>>,0>>::_Find_last<unsigned int>(
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
    if ( *((_QWORD *)a1 + 2) == 0x666666666666666LL )
      std::_Xlength_error("unordered_map/set too long");
    v20 = a3;
    v17 = a1 + 2;
    v7 = std::_Allocate<16,std::_Default_allocate_traits>(0x28u);
    v18 = v7;
    std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<unsigned int const,std::shared_ptr<OdmlMapDataPackage>>,void *>>>::construct<std::pair<unsigned int const,std::shared_ptr<OdmlMapDataPackage>>,std::piecewise_construct_t const &,std::tuple<unsigned int &&>,std::tuple<>>(
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
      std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<OdmlMapDataPackage>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<OdmlMapDataPackage>>>,0>>::_Forced_rehash(
        a1,
        v15);
      v19 = *(_OWORD *)std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<OdmlMapDataPackage>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<OdmlMapDataPackage>>>,0>>::_Find_last<unsigned int>(
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
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned int const,std::shared_ptr<OdmlMapDataPackage>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned int const,std::shared_ptr<OdmlMapDataPackage>>,void *>>>(&v17);
  }
  return a2;
}

```

## disassembly

```asm
0x18000e2b0  mov     [rsp-18h+arg_8], rbx
0x18000e2b5  mov     [rsp-18h+arg_10], rsi
0x18000e2ba  push    rbp
0x18000e2bb  push    rdi
0x18000e2bc  push    r14
0x18000e2be  mov     rbp, rsp
0x18000e2c1  sub     rsp, 50h
0x18000e2c5  mov     rsi, r8
0x18000e2c8  mov     rbx, rdx
0x18000e2cb  mov     rdi, rcx
0x18000e2ce  mov     rcx, r8; unsigned __int8 *
0x18000e2d1  call    ??R?$_Conditionally_enabled_hash@I$00@std@@SA_KAEBI@Z; std::_Conditionally_enabled_hash<uint,1>::operator()(uint const &)
0x18000e2d6  mov     r14, rax
0x18000e2d9  mov     r9, rax
0x18000e2dc  mov     r8, rsi
0x18000e2df  lea     rdx, [rbp+var_10]
0x18000e2e3  mov     rcx, rdi
0x18000e2e6  call    ??$_Find_last@I@?$_Hash@V?$_Umap_traits@IV?$shared_ptr@VOdmlMapDataPackage@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VOdmlMapDataPackage@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBIV?$shared_ptr@VOdmlMapDataPackage@@@std@@@std@@PEAX@std@@@1@AEBI_K@Z; std::_Hash<std::_Umap_traits<uint,std::shared_ptr<OdmlMapDataPackage>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<OdmlMapDataPackage>>>,0>>::_Find_last<uint>(uint const &,unsigned __int64)
0x18000e2eb  mov     rdx, qword ptr [rbp+var_10+8]
0x18000e2ef  test    rdx, rdx
0x18000e2f2  jz      short loc_18000E300
0x18000e2f4  mov     [rbx], rdx
0x18000e2f7  mov     byte ptr [rbx+8], 0
0x18000e2fb  jmp     loc_18000E406
0x18000e300  lea     rax, [rdi+8]
0x18000e304  mov     rcx, 666666666666666h
0x18000e30e  cmp     [rax+8], rcx
0x18000e312  jnz     short loc_18000E322
0x18000e314  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000e31b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000e322  mov     [rbp+arg_0], rsi
0x18000e326  mov     [rbp+var_20], rax
0x18000e32a  mov     [rbp+var_18], 0
0x18000e332  mov     ecx, 28h ; '('
0x18000e337  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000e33c  mov     rsi, rax
0x18000e33f  mov     [rbp+var_18], rax
0x18000e343  lea     rdx, [rax+10h]
0x18000e347  lea     r9, [rbp+arg_0]
0x18000e34b  call    ??$construct@U?$pair@$$CBIV?$shared_ptr@VOdmlMapDataPackage@@@std@@@std@@AEBUpiecewise_construct_t@2@V?$tuple@$$QEAI@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@$$CBIV?$shared_ptr@VOdmlMapDataPackage@@@std@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBIV?$shared_ptr@VOdmlMapDataPackage@@@std@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBIV?$shared_ptr@VOdmlMapDataPackage@@@std@@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@$$QEAI@1@$$QEAV?$tuple@$$V@1@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<uint const,std::shared_ptr<OdmlMapDataPackage>>,void *>>>::construct<std::pair<uint const,std::shared_ptr<OdmlMapDataPackage>>,std::piecewise_construct_t const &,std::tuple<uint &&>,std::tuple<>>(std::allocator<std::_List_node<std::pair<uint const,std::shared_ptr<OdmlMapDataPackage>>,void *>> &,std::pair<uint const,std::shared_ptr<OdmlMapDataPackage>> * const,std::piecewise_construct_t const &,std::tuple<uint &&> &&,std::tuple<> &&)
0x18000e350  nop
0x18000e351  mov     rdx, [rdi+10h]
0x18000e355  add     rdx, 1
0x18000e359  xorps   xmm0, xmm0
0x18000e35c  js      short loc_18000E365
0x18000e35e  cvtsi2ss xmm0, rdx
0x18000e363  jmp     short loc_18000E37D
0x18000e365  mov     rcx, rdx
0x18000e368  shr     rcx, 1
0x18000e36b  mov     rax, rdx
0x18000e36e  and     eax, 1
0x18000e371  or      rcx, rax
0x18000e374  cvtsi2ss xmm0, rcx
0x18000e379  addss   xmm0, xmm0
0x18000e37d  mov     rcx, [rdi+38h]
0x18000e381  xorps   xmm1, xmm1
0x18000e384  test    rcx, rcx
0x18000e387  js      short loc_18000E390
0x18000e389  cvtsi2ss xmm1, rcx
0x18000e38e  jmp     short loc_18000E3A5
0x18000e390  mov     rax, rcx
0x18000e393  shr     rax, 1
0x18000e396  and     ecx, 1
0x18000e399  or      rax, rcx
0x18000e39c  cvtsi2ss xmm1, rax
0x18000e3a1  addss   xmm1, xmm1
0x18000e3a5  divss   xmm0, xmm1
0x18000e3a9  comiss  xmm0, dword ptr [rdi]
0x18000e3ac  jbe     short loc_18000E3DC
0x18000e3ae  mov     rcx, rdi
0x18000e3b1  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18000e3b6  mov     rdx, rax
0x18000e3b9  mov     rcx, rdi
0x18000e3bc  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@IV?$shared_ptr@VOdmlMapDataPackage@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VOdmlMapDataPackage@@@std@@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<uint,std::shared_ptr<OdmlMapDataPackage>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<OdmlMapDataPackage>>>,0>>::_Forced_rehash(unsigned __int64)
0x18000e3c1  lea     r8, [rsi+10h]
0x18000e3c5  mov     r9, r14
0x18000e3c8  lea     rdx, [rbp+var_10]
0x18000e3cc  mov     rcx, rdi
0x18000e3cf  call    ??$_Find_last@I@?$_Hash@V?$_Umap_traits@IV?$shared_ptr@VOdmlMapDataPackage@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VOdmlMapDataPackage@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBIV?$shared_ptr@VOdmlMapDataPackage@@@std@@@std@@PEAX@std@@@1@AEBI_K@Z; std::_Hash<std::_Umap_traits<uint,std::shared_ptr<OdmlMapDataPackage>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<OdmlMapDataPackage>>>,0>>::_Find_last<uint>(uint const &,unsigned __int64)
0x18000e3d4  movups  xmm0, xmmword ptr [rax]
0x18000e3d7  movdqu  [rbp+var_10], xmm0
0x18000e3dc  mov     [rbp+var_18], 0
0x18000e3e4  mov     r9, rsi
0x18000e3e7  mov     r8, qword ptr [rbp+var_10]
0x18000e3eb  mov     rdx, r14
0x18000e3ee  mov     rcx, rdi
0x18000e3f1  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@UDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@V?$_Uhash_compare@UDataOriginKey@ClientsTracker@@UDataOriginKeyHasher@2@U?$equal_to@UDataOriginKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@6@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>,void *> * const,std::_List_node<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>,void *> * const)
0x18000e3f6  mov     [rbx], rax
0x18000e3f9  mov     byte ptr [rbx+8], 1
0x18000e3fd  lea     rcx, [rbp+var_20]
0x18000e401  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBIV?$shared_ptr@VOdmlMapDataPackage@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<uint const,std::shared_ptr<OdmlMapDataPackage>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<uint const,std::shared_ptr<OdmlMapDataPackage>>,void *>>>(void)
0x18000e406  mov     rax, rbx
0x18000e409  lea     r11, [rsp+50h+var_s0]
0x18000e40e  mov     rbx, [r11+28h]
0x18000e412  mov     rsi, [r11+30h]
0x18000e416  mov     rsp, r11
0x18000e419  pop     r14
0x18000e41b  pop     rdi
0x18000e41c  pop     rbp
0x18000e41d  retn
```
