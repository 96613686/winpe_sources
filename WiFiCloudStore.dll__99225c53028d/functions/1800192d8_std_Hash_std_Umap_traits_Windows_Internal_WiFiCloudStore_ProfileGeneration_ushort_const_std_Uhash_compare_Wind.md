# std::_Hash<std::_Umap_traits<Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *,std::_Uhash_compare<Windows::Internal::WiFiCloudStore::ProfileGeneration,std::hash<Windows::Internal::WiFiCloudStore::ProfileGeneration>,std::equal_to<Windows::Internal::WiFiCloudStore::ProfileGeneration>>,std::allocator<std::pair<Windows::Internal::WiFiCloudStore::ProfileGeneration const,ushort const *>>,0>>::emplace<std::pair<Windows::Internal::WiFiCloudStore::ProfileGeneration const,ushort const *> const &>(std::pair<Windows::Internal::WiFiCloudStore::ProfileGeneration const,ushort const *> const &)

- ea: `0x1800192d8`
- end: `0x18001943e`
- name: `??$emplace@AEBU?$pair@$$CBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBG@std@@@?$_Hash@V?$_Umap_traits@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBGV?$_Uhash_compare@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@U?$hash@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@std@@U?$equal_to@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@6@@std@@V?$allocator@U?$pair@$$CBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBG@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBG@std@@@std@@@std@@@std@@_N@1@AEBU?$pair@$$CBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBG@1@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180019230`

## callees

