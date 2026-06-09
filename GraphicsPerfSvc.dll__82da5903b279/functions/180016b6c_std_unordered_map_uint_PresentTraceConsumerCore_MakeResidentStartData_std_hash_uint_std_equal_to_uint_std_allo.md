# std::unordered_map<uint,PresentTraceConsumerCore::MakeResidentStartData,std::hash<uint>,std::equal_to<uint>,std::allocator<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>>>::_Insert_or_assign<uint,PresentTraceConsumerCore::MakeResidentStartData &>(uint &&,PresentTraceConsumerCore::MakeResidentStartData &)

- ea: `0x180016b6c`
- end: `0x180016d28`
- name: `??$_Insert_or_assign@IAEAUMakeResidentStartData@PresentTraceConsumerCore@@@?$unordered_map@IUMakeResidentStartData@PresentTraceConsumerCore@@U?$hash@I@std@@U?$equal_to@I@4@V?$allocator@U?$pair@$$CBIUMakeResidentStartData@PresentTraceConsumerCore@@@std@@@4@@std@@AEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUMakeResidentStartData@PresentTraceConsumerCore@@@std@@@std@@@std@@@std@@_N@1@$$QEAIAEAUMakeResidentStartData@PresentTraceConsumerCore@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(float *, __int64, unsigned __int8 *, _OWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019ee0`

## callees

