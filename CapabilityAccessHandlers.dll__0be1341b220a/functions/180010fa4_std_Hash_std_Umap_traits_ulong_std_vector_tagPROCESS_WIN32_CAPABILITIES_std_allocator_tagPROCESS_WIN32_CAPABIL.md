# std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180010fa4`
- end: `0x180011114`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `368`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000fe60`

## callees

- `0x18000f91c`
- `0x18001032c`
- `0x180010dbc`
- `0x180010fa4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010fdd`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010fdd`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  __int64 v4; // rbx
  unsigned __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 i; // r10
  __int64 v9; // rax
  unsigned int *v10; // rdx
  __int64 v11; // r10
  __int64 v12; // r11
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 *v15; // rax
  __int64 v16; // rdi
  _QWORD *v17; // rdx
  _QWORD *v18; // rax
  __int64 *v19; // rdi
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
  v4 = a1[1];
  LODWORD(v26) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>>>>>::_Assign_grow(
    a1 + 3,
    2 * v6,
    v4);
  a1[7] = v6;
  a1[6] = v6 - 1;
  for ( i = *(_QWORD *)a1[1]; i != v4; i = v12 )
  {
    v9 = std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>::operator()<unsigned long>(
           v7,
           i + 16);
    v13 = a1[3];
    v14 = 2 * (a1[6] & v9);
    if ( *(_QWORD *)(v13 + 16 * (a1[6] & v9)) == v4 )
    {
      *(_QWORD *)(v13 + 16 * (a1[6] & v9)) = v11;
LABEL_7:
      *(_QWORD *)(v13 + 8 * v14 + 8) = v11;
      continue;
    }
    v15 = *(__int64 **)(v13 + 16 * (a1[6] & v9) + 8);
    v7 = *v10;
    if ( (_DWORD)v7 == *((_DWORD *)v15 + 4) )
    {
      v16 = *v15;
      if ( *v15 != v11 )
      {
        v17 = *(_QWORD **)(v11 + 8);
        *v17 = v12;
        v7 = *(_QWORD *)(v12 + 8);
        *(_QWORD *)v7 = v16;
        v18 = *(_QWORD **)(v16 + 8);
        *v18 = v11;
        *(_QWORD *)(v16 + 8) = v7;
        *(_QWORD *)(v12 + 8) = v17;
        *(_QWORD *)(v11 + 8) = v18;
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
        v21 = *(_QWORD **)(v11 + 8);
        *v21 = v12;
        v7 = *(_QWORD *)(v12 + 8);
        *(_QWORD *)v7 = v20;
        v22 = *(_QWORD **)(v20 + 8);
        *v22 = v11;
        *(_QWORD *)(v20 + 8) = v7;
        *(_QWORD *)(v12 + 8) = v21;
        *(_QWORD *)(v11 + 8) = v22;
        goto LABEL_15;
      }
    }
    v23 = *(_QWORD **)(v11 + 8);
    *v23 = v12;
    v7 = *(_QWORD *)(v12 + 8);
    *(_QWORD *)v7 = v15;
    v24 = (_QWORD *)*v19;
    *v24 = v11;
    *v19 = v7;
    *(_QWORD *)(v12 + 8) = v23;
    *(_QWORD *)(v11 + 8) = v24;
    *(_QWORD *)(v13 + 8 * v14) = v11;
LABEL_15:
    ;
  }
  v26 = 0;
  return std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Clear_guard::~_Clear_guard(&v26);
}