- `0x18000a188`
- `0x1800192d8`
- `0x18001993c`
- `0x18001e66c`
- `0x1800302f0`
- `0x180031f8c`
- `0x180032054`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180019352`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180019352`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,unsigned short const *,std::_Uhash_compare<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,std::hash<enum Windows::Internal::WiFiCloudStore::ProfileGeneration>,std::equal_to<enum Windows::Internal::WiFiCloudStore::ProfileGeneration>>,std::allocator<std::pair<enum Windows::Internal::WiFiCloudStore::ProfileGeneration const,unsigned short const *>>,0>>::emplace<std::pair<enum Windows::Internal::WiFiCloudStore::ProfileGeneration const,unsigned short const *> const &>(
        __int64 a1,
        __int64 a2,
        unsigned __int8 *a3)
{
  __int64 v5; // rbp
  __int64 v6; // rax
  __int64 v7; // rdi
  _OWORD *v8; // r14
  unsigned __int64 v9; // rdx
  float v10; // xmm0_4
  __int64 v11; // rcx
  float v12; // xmm1_4
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 *v17; // [rsp+20h] [rbp-48h] BYREF
  _OWORD *v18; // [rsp+28h] [rbp-40h]

  v5 = std::_Conditionally_enabled_hash<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,1>::operator()(a3);
  v6 = *(_QWORD *)(qword_180052A58 + 16 * (qword_180052A70 & v5) + 8);
  v7 = qword_180052A48;
  if ( v6 == qword_180052A48 )
  {
LABEL_6:
    if ( qword_180052A50 == 0x7FFFFFFFFFFFFFFLL )
      std::_Xlength_error("unordered_map/set too long");
    v17 = &qword_180052A48;
    v8 = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
    v18 = v8;
    v8[1] = *(_OWORD *)a3;
    v9 = qword_180052A50 + 1;
    if ( qword_180052A50 + 1 < 0 )
      v10 = (float)(int)(v9 & 1 | (v9 >> 1)) + (float)(int)(v9 & 1 | (v9 >> 1));
    else
      v10 = (float)(int)v9;
    v11 = qword_180052A78;
    if ( qword_180052A78 < 0 )
    {
      v11 = qword_180052A78 & 1;
      v12 = (float)(int)(v11 | ((unsigned __int64)qword_180052A78 >> 1))
          + (float)(int)(v11 | ((unsigned __int64)qword_180052A78 >> 1));
    }
    else
    {
      v12 = (float)(int)qword_180052A78;
    }
    if ( (float)(v10 / v12) > *(float *)&c_wiFiCloudStoreDataReferenceCollectionNames )
    {
      v13 = std::_Hash<std::_Umap_traits<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,unsigned short const *,std::_Uhash_compare<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,std::hash<enum Windows::Internal::WiFiCloudStore::ProfileGeneration>,std::equal_to<enum Windows::Internal::WiFiCloudStore::ProfileGeneration>>,std::allocator<std::pair<enum Windows::Internal::WiFiCloudStore::ProfileGeneration const,unsigned short const *>>,0>>::_Desired_grow_bucket_count(
              v11,
              v9);
      std::_Hash<std::_Umap_traits<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,unsigned short const *,std::_Uhash_compare<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,std::hash<enum Windows::Internal::WiFiCloudStore::ProfileGeneration>,std::equal_to<enum Windows::Internal::WiFiCloudStore::ProfileGeneration>>,std::allocator<std::pair<enum Windows::Internal::WiFiCloudStore::ProfileGeneration const,unsigned short const *>>,0>>::_Forced_rehash(
        v14,
        v13);
      v7 = *std::_Hash<std::_Umap_traits<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,unsigned short const *,std::_Uhash_compare<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,std::hash<enum Windows::Internal::WiFiCloudStore::ProfileGeneration>,std::equal_to<enum Windows::Internal::WiFiCloudStore::ProfileGeneration>>,std::allocator<std::pair<enum Windows::Internal::WiFiCloudStore::ProfileGeneration const,unsigned short const *>>,0>>::_Find_last<enum Windows::Internal::WiFiCloudStore::ProfileGeneration>(
              v15,
              &v17,
              (_DWORD *)v8 + 4,
              v5);
    }
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,unsigned short const *,std::_Uhash_compare<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,std::hash<enum Windows::Internal::WiFiCloudStore::ProfileGeneration>,std::equal_to<enum Windows::Internal::WiFiCloudStore::ProfileGeneration>>,std::allocator<std::pair<enum Windows::Internal::WiFiCloudStore::ProfileGeneration const,unsigned short const *>>,0>>::_Insert_new_node_before(
                      v11,
                      v5,
                      v7,
                      v8,
                      v17,
                      v18);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    while ( *(_DWORD *)a3 != *(_DWORD *)(v6 + 16) )
    {
      if ( v6 == *(_QWORD *)(qword_180052A58 + 16 * (qword_180052A70 & v5)) )
      {
        v7 = v6;
        goto LABEL_6;
      }
      v6 = *(_QWORD *)(v6 + 8);
    }
    *(_QWORD *)a2 = v6;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x1800192d8  push    rbx
0x1800192da  push    rbp
0x1800192db  push    rsi
0x1800192dc  push    rdi
0x1800192dd  push    r14
0x1800192df  push    r15
0x1800192e1  sub     rsp, 38h
0x1800192e5  mov     rsi, r8
0x1800192e8  mov     rbx, rdx
0x1800192eb  mov     rcx, r8; unsigned __int8 *
0x1800192ee  call    ??R?$_Conditionally_enabled_hash@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@$00@std@@SA_KAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@Z; std::_Conditionally_enabled_hash<Windows::Internal::WiFiCloudStore::ProfileGeneration,1>::operator()(Windows::Internal::WiFiCloudStore::ProfileGeneration const &)
0x1800192f3  mov     rbp, rax
0x1800192f6  mov     rcx, rax
0x1800192f9  and     rcx, cs:qword_180052A70
0x180019300  add     rcx, rcx
0x180019303  mov     rdx, cs:qword_180052A58
0x18001930a  mov     rax, [rdx+rcx*8+8]
0x18001930f  mov     rdi, cs:qword_180052A48
0x180019316  cmp     rax, rdi
0x180019319  jz      short loc_180019338
0x18001931b  mov     r8, [rdx+rcx*8]
0x18001931f  mov     ecx, [rsi]
0x180019321  cmp     ecx, [rax+10h]
0x180019324  jz      loc_180019427
0x18001932a  cmp     rax, r8
0x18001932d  jz      short loc_180019335
0x18001932f  mov     rax, [rax+8]
0x180019333  jmp     short loc_180019321
0x180019335  mov     rdi, rax
0x180019338  mov     rax, 7FFFFFFFFFFFFFFh
0x180019342  cmp     cs:qword_180052A50, rax
0x180019349  jnz     short loc_180019359
0x18001934b  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180019352  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180019359  lea     rax, qword_180052A48
0x180019360  mov     [rsp+68h+var_48], rax
0x180019365  mov     [rsp+68h+var_40], 0
0x18001936e  mov     ecx, 20h ; ' '
0x180019373  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180019378  mov     r14, rax
0x18001937b  mov     [rsp+68h+var_40], rax
0x180019380  movups  xmm0, xmmword ptr [rsi]
0x180019383  movdqu  xmmword ptr [rax+10h], xmm0
0x180019388  mov     rdx, cs:qword_180052A50
0x18001938f  add     rdx, 1
0x180019393  xorps   xmm0, xmm0
0x180019396  js      short loc_18001939F
0x180019398  cvtsi2ss xmm0, rdx
0x18001939d  jmp     short loc_1800193B7
0x18001939f  mov     rcx, rdx
0x1800193a2  shr     rcx, 1
0x1800193a5  mov     rax, rdx
0x1800193a8  and     eax, 1
0x1800193ab  or      rcx, rax
0x1800193ae  cvtsi2ss xmm0, rcx
0x1800193b3  addss   xmm0, xmm0
0x1800193b7  mov     rcx, cs:qword_180052A78
0x1800193be  xorps   xmm1, xmm1
0x1800193c1  test    rcx, rcx
0x1800193c4  js      short loc_1800193CD
0x1800193c6  cvtsi2ss xmm1, rcx
0x1800193cb  jmp     short loc_1800193E2
0x1800193cd  mov     rax, rcx
0x1800193d0  shr     rax, 1
0x1800193d3  and     ecx, 1
0x1800193d6  or      rax, rcx
0x1800193d9  cvtsi2ss xmm1, rax
0x1800193de  addss   xmm1, xmm1
0x1800193e2  divss   xmm0, xmm1
0x1800193e6  comiss  xmm0, cs:?c_wiFiCloudStoreDataReferenceCollectionNames@@3V?$unordered_map@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBGU?$hash@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@std@@U?$equal_to@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@6@V?$allocator@U?$pair@$$CBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBG@std@@@6@@std@@B; std::unordered_map<Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *> const c_wiFiCloudStoreDataReferenceCollectionNames
0x1800193ed  jbe     short loc_180019410
0x1800193ef  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBGV?$_Uhash_compare@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@U?$hash@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@std@@U?$equal_to@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@6@@std@@V?$allocator@U?$pair@$$CBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBG@std@@@6@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *,std::_Uhash_compare<Windows::Internal::WiFiCloudStore::ProfileGeneration,std::hash<Windows::Internal::WiFiCloudStore::ProfileGeneration>,std::equal_to<Windows::Internal::WiFiCloudStore::ProfileGeneration>>,std::allocator<std::pair<Windows::Internal::WiFiCloudStore::ProfileGeneration const,ushort const *>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x1800193f4  mov     rdx, rax
0x1800193f7  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBGV?$_Uhash_compare@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@U?$hash@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@std@@U?$equal_to@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@6@@std@@V?$allocator@U?$pair@$$CBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBG@std@@@6@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *,std::_Uhash_compare<Windows::Internal::WiFiCloudStore::ProfileGeneration,std::hash<Windows::Internal::WiFiCloudStore::ProfileGeneration>,std::equal_to<Windows::Internal::WiFiCloudStore::ProfileGeneration>>,std::allocator<std::pair<Windows::Internal::WiFiCloudStore::ProfileGeneration const,ushort const *>>,0>>::_Forced_rehash(unsigned __int64)
0x1800193fc  mov     r9, rbp
0x1800193ff  lea     r8, [r14+10h]
0x180019403  lea     rdx, [rsp+68h+var_48]
0x180019408  call    ??$_Find_last@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@?$_Hash@V?$_Umap_traits@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBGV?$_Uhash_compare@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@U?$hash@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@std@@U?$equal_to@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@6@@std@@V?$allocator@U?$pair@$$CBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBG@std@@@6@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBG@std@@PEAX@std@@@1@AEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@_K@Z; std::_Hash<std::_Umap_traits<Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *,std::_Uhash_compare<Windows::Internal::WiFiCloudStore::ProfileGeneration,std::hash<Windows::Internal::WiFiCloudStore::ProfileGeneration>,std::equal_to<Windows::Internal::WiFiCloudStore::ProfileGeneration>>,std::allocator<std::pair<Windows::Internal::WiFiCloudStore::ProfileGeneration const,ushort const *>>,0>>::_Find_last<Windows::Internal::WiFiCloudStore::ProfileGeneration>(Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64)
0x18001940d  mov     rdi, [rax]
0x180019410  mov     r9, r14
0x180019413  mov     r8, rdi
0x180019416  mov     rdx, rbp
0x180019419  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBGV?$_Uhash_compare@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@U?$hash@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@std@@U?$equal_to@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@6@@std@@V?$allocator@U?$pair@$$CBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBG@std@@@6@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBG@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *,std::_Uhash_compare<Windows::Internal::WiFiCloudStore::ProfileGeneration,std::hash<Windows::Internal::WiFiCloudStore::ProfileGeneration>,std::equal_to<Windows::Internal::WiFiCloudStore::ProfileGeneration>>,std::allocator<std::pair<Windows::Internal::WiFiCloudStore::ProfileGeneration const,ushort const *>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<Windows::Internal::WiFiCloudStore::ProfileGeneration const,ushort const *>,void *> * const,std::_List_node<std::pair<Windows::Internal::WiFiCloudStore::ProfileGeneration const,ushort const *>,void *> * const)
0x18001941e  mov     [rbx], rax
0x180019421  mov     byte ptr [rbx+8], 1
0x180019425  jmp     short loc_18001942E
0x180019427  mov     [rbx], rax
0x18001942a  mov     byte ptr [rbx+8], 0
0x18001942e  mov     rax, rbx
0x180019431  add     rsp, 38h
0x180019435  pop     r15
0x180019437  pop     r14
0x180019439  pop     rdi
0x18001943a  pop     rsi
0x18001943b  pop     rbp
0x18001943c  pop     rbx
0x18001943d  retn
```
