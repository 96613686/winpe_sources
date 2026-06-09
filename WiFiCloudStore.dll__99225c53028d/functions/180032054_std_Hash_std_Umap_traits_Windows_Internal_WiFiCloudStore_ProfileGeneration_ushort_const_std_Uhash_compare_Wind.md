# std::_Hash<std::_Umap_traits<Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *,std::_Uhash_compare<Windows::Internal::WiFiCloudStore::ProfileGeneration,std::hash<Windows::Internal::WiFiCloudStore::ProfileGeneration>,std::equal_to<Windows::Internal::WiFiCloudStore::ProfileGeneration>>,std::allocator<std::pair<Windows::Internal::WiFiCloudStore::ProfileGeneration const,ushort const *>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180032054`
- end: `0x1800321df`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBGV?$_Uhash_compare@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@U?$hash@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@std@@U?$equal_to@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@6@@std@@V?$allocator@U?$pair@$$CBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBG@std@@@6@$0A@@std@@@std@@IEAAX_K@Z`
- size: `395`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800192d8`

## callees

- `0x1800194d4`
- `0x18002ff80`
- `0x1800302f0`
- `0x180032054`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18003208e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18003208e`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,unsigned short const *,std::_Uhash_compare<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,std::hash<enum Windows::Internal::WiFiCloudStore::ProfileGeneration>,std::equal_to<enum Windows::Internal::WiFiCloudStore::ProfileGeneration>>,std::allocator<std::pair<enum Windows::Internal::WiFiCloudStore::ProfileGeneration const,unsigned short const *>>,0>>::_Forced_rehash(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rcx
  __int64 v3; // rdi
  unsigned __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rsi
  unsigned __int8 *v7; // r11
  unsigned __int8 *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // r11
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 *v13; // rax
  int v14; // ecx
  __int64 v15; // r10
  unsigned __int8 **v16; // rdx
  _QWORD *v17; // rcx
  _QWORD *v18; // rax
  __int64 **v19; // r10
  __int64 v20; // r8
  unsigned __int8 **v21; // rdx
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  unsigned __int8 **v24; // rdx
  __int64 **v25; // rcx
  __int64 *v26; // rax
  __int64 v28; // [rsp+50h] [rbp+8h] BYREF

  HIDWORD(v28) = HIDWORD(a1);
  LODWORD(v28) = 0;
  _BitScanReverse64(&v2, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v2 )
    std::_Xlength_error("invalid hash bucket count");
  v3 = qword_180052A48;
  LODWORD(v28) = 0;
  _BitScanReverse64(&v4, (a2 - 1) | 1);
  v5 = 1LL << ((unsigned __int8)v4 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum Windows::Internal::WiFiCloudStore::ProfileGeneration const,unsigned short const *>>>>>>::_Assign_grow(
    &qword_180052A58,
    2 * v5,
    qword_180052A48);
  v6 = v5 - 1;
  qword_180052A78 = v5;
  qword_180052A70 = v5 - 1;
  v7 = *(unsigned __int8 **)qword_180052A48;
  v8 = *(unsigned __int8 **)qword_180052A48;
  while ( v7 != (unsigned __int8 *)v3 )
  {
    v8 = *(unsigned __int8 **)v8;
    v9 = std::_Conditionally_enabled_hash<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,1>::operator()(v7 + 16);
    v11 = qword_180052A58;
    v12 = 2 * (v6 & v9);
    if ( *(_QWORD *)(qword_180052A58 + 16 * (v6 & v9)) == v3 )
    {
      *(_QWORD *)(qword_180052A58 + 16 * (v6 & v9)) = v10;
LABEL_7:
      *(_QWORD *)(v11 + 8 * v12 + 8) = v10;
      goto LABEL_15;
    }
    v13 = *(__int64 **)(qword_180052A58 + 16 * (v6 & v9) + 8);
    v14 = *(_DWORD *)(v10 + 16);
    if ( v14 == *((_DWORD *)v13 + 4) )
    {
      v15 = *v13;
      if ( *v13 != v10 )
      {
        v16 = *(unsigned __int8 ***)(v10 + 8);
        *v16 = v8;
        v17 = (_QWORD *)*((_QWORD *)v8 + 1);
        *v17 = v15;
        v18 = *(_QWORD **)(v15 + 8);
        *v18 = v10;
        *(_QWORD *)(v15 + 8) = v17;
        *((_QWORD *)v8 + 1) = v16;
        *(_QWORD *)(v10 + 8) = v18;
      }
      goto LABEL_7;
    }
    while ( 1 )
    {
      v19 = (__int64 **)(v13 + 1);
      if ( *(__int64 **)(qword_180052A58 + 8 * v12) == v13 )
        break;
      v13 = *v19;
      if ( v14 == *((_DWORD *)*v19 + 4) )
      {
        v20 = *v13;
        v21 = *(unsigned __int8 ***)(v10 + 8);
        *v21 = v8;
        v22 = (_QWORD *)*((_QWORD *)v8 + 1);
        *v22 = v20;
        v23 = *(_QWORD **)(v20 + 8);
        *v23 = v10;
        *(_QWORD *)(v20 + 8) = v22;
        *((_QWORD *)v8 + 1) = v21;
        *(_QWORD *)(v10 + 8) = v23;
        goto LABEL_15;
      }
    }
    v24 = *(unsigned __int8 ***)(v10 + 8);
    *v24 = v8;
    v25 = (__int64 **)*((_QWORD *)v8 + 1);
    *v25 = v13;
    v26 = *v19;
    *v26 = v10;
    *v19 = (__int64 *)v25;
    *((_QWORD *)v8 + 1) = v24;
    *(_QWORD *)(v10 + 8) = v26;
    *(_QWORD *)(v11 + 8 * v12) = v10;
LABEL_15:
    v6 = qword_180052A70;
    v7 = v8;
  }
  v28 = 0;
  return std::_Hash<std::_Umap_traits<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,unsigned short const *,std::_Uhash_compare<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,std::hash<enum Windows::Internal::WiFiCloudStore::ProfileGeneration>,std::equal_to<enum Windows::Internal::WiFiCloudStore::ProfileGeneration>>,std::allocator<std::pair<enum Windows::Internal::WiFiCloudStore::ProfileGeneration const,unsigned short const *>>,0>>::_Clear_guard::~_Clear_guard(&v28);
}

```

