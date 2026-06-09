# std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x18000acf4`
- end: `0x18000ae89`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@UDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@V?$_Uhash_compare@UDataOriginKey@ClientsTracker@@UDataOriginKeyHasher@2@U?$equal_to@UDataOriginKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@6@$0A@@std@@@std@@IEAAX_K@Z`
- size: `405`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800085ec`

## callees

- `0x180009008`
- `0x1800090a8`
- `0x18000a90c`
- `0x18000acf4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ad30`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ad30`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,enum MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  __int64 v4; // rdi
  unsigned __int64 v5; // rcx
  __int64 v6; // rbx
  _QWORD *v7; // r11
  _QWORD *v8; // rbx
  unsigned int v9; // ebp
  __int64 v10; // rsi
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
  unsigned __int64 v29; // [rsp+68h] [rbp+10h] BYREF

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
    v9 = *((_DWORD *)v7 + 4);
    v10 = *((int *)v7 + 5);
    v8 = (_QWORD *)*v8;
    v29 = v10 | ((unsigned __int64)v9 << 32);
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
    if ( *((_DWORD *)v15 + 4) == v9 && *((_DWORD *)v15 + 5) == (_DWORD)v10 )
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
      if ( *((_DWORD *)*v20 + 4) == v9 && *((_DWORD *)v15 + 5) == (_DWORD)v10 )
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
  return std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,enum MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>,0>>::_Clear_guard::~_Clear_guard(&v29);
}

```

## disassembly

```asm
0x18000acf4  push    rbx
0x18000acf6  push    rbp
0x18000acf7  push    rsi
0x18000acf8  push    rdi
0x18000acf9  push    r14
0x18000acfb  push    r15
0x18000acfd  sub     rsp, 28h
0x18000ad01  mov     rax, 0FFFFFFFFFFFFFFFh
0x18000ad0b  mov     dword ptr [rsp+58h+arg_8], 0
0x18000ad13  mov     r14, rcx
0x18000ad16  mov     ebx, 1
0x18000ad1b  bsr     rcx, rax
0x18000ad1f  mov     eax, ebx
0x18000ad21  shl     rax, cl
0x18000ad24  cmp     rdx, rax
0x18000ad27  jbe     short loc_18000AD37
0x18000ad29  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18000ad30  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000ad37  mov     rdi, [r14+8]
0x18000ad3b  lea     rax, [rdx-1]
0x18000ad3f  or      rax, rbx
0x18000ad42  mov     dword ptr [rsp+58h+arg_8], 0
0x18000ad4a  bsr     rcx, rax
0x18000ad4e  mov     r8, rdi
0x18000ad51  inc     ecx
0x18000ad53  shl     rbx, cl
0x18000ad56  lea     rcx, [r14+18h]
0x18000ad5a  lea     rdx, [rbx+rbx]
0x18000ad5e  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>)
0x18000ad63  mov     [r14+38h], rbx
0x18000ad67  lea     rax, [rbx-1]
0x18000ad6b  mov     [r14+30h], rax
0x18000ad6f  mov     r11, [r14+8]
0x18000ad73  mov     r11, [r11]
0x18000ad76  mov     rbx, r11
0x18000ad79  cmp     r11, rdi
0x18000ad7c  jz      loc_18000AE69
0x18000ad82  mov     ebp, [r11+10h]
0x18000ad86  movsxd  rsi, dword ptr [r11+14h]
0x18000ad8a  mov     ecx, ebp
0x18000ad8c  mov     rbx, [rbx]
0x18000ad8f  shl     rcx, 20h
0x18000ad93  or      rcx, rsi
0x18000ad96  mov     [rsp+58h+arg_8], rcx
0x18000ad9b  lea     rcx, [rsp+58h+arg_8]; unsigned __int8 *
0x18000ada0  call    ??R?$_Conditionally_enabled_hash@_K$00@std@@SA_KAEB_K@Z; std::_Conditionally_enabled_hash<unsigned __int64,1>::operator()(unsigned __int64 const &)
0x18000ada5  mov     r9, [r14+18h]
0x18000ada9  mov     r8, rax
0x18000adac  and     r8, [r14+30h]
0x18000adb0  add     r8, r8
0x18000adb3  cmp     [r9+r8*8], rdi
0x18000adb7  jnz     short loc_18000ADC7
0x18000adb9  mov     [r9+r8*8], r11
0x18000adbd  mov     [r9+r8*8+8], r11
0x18000adc2  jmp     loc_18000AE61
0x18000adc7  mov     rax, [r9+r8*8+8]
0x18000adcc  cmp     [rax+10h], ebp
0x18000adcf  jnz     short loc_18000AE01
0x18000add1  cmp     [rax+14h], esi
0x18000add4  jnz     short loc_18000AE01
0x18000add6  mov     r10, [rax]
0x18000add9  cmp     r10, r11
0x18000addc  jz      short loc_18000ADBD
0x18000adde  mov     rdx, [r11+8]
0x18000ade2  mov     [rdx], rbx
0x18000ade5  mov     rcx, [rbx+8]
0x18000ade9  mov     [rcx], r10
0x18000adec  mov     rax, [r10+8]
0x18000adf0  mov     [rax], r11
0x18000adf3  mov     [r10+8], rcx
0x18000adf7  mov     [rbx+8], rdx
0x18000adfb  mov     [r11+8], rax
0x18000adff  jmp     short loc_18000ADBD
0x18000ae01  lea     r10, [rax+8]
0x18000ae05  cmp     [r9+r8*8], rax
0x18000ae09  jz      short loc_18000AE3E
0x18000ae0b  mov     rax, [r10]
0x18000ae0e  cmp     [rax+10h], ebp
0x18000ae11  jnz     short loc_18000AE01
0x18000ae13  cmp     [rax+14h], esi
0x18000ae16  jnz     short loc_18000AE01
0x18000ae18  mov     r8, [rax]
0x18000ae1b  mov     rdx, [r11+8]
0x18000ae1f  mov     [rdx], rbx
0x18000ae22  mov     rcx, [rbx+8]
0x18000ae26  mov     [rcx], r8
0x18000ae29  mov     rax, [r8+8]
0x18000ae2d  mov     [rax], r11
0x18000ae30  mov     [r8+8], rcx
0x18000ae34  mov     [rbx+8], rdx
0x18000ae38  mov     [r11+8], rax
0x18000ae3c  jmp     short loc_18000AE61
0x18000ae3e  mov     rdx, [r11+8]
0x18000ae42  mov     [rdx], rbx
0x18000ae45  mov     rcx, [rbx+8]
0x18000ae49  mov     [rcx], rax
0x18000ae4c  mov     rax, [r10]
0x18000ae4f  mov     [rax], r11
0x18000ae52  mov     [r10], rcx
0x18000ae55  mov     [rbx+8], rdx
0x18000ae59  mov     [r11+8], rax
0x18000ae5d  mov     [r9+r8*8], r11
0x18000ae61  mov     r11, rbx
0x18000ae64  jmp     loc_18000AD79
0x18000ae69  lea     rcx, [rsp+58h+arg_8]
0x18000ae6e  mov     [rsp+58h+arg_8], 0
0x18000ae77  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@UDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@V?$_Uhash_compare@UDataOriginKey@ClientsTracker@@UDataOriginKeyHasher@2@U?$equal_to@UDataOriginKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@6@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18000ae7c  add     rsp, 28h
0x18000ae80  pop     r15
0x18000ae82  pop     r14
0x18000ae84  pop     rdi
0x18000ae85  pop     rsi
0x18000ae86  pop     rbp
0x18000ae87  pop     rbx
0x18000ae88  retn
```
