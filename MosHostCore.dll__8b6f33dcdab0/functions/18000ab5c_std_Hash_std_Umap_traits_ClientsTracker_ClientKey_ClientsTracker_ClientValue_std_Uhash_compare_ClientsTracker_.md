# std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x18000ab5c`
- end: `0x18000aced`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@IEAAX_K@Z`
- size: `401`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000aef4`

## callees

- `0x180008fac`
- `0x1800090a8`
- `0x18000a90c`
- `0x18000ab5c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ab98`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ab98`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  __int64 v4; // rdi
  unsigned __int64 v5; // rcx
  __int64 v6; // rbx
  _QWORD *v7; // r11
  _QWORD *v8; // rbx
  int v9; // esi
  __int64 v10; // rbp
  __int64 v11; // rax
  __int64 v12; // r11
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 *v15; // rax
  __int64 v16; // r10
  _QWORD *v17; // rdx
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  __int64 **v20; // r10
  __int64 v21; // r8
  _QWORD *v22; // rdx
  _QWORD *v23; // rcx
  _QWORD *v24; // rax
  _QWORD *v25; // rdx
  __int64 **v26; // rcx
  __int64 *v27; // rax
  __int64 v29; // [rsp+68h] [rbp+10h] BYREF

  LODWORD(v29) = 0;
  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = a1[1];
  LODWORD(v29) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>>>>>::_Assign_grow(
    a1 + 3,
    2 * v6,
    v4);
  a1[7] = v6;
  a1[6] = v6 - 1;
  v7 = *(_QWORD **)a1[1];
  v8 = v7;
  while ( v7 != (_QWORD *)v4 )
  {
    v9 = *((_DWORD *)v7 + 5);
    v10 = *((unsigned int *)v7 + 4);
    v8 = (_QWORD *)*v8;
    v29 = v10 | ((__int64)v9 << 32);
    v11 = std::_Conditionally_enabled_hash<unsigned __int64,1>::operator()((unsigned __int8 *)&v29);
    v13 = a1[3];
    v14 = 2 * (a1[6] & v11);
    if ( *(_QWORD *)(v13 + 16 * (a1[6] & v11)) == v4 )
    {
      *(_QWORD *)(v13 + 16 * (a1[6] & v11)) = v12;
LABEL_7:
      *(_QWORD *)(v13 + 8 * v14 + 8) = v12;
      goto LABEL_17;
    }
    v15 = *(__int64 **)(v13 + 16 * (a1[6] & v11) + 8);
    if ( *((_DWORD *)v15 + 4) == (_DWORD)v10 && *((_DWORD *)v15 + 5) == v9 )
    {
      v16 = *v15;
      if ( *v15 != v12 )
      {
        v17 = *(_QWORD **)(v12 + 8);
        *v17 = v8;
        v18 = (_QWORD *)v8[1];
        *v18 = v16;
        v19 = *(_QWORD **)(v16 + 8);
        *v19 = v12;
        *(_QWORD *)(v16 + 8) = v18;
        v8[1] = v17;
        *(_QWORD *)(v12 + 8) = v19;
      }
      goto LABEL_7;
    }
    while ( 1 )
    {
      v20 = (__int64 **)(v15 + 1);
      if ( *(__int64 **)(v13 + 8 * v14) == v15 )
        break;
      v15 = *v20;
      if ( *((_DWORD *)*v20 + 4) == (_DWORD)v10 && *((_DWORD *)v15 + 5) == v9 )
      {
        v21 = *v15;
        v22 = *(_QWORD **)(v12 + 8);
        *v22 = v8;
        v23 = (_QWORD *)v8[1];
        *v23 = v21;
        v24 = *(_QWORD **)(v21 + 8);
        *v24 = v12;
        *(_QWORD *)(v21 + 8) = v23;
        v8[1] = v22;
        *(_QWORD *)(v12 + 8) = v24;
        goto LABEL_17;
      }
    }
    v25 = *(_QWORD **)(v12 + 8);
    *v25 = v8;
    v26 = (__int64 **)v8[1];
    *v26 = v15;
    v27 = *v20;
    *v27 = v12;
    *v20 = (__int64 *)v26;
    v8[1] = v25;
    *(_QWORD *)(v12 + 8) = v27;
    *(_QWORD *)(v13 + 8 * v14) = v12;
LABEL_17:
    v7 = v8;
  }
  v29 = 0;
  return std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Clear_guard::~_Clear_guard(&v29);
}

```

## disassembly

