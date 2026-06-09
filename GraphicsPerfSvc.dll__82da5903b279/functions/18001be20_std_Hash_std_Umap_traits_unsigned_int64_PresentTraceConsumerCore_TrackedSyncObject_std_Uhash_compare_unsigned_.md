# std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x18001be20`
- end: `0x18001bf99`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@IEAAX_K@Z`
- size: `377`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001740c`

## callees

- `0x1800186e8`
- `0x18001b36c`
- `0x18001baec`
- `0x18001be20`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001be59`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001be59`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  _QWORD *v4; // rdi
  unsigned __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 **v7; // rcx
  _QWORD *v8; // r11
  _QWORD *v9; // rbx
  __int64 appended; // rax
  __int64 ***v11; // rdx
  __int64 v12; // r11
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 *v15; // rax
  __int64 *v16; // r10
  _QWORD *v17; // rdx
  _QWORD *v18; // rax
  __int64 **v19; // r10
  __int64 *v20; // r8
  _QWORD *v21; // rdx
  _QWORD *v22; // rax
  _QWORD *v23; // rdx
  __int64 *v24; // rax
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
    appended = std::_Fnv1a_append_bytes((__int64)v7, (const unsigned __int8 *const)v8 + 16, 8u);
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
    if ( *v11 == (__int64 **)v15[2] )
    {
      v16 = (__int64 *)*v15;
      if ( *v15 != v12 )
      {
        v17 = *(_QWORD **)(v12 + 8);
        *v17 = v9;
        v7 = (__int64 **)v9[1];
        *v7 = v16;
        v18 = (_QWORD *)v16[1];
        *v18 = v12;
        v16[1] = (__int64)v7;
        v9[1] = v17;
        *(_QWORD *)(v12 + 8) = v18;
      }
      goto LABEL_7;
    }
    while ( 1 )
    {
      v19 = (__int64 **)(v15 + 1);
      if ( *(__int64 **)(v13 + 8 * v14) == v15 )
        break;
      v15 = *v19;
      if ( v7 == (__int64 **)(*v19)[2] )
      {
        v20 = (__int64 *)*v15;
        v21 = *(_QWORD **)(v12 + 8);
        *v21 = v9;
        v7 = (__int64 **)v9[1];
        *v7 = v20;
        v22 = (_QWORD *)v20[1];
        *v22 = v12;
        v20[1] = (__int64)v7;
        v9[1] = v21;
        *(_QWORD *)(v12 + 8) = v22;
        goto LABEL_15;
      }
    }
    v23 = *(_QWORD **)(v12 + 8);
    *v23 = v9;
    v7 = (__int64 **)v9[1];
    *v7 = v15;
    v24 = *v19;
    *v24 = v12;
    *v19 = (__int64 *)v7;
    v9[1] = v23;
    *(_QWORD *)(v12 + 8) = v24;
    *(_QWORD *)(v13 + 8 * v14) = v12;
LABEL_15:
    v8 = v9;
  }
  v26 = 0;
  return std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Clear_guard::~_Clear_guard(&v26);
}

