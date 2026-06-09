# std::_Hash<std::_Umap_traits<uint,PresentTraceConsumerCore::MakeResidentStartData,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x18001bb28`
- end: `0x18001bc9e`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@IUMakeResidentStartData@PresentTraceConsumerCore@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMakeResidentStartData@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@IEAAX_K@Z`
- size: `374`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016b6c`

## callees

- `0x1800186b0`
- `0x18001b36c`
- `0x18001baec`
- `0x18001bb28`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001bb61`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001bb61`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned int,PresentTraceConsumerCore::MakeResidentStartData,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,PresentTraceConsumerCore::MakeResidentStartData>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  _QWORD *v4; // rdi
  unsigned __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rcx
  _QWORD *v8; // r11
  _QWORD *v9; // rbx
  __int64 appended; // rax
  unsigned int *v11; // rdx
  __int64 v12; // r11
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 *v15; // rax
  __int64 v16; // r10
  _QWORD *v17; // rdx
  _QWORD *v18; // rax
  __int64 *v19; // r10
  __int64 v20; // r8
  _QWORD *v21; // rdx
  _QWORD *v22; // rax
  _QWORD *v23; // rdx
  _QWORD *v24; // rax
  __int64 v26; // [rsp+58h] [rbp+10h] BYREF

  LODWORD(v26) = 0;
  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = (_QWORD *)a1[1];
  LODWORD(v26) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned int>>>>>>::_Assign_grow(
    a1 + 3,
    2 * v6,
    v4);
  a1[7] = v6;
  a1[6] = v6 - 1;
  v8 = *(_QWORD **)a1[1];
  v9 = v8;
  while ( v8 != v4 )
  {
    v9 = (_QWORD *)*v9;
    appended = std::_Fnv1a_append_bytes(v7, (const unsigned __int8 *const)v8 + 16, 4u);
    v13 = a1[3];
    v14 = 2 * (a1[6] & appended);
    if ( *(_QWORD **)(v13 + 16 * (a1[6] & appended)) == v4 )
    {
      *(_QWORD *)(v13 + 16 * (a1[6] & appended)) = v12;
LABEL_7:
      *(_QWORD *)(v13 + 8 * v14 + 8) = v12;
      goto LABEL_15;
    }
    v15 = *(__int64 **)(v13 + 16 * (a1[6] & appended) + 8);
    v7 = *v11;
    if ( (_DWORD)v7 == *((_DWORD *)v15 + 4) )
    {
      v16 = *v15;
      if ( *v15 != v12 )
      {
        v17 = *(_QWORD **)(v12 + 8);
        *v17 = v9;
        v7 = v9[1];
        *(_QWORD *)v7 = v16;
        v18 = *(_QWORD **)(v16 + 8);
        *v18 = v12;
        *(_QWORD *)(v16 + 8) = v7;
        v9[1] = v17;
        *(_QWORD *)(v12 + 8) = v18;
      }
      goto LABEL_7;
    }
    while ( 1 )
    {
      v19 = v15 + 1;
      if ( *(__int64 **)(v13 + 8 * v14) == v15 )
        break;
      v15 = (__int64 *)*v19;
      if ( (_DWORD)v7 == *(_DWORD *)(*v19 + 16) )
      {
        v20 = *v15;
        v21 = *(_QWORD **)(v12 + 8);
        *v21 = v9;
        v7 = v9[1];
        *(_QWORD *)v7 = v20;
        v22 = *(_QWORD **)(v20 + 8);
        *v22 = v12;
        *(_QWORD *)(v20 + 8) = v7;
        v9[1] = v21;
        *(_QWORD *)(v12 + 8) = v22;
        goto LABEL_15;
      }
    }
    v23 = *(_QWORD **)(v12 + 8);
    *v23 = v9;
    v7 = v9[1];
    *(_QWORD *)v7 = v15;
    v24 = (_QWORD *)*v19;
    *v24 = v12;
    *v19 = v7;
    v9[1] = v23;
    *(_QWORD *)(v12 + 8) = v24;
    *(_QWORD *)(v13 + 8 * v14) = v12;
LABEL_15:
    v8 = v9;
  }
  v26 = 0;
  return std::_Hash<std::_Umap_traits<unsigned int,PresentTraceConsumerCore::MakeResidentStartData,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,PresentTraceConsumerCore::MakeResidentStartData>>,0>>::_Clear_guard::~_Clear_guard(&v26);
}