```

## disassembly

```asm
0x180010fa4  push    rbx
0x180010fa6  push    rsi
0x180010fa7  push    rdi
0x180010fa8  push    r14
0x180010faa  sub     rsp, 28h
0x180010fae  mov     rax, 0FFFFFFFFFFFFFFFh
0x180010fb8  mov     dword ptr [rsp+48h+arg_8], 0
0x180010fc0  mov     rsi, rcx
0x180010fc3  mov     edi, 1
0x180010fc8  bsr     rcx, rax
0x180010fcc  mov     eax, edi
0x180010fce  shl     rax, cl
0x180010fd1  cmp     rdx, rax
0x180010fd4  jbe     short loc_180010FE4
0x180010fd6  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180010fdd  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180010fe4  mov     rbx, [rsi+8]
0x180010fe8  lea     rax, [rdx-1]
0x180010fec  or      rax, rdi
0x180010fef  mov     dword ptr [rsp+48h+arg_8], 0
0x180010ff7  bsr     rcx, rax
0x180010ffb  mov     r8, rbx
0x180010ffe  inc     ecx
0x180011000  shl     rdi, cl
0x180011003  lea     rcx, [rsi+18h]
0x180011007  lea     rdx, [rdi+rdi]
0x18001100b  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>>>)
0x180011010  mov     [rsi+38h], rdi
0x180011014  lea     rax, [rdi-1]
0x180011018  mov     [rsi+30h], rax
0x18001101c  mov     r10, [rsi+8]
0x180011020  mov     r10, [r10]
0x180011023  mov     r11, r10
0x180011026  cmp     r10, rbx
0x180011029  jz      loc_1800110F7
0x18001102f  mov     r11, [r11]
0x180011032  lea     rdx, [r10+10h]
0x180011036  call    ??$?RK@?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@QEBA_KAEBK@Z; std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>::operator()<ulong>(ulong const &)
0x18001103b  mov     r9, [rsi+18h]
0x18001103f  mov     r8, rax
0x180011042  and     r8, [rsi+30h]
0x180011046  add     r8, r8
0x180011049  cmp     [r9+r8*8], rbx
0x18001104d  jnz     short loc_18001105D
0x18001104f  mov     [r9+r8*8], r10
0x180011053  mov     [r9+r8*8+8], r10
0x180011058  jmp     loc_1800110EF
0x18001105d  mov     rax, [r9+r8*8+8]
0x180011062  mov     ecx, [rdx]
0x180011064  cmp     ecx, [rax+10h]
0x180011067  jnz     short loc_180011094
0x180011069  mov     rdi, [rax]
0x18001106c  cmp     rdi, r10
0x18001106f  jz      short loc_180011053
0x180011071  mov     rdx, [r10+8]
0x180011075  mov     [rdx], r11
0x180011078  mov     rcx, [r11+8]
0x18001107c  mov     [rcx], rdi
0x18001107f  mov     rax, [rdi+8]
0x180011083  mov     [rax], r10
0x180011086  mov     [rdi+8], rcx
0x18001108a  mov     [r11+8], rdx
0x18001108e  mov     [r10+8], rax
0x180011092  jmp     short loc_180011053
0x180011094  lea     rdi, [rax+8]
0x180011098  cmp     [r9+r8*8], rax
0x18001109c  jz      short loc_1800110CC
0x18001109e  mov     rax, [rdi]
0x1800110a1  cmp     ecx, [rax+10h]
0x1800110a4  jnz     short loc_180011094
0x1800110a6  mov     r8, [rax]
0x1800110a9  mov     rdx, [r10+8]
0x1800110ad  mov     [rdx], r11
0x1800110b0  mov     rcx, [r11+8]
0x1800110b4  mov     [rcx], r8
0x1800110b7  mov     rax, [r8+8]
0x1800110bb  mov     [rax], r10
0x1800110be  mov     [r8+8], rcx
0x1800110c2  mov     [r11+8], rdx
0x1800110c6  mov     [r10+8], rax
0x1800110ca  jmp     short loc_1800110EF
0x1800110cc  mov     rdx, [r10+8]
0x1800110d0  mov     [rdx], r11
0x1800110d3  mov     rcx, [r11+8]
0x1800110d7  mov     [rcx], rax
0x1800110da  mov     rax, [rdi]
0x1800110dd  mov     [rax], r10
0x1800110e0  mov     [rdi], rcx
0x1800110e3  mov     [r11+8], rdx
0x1800110e7  mov     [r10+8], rax
0x1800110eb  mov     [r9+r8*8], r10
0x1800110ef  mov     r10, r11
0x1800110f2  jmp     loc_180011026
0x1800110f7  lea     rcx, [rsp+48h+arg_8]
0x1800110fc  mov     [rsp+48h+arg_8], 0
0x180011105  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18001110a  add     rsp, 28h
0x18001110e  pop     r14
0x180011110  pop     rdi
0x180011111  pop     rsi
0x180011112  pop     rbx
0x180011113  retn
```