```

## disassembly

```asm
0x18001be20  push    rbx
0x18001be22  push    rsi
0x18001be23  push    rdi
0x18001be24  push    r14
0x18001be26  sub     rsp, 28h
0x18001be2a  mov     rax, 0FFFFFFFFFFFFFFFh
0x18001be34  mov     dword ptr [rsp+48h+arg_8], 0
0x18001be3c  mov     rsi, rcx
0x18001be3f  mov     ebx, 1
0x18001be44  bsr     rcx, rax
0x18001be48  mov     eax, ebx
0x18001be4a  shl     rax, cl
0x18001be4d  cmp     rdx, rax
0x18001be50  jbe     short loc_18001BE60
0x18001be52  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18001be59  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001be60  mov     rdi, [rsi+8]
0x18001be64  lea     rax, [rdx-1]
0x18001be68  or      rax, rbx
0x18001be6b  mov     dword ptr [rsp+48h+arg_8], 0
0x18001be73  bsr     rcx, rax
0x18001be77  mov     r8, rdi
0x18001be7a  inc     ecx
0x18001be7c  shl     rbx, cl
0x18001be7f  lea     rcx, [rsi+18h]
0x18001be83  lea     rdx, [rbx+rbx]
0x18001be87  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KI@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KI@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,uint>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,uint>>>>)
0x18001be8c  mov     [rsi+38h], rbx
0x18001be90  lea     rax, [rbx-1]
0x18001be94  mov     [rsi+30h], rax
0x18001be98  mov     r11, [rsi+8]
0x18001be9c  mov     r11, [r11]
0x18001be9f  mov     rbx, r11
0x18001bea2  cmp     r11, rdi
0x18001bea5  jz      loc_18001BF7C
0x18001beab  mov     rbx, [rbx]
0x18001beae  lea     rdx, [r11+10h]; unsigned __int8 *
0x18001beb2  mov     r8d, 8; unsigned __int64
0x18001beb8  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18001bebd  mov     r9, [rsi+18h]
0x18001bec1  mov     r8, rax
0x18001bec4  and     r8, [rsi+30h]
0x18001bec8  add     r8, r8
0x18001becb  cmp     [r9+r8*8], rdi
0x18001becf  jnz     short loc_18001BEDF
0x18001bed1  mov     [r9+r8*8], r11
0x18001bed5  mov     [r9+r8*8+8], r11
0x18001beda  jmp     loc_18001BF74
0x18001bedf  mov     rax, [r9+r8*8+8]
0x18001bee4  mov     rcx, [rdx]
0x18001bee7  cmp     rcx, [rax+10h]
0x18001beeb  jnz     short loc_18001BF18
0x18001beed  mov     r10, [rax]
0x18001bef0  cmp     r10, r11
0x18001bef3  jz      short loc_18001BED5
0x18001bef5  mov     rdx, [r11+8]
0x18001bef9  mov     [rdx], rbx
0x18001befc  mov     rcx, [rbx+8]
0x18001bf00  mov     [rcx], r10
0x18001bf03  mov     rax, [r10+8]
0x18001bf07  mov     [rax], r11
0x18001bf0a  mov     [r10+8], rcx
0x18001bf0e  mov     [rbx+8], rdx
0x18001bf12  mov     [r11+8], rax
0x18001bf16  jmp     short loc_18001BED5
0x18001bf18  lea     r10, [rax+8]
0x18001bf1c  cmp     [r9+r8*8], rax
0x18001bf20  jz      short loc_18001BF51
0x18001bf22  mov     rax, [r10]
0x18001bf25  cmp     rcx, [rax+10h]
0x18001bf29  jnz     short loc_18001BF18
0x18001bf2b  mov     r8, [rax]
0x18001bf2e  mov     rdx, [r11+8]
0x18001bf32  mov     [rdx], rbx
0x18001bf35  mov     rcx, [rbx+8]
0x18001bf39  mov     [rcx], r8
0x18001bf3c  mov     rax, [r8+8]
0x18001bf40  mov     [rax], r11
0x18001bf43  mov     [r8+8], rcx
0x18001bf47  mov     [rbx+8], rdx
0x18001bf4b  mov     [r11+8], rax
0x18001bf4f  jmp     short loc_18001BF74
0x18001bf51  mov     rdx, [r11+8]
0x18001bf55  mov     [rdx], rbx
0x18001bf58  mov     rcx, [rbx+8]
0x18001bf5c  mov     [rcx], rax
0x18001bf5f  mov     rax, [r10]
0x18001bf62  mov     [rax], r11
0x18001bf65  mov     [r10], rcx
0x18001bf68  mov     [rbx+8], rdx
0x18001bf6c  mov     [r11+8], rax
0x18001bf70  mov     [r9+r8*8], r11
0x18001bf74  mov     r11, rbx
0x18001bf77  jmp     loc_18001BEA2
0x18001bf7c  lea     rcx, [rsp+48h+arg_8]
0x18001bf81  mov     [rsp+48h+arg_8], 0
0x18001bf8a  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18001bf8f  add     rsp, 28h
0x18001bf93  pop     r14
0x18001bf95  pop     rdi
0x18001bf96  pop     rsi
0x18001bf97  pop     rbx
0x18001bf98  retn
```