```

## disassembly

```asm
0x18001bb28  push    rbx
0x18001bb2a  push    rsi
0x18001bb2b  push    rdi
0x18001bb2c  push    r14
0x18001bb2e  sub     rsp, 28h
0x18001bb32  mov     rax, 0FFFFFFFFFFFFFFFh
0x18001bb3c  mov     dword ptr [rsp+48h+arg_8], 0
0x18001bb44  mov     rsi, rcx
0x18001bb47  mov     ebx, 1
0x18001bb4c  bsr     rcx, rax
0x18001bb50  mov     eax, ebx
0x18001bb52  shl     rax, cl
0x18001bb55  cmp     rdx, rax
0x18001bb58  jbe     short loc_18001BB68
0x18001bb5a  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18001bb61  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001bb68  mov     rdi, [rsi+8]
0x18001bb6c  lea     rax, [rdx-1]
0x18001bb70  or      rax, rbx
0x18001bb73  mov     dword ptr [rsp+48h+arg_8], 0
0x18001bb7b  bsr     rcx, rax
0x18001bb7f  mov     r8, rdi
0x18001bb82  inc     ecx
0x18001bb84  shl     rbx, cl
0x18001bb87  lea     rcx, [rsi+18h]
0x18001bb8b  lea     rdx, [rbx+rbx]
0x18001bb8f  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KI@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KI@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,uint>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,uint>>>>)
0x18001bb94  mov     [rsi+38h], rbx
0x18001bb98  lea     rax, [rbx-1]
0x18001bb9c  mov     [rsi+30h], rax
0x18001bba0  mov     r11, [rsi+8]
0x18001bba4  mov     r11, [r11]
0x18001bba7  mov     rbx, r11
0x18001bbaa  cmp     r11, rdi
0x18001bbad  jz      loc_18001BC81
0x18001bbb3  mov     rbx, [rbx]
0x18001bbb6  lea     rdx, [r11+10h]; unsigned __int8 *
0x18001bbba  mov     r8d, 4; unsigned __int64
0x18001bbc0  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18001bbc5  mov     r9, [rsi+18h]
0x18001bbc9  mov     r8, rax
0x18001bbcc  and     r8, [rsi+30h]
0x18001bbd0  add     r8, r8
0x18001bbd3  cmp     [r9+r8*8], rdi
0x18001bbd7  jnz     short loc_18001BBE7
0x18001bbd9  mov     [r9+r8*8], r11
0x18001bbdd  mov     [r9+r8*8+8], r11
0x18001bbe2  jmp     loc_18001BC79
0x18001bbe7  mov     rax, [r9+r8*8+8]
0x18001bbec  mov     ecx, [rdx]
0x18001bbee  cmp     ecx, [rax+10h]
0x18001bbf1  jnz     short loc_18001BC1E
0x18001bbf3  mov     r10, [rax]
0x18001bbf6  cmp     r10, r11
0x18001bbf9  jz      short loc_18001BBDD
0x18001bbfb  mov     rdx, [r11+8]
0x18001bbff  mov     [rdx], rbx
0x18001bc02  mov     rcx, [rbx+8]
0x18001bc06  mov     [rcx], r10
0x18001bc09  mov     rax, [r10+8]
0x18001bc0d  mov     [rax], r11
0x18001bc10  mov     [r10+8], rcx
0x18001bc14  mov     [rbx+8], rdx
0x18001bc18  mov     [r11+8], rax
0x18001bc1c  jmp     short loc_18001BBDD
0x18001bc1e  lea     r10, [rax+8]
0x18001bc22  cmp     [r9+r8*8], rax
0x18001bc26  jz      short loc_18001BC56
0x18001bc28  mov     rax, [r10]
0x18001bc2b  cmp     ecx, [rax+10h]
0x18001bc2e  jnz     short loc_18001BC1E
0x18001bc30  mov     r8, [rax]
0x18001bc33  mov     rdx, [r11+8]
0x18001bc37  mov     [rdx], rbx
0x18001bc3a  mov     rcx, [rbx+8]
0x18001bc3e  mov     [rcx], r8
0x18001bc41  mov     rax, [r8+8]
0x18001bc45  mov     [rax], r11
0x18001bc48  mov     [r8+8], rcx
0x18001bc4c  mov     [rbx+8], rdx
0x18001bc50  mov     [r11+8], rax
0x18001bc54  jmp     short loc_18001BC79
0x18001bc56  mov     rdx, [r11+8]
0x18001bc5a  mov     [rdx], rbx
0x18001bc5d  mov     rcx, [rbx+8]
0x18001bc61  mov     [rcx], rax
0x18001bc64  mov     rax, [r10]
0x18001bc67  mov     [rax], r11
0x18001bc6a  mov     [r10], rcx
0x18001bc6d  mov     [rbx+8], rdx
0x18001bc71  mov     [r11+8], rax
0x18001bc75  mov     [r9+r8*8], r11
0x18001bc79  mov     r11, rbx
0x18001bc7c  jmp     loc_18001BBAA
0x18001bc81  lea     rcx, [rsp+48h+arg_8]
0x18001bc86  mov     [rsp+48h+arg_8], 0
0x18001bc8f  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@IUMakeResidentStartData@PresentTraceConsumerCore@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMakeResidentStartData@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<uint,PresentTraceConsumerCore::MakeResidentStartData,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18001bc94  add     rsp, 28h
0x18001bc98  pop     r14
0x18001bc9a  pop     rdi
0x18001bc9b  pop     rsi
0x18001bc9c  pop     rbx
0x18001bc9d  retn
```