- `0x180003ebc`
- `0x180016898`
- `0x180016b6c`
- `0x180017c54`
- `0x18001b528`
- `0x18001baec`
- `0x18001bb28`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180016be7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180016be7`

## pseudocode

```c
__int64 __fastcall std::unordered_map<unsigned int,PresentTraceConsumerCore::MakeResidentStartData>::_Insert_or_assign<unsigned int,PresentTraceConsumerCore::MakeResidentStartData &>(
        float *a1,
        __int64 a2,
        unsigned __int8 *a3,
        _OWORD *a4)
{
  __int64 appended; // r13
  __int64 v9; // rdx
  char *v10; // rbx
  __int64 v11; // rdx
  float v12; // xmm0_4
  __int64 v13; // rcx
  float v14; // xmm1_4
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  _QWORD *v18; // r8
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // r9
  _QWORD *v23; // [rsp+20h] [rbp-68h] BYREF
  char *v24; // [rsp+28h] [rbp-60h]
  _OWORD v25[5]; // [rsp+30h] [rbp-58h] BYREF

  appended = std::_Fnv1a_append_bytes((unsigned __int64)a1, a3, 4u);
  std::_Hash<std::_Umap_traits<unsigned int,unsigned __int64,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,unsigned __int64>>,0>>::_Find_last<unsigned int>(
    a1,
    v25,
    a3,
    appended);
  v9 = *((_QWORD *)&v25[0] + 1);
  if ( !*((_QWORD *)&v25[0] + 1) )
  {
    if ( *((_QWORD *)a1 + 2) == 0x666666666666666LL )
      std::_Xlength_error("unordered_map/set too long");
    v23 = a1 + 2;
    v10 = (char *)operator new(0x28u);
    v24 = v10;
    *((_DWORD *)v10 + 4) = *(_DWORD *)a3;
    *(_OWORD *)(v10 + 24) = *a4;
    v11 = *((_QWORD *)a1 + 2) + 1LL;
    if ( v11 < 0 )
      v12 = (float)(v11 & 1 | (unsigned int)((unsigned __int64)v11 >> 1))
          + (float)(v11 & 1 | (unsigned int)((unsigned __int64)v11 >> 1));
    else
      v12 = (float)(int)v11;
    v13 = *((_QWORD *)a1 + 7);
    if ( v13 < 0 )
    {
      v15 = *((_QWORD *)a1 + 7) & 1LL | ((unsigned __int64)v13 >> 1);
      v14 = (float)(int)v15 + (float)(int)v15;
    }
    else
    {
      v14 = (float)(int)v13;
    }
    if ( (float)(v12 / v14) > *a1 )
    {
      v16 = std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Umap_traits<unsigned int,PresentTraceConsumerCore::MakeResidentStartData,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,PresentTraceConsumerCore::MakeResidentStartData>>,0>>::_Forced_rehash(
        a1,
        v16);
      v25[0] = *(_OWORD *)std::_Hash<std::_Umap_traits<unsigned int,unsigned __int64,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,unsigned __int64>>,0>>::_Find_last<unsigned int>(
                            a1,
                            v25,
                            (_DWORD *)v10 + 4,
                            appended);
    }
    v24 = 0;
    v17 = *(_QWORD *)&v25[0];
    v18 = *(_QWORD **)(*(_QWORD *)&v25[0] + 8LL);
    ++*((_QWORD *)a1 + 2);
    *(_QWORD *)v10 = v17;
    *((_QWORD *)v10 + 1) = v18;
    *v18 = v10;
    *(_QWORD *)(v17 + 8) = v10;
    v19 = 2 * (appended & *((_QWORD *)a1 + 6));
    v20 = *((_QWORD *)a1 + 3);
    v21 = *(_QWORD *)(v20 + 16 * (appended & *((_QWORD *)a1 + 6)));
    if ( v21 == *((_QWORD *)a1 + 1) )
    {
      *(_QWORD *)(v20 + 16 * (appended & *((_QWORD *)a1 + 6))) = v10;
LABEL_18:
      *(_QWORD *)(v20 + 8 * v19 + 8) = v10;
      goto LABEL_19;
    }
    if ( v21 == v17 )
    {
      *(_QWORD *)(v20 + 16 * (appended & *((_QWORD *)a1 + 6))) = v10;
    }
    else if ( *(_QWORD **)(v20 + 16 * (appended & *((_QWORD *)a1 + 6)) + 8) == v18 )
    {
      goto LABEL_18;
    }
LABEL_19:
    *(_QWORD *)a2 = v10;
    *(_BYTE *)(a2 + 8) = 1;
    std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<unsigned int const,PresentTraceConsumerCore::MakeResidentStartData>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<unsigned int const,PresentTraceConsumerCore::MakeResidentStartData>,void *>>>(&v23);
    return a2;
  }
  *(_OWORD *)(*((_QWORD *)&v25[0] + 1) + 24LL) = *a4;
  *(_QWORD *)a2 = v9;
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x180016b6c  push    rbx
0x180016b6e  push    rbp
0x180016b6f  push    rsi
0x180016b70  push    rdi
0x180016b71  push    r12
0x180016b73  push    r13
0x180016b75  push    r14
0x180016b77  push    r15
0x180016b79  sub     rsp, 48h
0x180016b7d  mov     r14, r9
0x180016b80  mov     r15, r8
0x180016b83  mov     rdi, rdx
0x180016b86  mov     rsi, rcx
0x180016b89  mov     r8d, 4; unsigned __int64
0x180016b8f  mov     rdx, r15; unsigned __int8 *
0x180016b92  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x180016b97  mov     r13, rax
0x180016b9a  mov     r9, rax
0x180016b9d  mov     r8, r15
0x180016ba0  lea     rdx, [rsp+88h+var_58]
0x180016ba5  mov     rcx, rsi
0x180016ba8  call    ??$_Find_last@I@?$_Hash@V?$_Umap_traits@I_KV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBI_K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBI_K@std@@PEAX@std@@@1@AEBI_K@Z; std::_Hash<std::_Umap_traits<uint,unsigned __int64,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,unsigned __int64>>,0>>::_Find_last<uint>(uint const &,unsigned __int64)
0x180016bad  mov     rdx, qword ptr [rsp+88h+var_58+8]
0x180016bb2  test    rdx, rdx
0x180016bb5  jz      short loc_180016BCC
0x180016bb7  movups  xmm0, xmmword ptr [r14]
0x180016bbb  movdqu  xmmword ptr [rdx+18h], xmm0
0x180016bc0  mov     [rdi], rdx
0x180016bc3  mov     byte ptr [rdi+8], 0
0x180016bc7  jmp     loc_180016D14
0x180016bcc  lea     rbp, [rsi+8]
0x180016bd0  mov     rax, 666666666666666h
0x180016bda  cmp     [rbp+8], rax
0x180016bde  jnz     short loc_180016BEE
0x180016be0  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180016be7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180016bee  mov     [rsp+88h+var_68], rbp
0x180016bf3  mov     [rsp+88h+var_60], 0
0x180016bfc  mov     ecx, 28h ; '('; Size
0x180016c01  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016c06  mov     rbx, rax
0x180016c09  mov     [rsp+88h+var_60], rax
0x180016c0e  mov     ecx, [r15]
0x180016c11  mov     [rax+10h], ecx
0x180016c14  movups  xmm0, xmmword ptr [r14]
0x180016c18  movdqu  xmmword ptr [rax+18h], xmm0
0x180016c1d  mov     rdx, [rsi+10h]
0x180016c21  add     rdx, 1
0x180016c25  xorps   xmm0, xmm0
0x180016c28  js      short loc_180016C31
0x180016c2a  cvtsi2ss xmm0, rdx
0x180016c2f  jmp     short loc_180016C49
0x180016c31  mov     rcx, rdx
0x180016c34  shr     rcx, 1
0x180016c37  mov     rax, rdx
0x180016c3a  and     eax, 1
0x180016c3d  or      rcx, rax
0x180016c40  cvtsi2ss xmm0, rcx
0x180016c45  addss   xmm0, xmm0
0x180016c49  mov     rcx, [rsi+38h]
0x180016c4d  xorps   xmm1, xmm1
0x180016c50  test    rcx, rcx
0x180016c53  js      short loc_180016C5C
0x180016c55  cvtsi2ss xmm1, rcx
0x180016c5a  jmp     short loc_180016C71
0x180016c5c  mov     rax, rcx
0x180016c5f  shr     rax, 1
0x180016c62  and     ecx, 1
0x180016c65  or      rax, rcx
0x180016c68  cvtsi2ss xmm1, rax
0x180016c6d  addss   xmm1, xmm1
0x180016c71  divss   xmm0, xmm1
0x180016c75  comiss  xmm0, dword ptr [rsi]
0x180016c78  jbe     short loc_180016CAA
0x180016c7a  mov     rcx, rsi
0x180016c7d  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180016c82  mov     rdx, rax
0x180016c85  mov     rcx, rsi
0x180016c88  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@IUMakeResidentStartData@PresentTraceConsumerCore@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMakeResidentStartData@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<uint,PresentTraceConsumerCore::MakeResidentStartData,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>>,0>>::_Forced_rehash(unsigned __int64)
0x180016c8d  mov     r9, r13
0x180016c90  lea     r8, [rbx+10h]
0x180016c94  lea     rdx, [rsp+88h+var_58]
0x180016c99  mov     rcx, rsi
0x180016c9c  call    ??$_Find_last@I@?$_Hash@V?$_Umap_traits@I_KV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBI_K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBI_K@std@@PEAX@std@@@1@AEBI_K@Z; std::_Hash<std::_Umap_traits<uint,unsigned __int64,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,unsigned __int64>>,0>>::_Find_last<uint>(uint const &,unsigned __int64)
0x180016ca1  movups  xmm0, xmmword ptr [rax]
0x180016ca4  movdqu  [rsp+88h+var_58], xmm0
0x180016caa  mov     [rsp+88h+var_60], 0
0x180016cb3  mov     rdx, qword ptr [rsp+88h+var_58]
0x180016cb8  mov     r8, [rdx+8]
0x180016cbc  inc     qword ptr [rsi+10h]
0x180016cc0  mov     [rbx], rdx
0x180016cc3  mov     [rbx+8], r8
0x180016cc7  mov     [r8], rbx
0x180016cca  mov     [rdx+8], rbx
0x180016cce  mov     rax, [rsi+30h]
0x180016cd2  and     rax, r13
0x180016cd5  add     rax, rax
0x180016cd8  mov     rcx, [rsi+18h]
0x180016cdc  mov     r9, [rcx+rax*8]
0x180016ce0  cmp     r9, [rbp+0]
0x180016ce4  jnz     short loc_180016CEC
0x180016ce6  mov     [rcx+rax*8], rbx
0x180016cea  jmp     short loc_180016CFE
0x180016cec  cmp     r9, rdx
0x180016cef  jnz     short loc_180016CF7
0x180016cf1  mov     [rcx+rax*8], rbx
0x180016cf5  jmp     short loc_180016D03
0x180016cf7  cmp     [rcx+rax*8+8], r8
0x180016cfc  jnz     short loc_180016D03
0x180016cfe  mov     [rcx+rax*8+8], rbx
0x180016d03  mov     [rdi], rbx
0x180016d06  mov     byte ptr [rdi+8], 1
0x180016d0a  lea     rcx, [rsp+88h+var_68]
0x180016d0f  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@U?$pair@$$CBIUMakeResidentStartData@PresentTraceConsumerCore@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>,void *>>>(void)
0x180016d14  mov     rax, rdi
0x180016d17  add     rsp, 48h
0x180016d1b  pop     r15
0x180016d1d  pop     r14
0x180016d1f  pop     r13
0x180016d21  pop     r12
0x180016d23  pop     rdi
0x180016d24  pop     rsi
0x180016d25  pop     rbp
0x180016d26  pop     rbx
0x180016d27  retn
```