```asm
0x18000ab5c  push    rbx
0x18000ab5e  push    rbp
0x18000ab5f  push    rsi
0x18000ab60  push    rdi
0x18000ab61  push    r14
0x18000ab63  push    r15
0x18000ab65  sub     rsp, 28h
0x18000ab69  mov     rax, 0FFFFFFFFFFFFFFFh
0x18000ab73  mov     dword ptr [rsp+58h+arg_8], 0
0x18000ab7b  mov     r14, rcx
0x18000ab7e  mov     ebx, 1
0x18000ab83  bsr     rcx, rax
0x18000ab87  mov     eax, ebx
0x18000ab89  shl     rax, cl
0x18000ab8c  cmp     rdx, rax
0x18000ab8f  jbe     short loc_18000AB9F
0x18000ab91  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18000ab98  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000ab9f  mov     rdi, [r14+8]
0x18000aba3  lea     rax, [rdx-1]
0x18000aba7  or      rax, rbx
0x18000abaa  mov     dword ptr [rsp+58h+arg_8], 0
0x18000abb2  bsr     rcx, rax
0x18000abb6  mov     r8, rdi
0x18000abb9  inc     ecx
0x18000abbb  shl     rbx, cl
0x18000abbe  lea     rcx, [r14+18h]
0x18000abc2  lea     rdx, [rbx+rbx]
0x18000abc6  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>)
0x18000abcb  mov     [r14+38h], rbx
0x18000abcf  lea     rax, [rbx-1]
0x18000abd3  mov     [r14+30h], rax
0x18000abd7  mov     r11, [r14+8]
0x18000abdb  mov     r11, [r11]
0x18000abde  mov     rbx, r11
0x18000abe1  lea     rcx, [rsp+58h+arg_8]; unsigned __int8 *
0x18000abe6  cmp     r11, rdi
0x18000abe9  jz      loc_18000ACD2
0x18000abef  movsxd  rsi, dword ptr [r11+14h]
0x18000abf3  mov     ebp, [r11+10h]
0x18000abf7  mov     rax, rsi
0x18000abfa  mov     rbx, [rbx]
0x18000abfd  shl     rax, 20h
0x18000ac01  or      rax, rbp
0x18000ac04  mov     [rsp+58h+arg_8], rax
0x18000ac09  call    ??R?$_Conditionally_enabled_hash@_K$00@std@@SA_KAEB_K@Z; std::_Conditionally_enabled_hash<unsigned __int64,1>::operator()(unsigned __int64 const &)
0x18000ac0e  mov     r9, [r14+18h]
0x18000ac12  mov     r8, rax
0x18000ac15  and     r8, [r14+30h]
0x18000ac19  add     r8, r8
0x18000ac1c  cmp     [r9+r8*8], rdi
0x18000ac20  jnz     short loc_18000AC30
0x18000ac22  mov     [r9+r8*8], r11
0x18000ac26  mov     [r9+r8*8+8], r11
0x18000ac2b  jmp     loc_18000ACCA
0x18000ac30  mov     rax, [r9+r8*8+8]
0x18000ac35  cmp     [rax+10h], ebp
0x18000ac38  jnz     short loc_18000AC6A
0x18000ac3a  cmp     [rax+14h], esi
0x18000ac3d  jnz     short loc_18000AC6A
0x18000ac3f  mov     r10, [rax]
0x18000ac42  cmp     r10, r11
0x18000ac45  jz      short loc_18000AC26
0x18000ac47  mov     rdx, [r11+8]
0x18000ac4b  mov     [rdx], rbx
0x18000ac4e  mov     rcx, [rbx+8]
0x18000ac52  mov     [rcx], r10
0x18000ac55  mov     rax, [r10+8]
0x18000ac59  mov     [rax], r11
0x18000ac5c  mov     [r10+8], rcx
0x18000ac60  mov     [rbx+8], rdx
0x18000ac64  mov     [r11+8], rax
0x18000ac68  jmp     short loc_18000AC26
0x18000ac6a  lea     r10, [rax+8]
0x18000ac6e  cmp     [r9+r8*8], rax
0x18000ac72  jz      short loc_18000ACA7
0x18000ac74  mov     rax, [r10]
0x18000ac77  cmp     [rax+10h], ebp
0x18000ac7a  jnz     short loc_18000AC6A
0x18000ac7c  cmp     [rax+14h], esi
0x18000ac7f  jnz     short loc_18000AC6A
0x18000ac81  mov     r8, [rax]
0x18000ac84  mov     rdx, [r11+8]
0x18000ac88  mov     [rdx], rbx
0x18000ac8b  mov     rcx, [rbx+8]
0x18000ac8f  mov     [rcx], r8
0x18000ac92  mov     rax, [r8+8]
0x18000ac96  mov     [rax], r11
0x18000ac99  mov     [r8+8], rcx
0x18000ac9d  mov     [rbx+8], rdx
0x18000aca1  mov     [r11+8], rax
0x18000aca5  jmp     short loc_18000ACCA
0x18000aca7  mov     rdx, [r11+8]
0x18000acab  mov     [rdx], rbx
0x18000acae  mov     rcx, [rbx+8]
0x18000acb2  mov     [rcx], rax
0x18000acb5  mov     rax, [r10]
0x18000acb8  mov     [rax], r11
0x18000acbb  mov     [r10], rcx
0x18000acbe  mov     [rbx+8], rdx
0x18000acc2  mov     [r11+8], rax
0x18000acc6  mov     [r9+r8*8], r11
0x18000acca  mov     r11, rbx
0x18000accd  jmp     loc_18000ABE1
0x18000acd2  mov     [rsp+58h+arg_8], 0
0x18000acdb  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18000ace0  add     rsp, 28h
0x18000ace4  pop     r15
0x18000ace6  pop     r14
0x18000ace8  pop     rdi
0x18000ace9  pop     rsi
0x18000acea  pop     rbp
0x18000aceb  pop     rbx
0x18000acec  retn
```