## disassembly

```asm
0x180032054  mov     [rsp+arg_0], rcx
0x180032059  push    rbx
0x18003205a  push    rsi
0x18003205b  push    rdi
0x18003205c  push    r14
0x18003205e  sub     rsp, 28h
0x180032062  mov     rax, 0FFFFFFFFFFFFFFFh
0x18003206c  mov     dword ptr [rsp+48h+arg_0], 0
0x180032074  bsr     rcx, rax
0x180032078  mov     ebx, 1
0x18003207d  mov     eax, ebx
0x18003207f  shl     rax, cl
0x180032082  cmp     rdx, rax
0x180032085  jbe     short loc_180032095
0x180032087  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18003208e  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180032095  mov     rdi, cs:qword_180052A48
0x18003209c  lea     rax, [rdx-1]
0x1800320a0  or      rax, rbx
0x1800320a3  mov     dword ptr [rsp+48h+arg_0], 0
0x1800320ab  bsr     rcx, rax
0x1800320af  mov     r8, rdi
0x1800320b2  inc     ecx
0x1800320b4  shl     rbx, cl
0x1800320b7  lea     rcx, qword_180052A58
0x1800320be  lea     rdx, [rbx+rbx]
0x1800320c2  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBG@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBG@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<Windows::Internal::WiFiCloudStore::ProfileGeneration const,ushort const *>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<Windows::Internal::WiFiCloudStore::ProfileGeneration const,ushort const *>>>>)
0x1800320c7  mov     r11, cs:qword_180052A48
0x1800320ce  lea     rsi, [rbx-1]
0x1800320d2  mov     cs:qword_180052A78, rbx
0x1800320d9  mov     cs:qword_180052A70, rsi
0x1800320e0  mov     r11, [r11]
0x1800320e3  mov     rbx, r11
0x1800320e6  cmp     r11, rdi
0x1800320e9  jz      loc_1800321C2
0x1800320ef  mov     rbx, [rbx]
0x1800320f2  lea     rcx, [r11+10h]; unsigned __int8 *
0x1800320f6  call    ??R?$_Conditionally_enabled_hash@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@$00@std@@SA_KAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@Z; std::_Conditionally_enabled_hash<Windows::Internal::WiFiCloudStore::ProfileGeneration,1>::operator()(Windows::Internal::WiFiCloudStore::ProfileGeneration const &)
0x1800320fb  mov     r9, cs:qword_180052A58
0x180032102  mov     r8, rax
0x180032105  and     r8, rsi
0x180032108  add     r8, r8
0x18003210b  cmp     [r9+r8*8], rdi
0x18003210f  jnz     short loc_18003211F
0x180032111  mov     [r9+r8*8], r11
0x180032115  mov     [r9+r8*8+8], r11
0x18003211a  jmp     loc_1800321B3
0x18003211f  mov     rax, [r9+r8*8+8]
0x180032124  mov     ecx, [r11+10h]
0x180032128  cmp     ecx, [rax+10h]
0x18003212b  jnz     short loc_180032158
0x18003212d  mov     r10, [rax]
0x180032130  cmp     r10, r11
0x180032133  jz      short loc_180032115
0x180032135  mov     rdx, [r11+8]
0x180032139  mov     [rdx], rbx
0x18003213c  mov     rcx, [rbx+8]
0x180032140  mov     [rcx], r10
0x180032143  mov     rax, [r10+8]
0x180032147  mov     [rax], r11
0x18003214a  mov     [r10+8], rcx
0x18003214e  mov     [rbx+8], rdx
0x180032152  mov     [r11+8], rax
0x180032156  jmp     short loc_180032115
0x180032158  lea     r10, [rax+8]
0x18003215c  cmp     [r9+r8*8], rax
0x180032160  jz      short loc_180032190
0x180032162  mov     rax, [r10]
0x180032165  cmp     ecx, [rax+10h]
0x180032168  jnz     short loc_180032158
0x18003216a  mov     r8, [rax]
0x18003216d  mov     rdx, [r11+8]
0x180032171  mov     [rdx], rbx
0x180032174  mov     rcx, [rbx+8]
0x180032178  mov     [rcx], r8
0x18003217b  mov     rax, [r8+8]
0x18003217f  mov     [rax], r11
0x180032182  mov     [r8+8], rcx
0x180032186  mov     [rbx+8], rdx
0x18003218a  mov     [r11+8], rax
0x18003218e  jmp     short loc_1800321B3
0x180032190  mov     rdx, [r11+8]
0x180032194  mov     [rdx], rbx
0x180032197  mov     rcx, [rbx+8]
0x18003219b  mov     [rcx], rax
0x18003219e  mov     rax, [r10]
0x1800321a1  mov     [rax], r11
0x1800321a4  mov     [r10], rcx
0x1800321a7  mov     [rbx+8], rdx
0x1800321ab  mov     [r11+8], rax
0x1800321af  mov     [r9+r8*8], r11
0x1800321b3  mov     rsi, cs:qword_180052A70
0x1800321ba  mov     r11, rbx
0x1800321bd  jmp     loc_1800320E6
0x1800321c2  lea     rcx, [rsp+48h+arg_0]
0x1800321c7  mov     [rsp+48h+arg_0], 0
0x1800321d0  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBGV?$_Uhash_compare@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@U?$hash@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@std@@U?$equal_to@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@6@@std@@V?$allocator@U?$pair@$$CBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBG@std@@@6@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *,std::_Uhash_compare<Windows::Internal::WiFiCloudStore::ProfileGeneration,std::hash<Windows::Internal::WiFiCloudStore::ProfileGeneration>,std::equal_to<Windows::Internal::WiFiCloudStore::ProfileGeneration>>,std::allocator<std::pair<Windows::Internal::WiFiCloudStore::ProfileGeneration const,ushort const *>>,0>>::_Clear_guard::~_Clear_guard(void)
0x1800321d5  add     rsp, 28h
0x1800321d9  pop     r14
0x1800321db  pop     rdi
0x1800321dc  pop     rsi
0x1800321dd  pop     rbx
0x1800321de  retn
```
