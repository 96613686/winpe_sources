# std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::_Rehash_for_1(void)

- ea: `0x140007484`
- end: `0x1400076f5`
- name: `?_Rehash_for_1@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@IEAAXXZ`
- size: `625`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400067a8`

## callees

- `0x140004b0c`
- `0x140007484`
- `0x140007854`
- `0x140014c4b`

## import_xrefs

- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x140007551`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x140007551`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::_Rehash_for_1(
        __int64 a1)
{
  __int64 v1; // rdx
  bool v2; // sf
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // rbx
  float v6; // xmm0_4
  float v7; // xmm0_4
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rax
  _QWORD *v13; // rbx
  unsigned __int64 v14; // rcx
  __int64 v15; // rdi
  _QWORD *v16; // rax
  _QWORD *i; // rdx
  __int64 v18; // r9
  unsigned __int64 j; // r8
  __int64 v20; // rcx
  __int64 v21; // r11
  unsigned __int64 k; // r8
  __int64 v23; // rcx
  __int64 v24; // rdi
  __int64 v25; // r11
  _QWORD *v26; // rcx
  _QWORD *v27; // r10
  _QWORD *v28; // r9
  _QWORD *v29; // r8
  _QWORD *v30; // rcx
  _QWORD *v31; // r9
  _QWORD *v32; // r10
  _QWORD *v33; // r9
  _QWORD *v34; // r8
  __int64 v36; // r10
  _QWORD *v37; // r9
  _QWORD *v38; // r8
  _QWORD *v39; // rcx
  _QWORD v40[7]; // [rsp+20h] [rbp-38h] BYREF

  v1 = *(_QWORD *)(a1 + 16);
  v2 = v1 + 1 < 0;
  v3 = v1 + 1;
  v4 = *(_QWORD *)(a1 + 56);
  if ( v2 )
    v6 = (float)(int)(v3 & 1 | (v3 >> 1)) + (float)(int)(v3 & 1 | (v3 >> 1));
  else
    v6 = (float)(int)v3;
  v7 = ceilf_0(v6 / *(float *)a1);
  v8 = 0;
  if ( v7 >= 9.223372e18 )
  {
    v7 = v7 - 9.223372e18;
    if ( v7 < 9.223372e18 )
      v8 = 0x8000000000000000uLL;
  }
  v9 = v8 + (unsigned int)(int)v7;
  v10 = 8;
  if ( v9 > 8 )
    v10 = v9;
  if ( v4 < v10 )
  {
    if ( v4 >= 0x200 || (v4 *= 8LL, v4 < v10) )
      v4 = v10;
  }
  _BitScanReverse64(&v11, 0xFFFFFFFFFFFFFFFuLL);
  if ( v4 > 1LL << v11 )
    std::_Xlength_error("invalid hash bucket count");
  v12 = v4 - 1;
  v13 = *(_QWORD **)(a1 + 8);
  _BitScanReverse64(&v14, v12 | 1);
  v15 = 1LL << ((unsigned __int8)v14 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(
    a1 + 24,
    2 * v15,
    v13);
  *(_QWORD *)(a1 + 56) = v15;
  *(_QWORD *)(a1 + 48) = v15 - 1;
  v16 = **(_QWORD ***)(a1 + 8);
  for ( i = v16; i != v13; v16 = i )
  {
    i = (_QWORD *)*i;
    v18 = 0xCBF29CE484222325uLL;
    for ( j = 0; j < 8; ++j )
    {
      v20 = *((unsigned __int8 *)v16 + j + 16);
      v18 = 0x100000001B3LL * (v20 ^ v18);
    }
    v21 = 0xCBF29CE484222325uLL;
    for ( k = 0; k < 8; ++k )
    {
      v23 = *((unsigned __int8 *)v16 + k + 24);
      v21 = 0x100000001B3LL * (v23 ^ v21);
    }
    v24 = *(_QWORD *)(a1 + 24);
    v25 = 2 * (*(_QWORD *)(a1 + 48) & (v18 ^ v21));
    if ( *(_QWORD **)(v24 + 8 * v25) == v13 )
    {
      *(_QWORD *)(v24 + 8 * v25) = v16;
    }
    else
    {
      v26 = *(_QWORD **)(v24 + 8 * v25 + 8);
      if ( v16[2] != v26[2] || v16[3] != v26[3] )
      {
        do
        {
          if ( *(_QWORD **)(v24 + 8 * v25) == v26 )
          {
            v32 = (_QWORD *)v16[1];
            *v32 = i;
            v33 = (_QWORD *)i[1];
            *v33 = v26;
            v34 = (_QWORD *)v26[1];
            *v34 = v16;
            v26[1] = v33;
            i[1] = v32;
            v16[1] = v34;
            *(_QWORD *)(v24 + 8 * v25) = v16;
            goto LABEL_31;
          }
          v31 = (_QWORD *)v26[1];
          v26 = v31;
        }
        while ( v16[2] != v31[2] || v16[3] != v31[3] );
        v36 = *v31;
        v37 = (_QWORD *)v16[1];
        *v37 = i;
        v38 = (_QWORD *)i[1];
        *v38 = v36;
        v39 = *(_QWORD **)(v36 + 8);
        *v39 = v16;
        *(_QWORD *)(v36 + 8) = v38;
        i[1] = v37;
        v16[1] = v39;
        continue;
      }
      v27 = (_QWORD *)*v26;
      if ( (_QWORD *)*v26 != v16 )
      {
        v28 = (_QWORD *)v16[1];
        *v28 = i;
        v29 = (_QWORD *)i[1];
        *v29 = v27;
        v30 = (_QWORD *)v27[1];
        *v30 = v16;
        v27[1] = v29;
        i[1] = v28;
        v16[1] = v30;
      }
    }
    *(_QWORD *)(v24 + 8 * v25 + 8) = v16;
LABEL_31:
    ;
  }
  v40[0] = 0;
  return std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::_Clear_guard::~_Clear_guard(
           v40,
           i);
}

```

## disassembly

```asm
0x140007484  mov     [rsp+arg_8], rbx
0x140007489  mov     [rsp+arg_10], rbp
0x14000748e  push    rsi
0x14000748f  push    rdi
0x140007490  push    r12
0x140007492  push    r13
0x140007494  push    r14
0x140007496  sub     rsp, 30h
0x14000749a  mov     rdx, [rcx+10h]
0x14000749e  mov     ebp, 1
0x1400074a3  add     rdx, rbp
0x1400074a6  mov     rbx, [rcx+38h]
0x1400074aa  mov     rsi, rcx
0x1400074ad  xorps   xmm0, xmm0
0x1400074b0  js      short loc_1400074B9
0x1400074b2  cvtsi2ss xmm0, rdx
0x1400074b7  jmp     short loc_1400074CE
0x1400074b9  mov     rax, rdx
0x1400074bc  and     rdx, rbp
0x1400074bf  shr     rax, 1
0x1400074c2  or      rax, rdx
0x1400074c5  cvtsi2ss xmm0, rax
0x1400074ca  addss   xmm0, xmm0
0x1400074ce  divss   xmm0, dword ptr [rcx]; X
0x1400074d2  call    ceilf_0
0x1400074d7  movss   xmm1, cs:__real@5f000000
0x1400074df  xor     ecx, ecx
0x1400074e1  comiss  xmm0, xmm1
0x1400074e4  jb      short loc_1400074FC
0x1400074e6  subss   xmm0, xmm1
0x1400074ea  comiss  xmm0, xmm1
0x1400074ed  jnb     short loc_1400074FC
0x1400074ef  mov     rax, 8000000000000000h
0x1400074f9  mov     rcx, rax
0x1400074fc  cvttss2si rax, xmm0
0x140007501  add     rax, rcx
0x140007504  mov     ecx, 8
0x140007509  cmp     rax, rcx
0x14000750c  cmova   rcx, rax
0x140007510  cmp     rbx, rcx
0x140007513  jnb     short loc_140007531
0x140007515  cmp     rbx, 200h
0x14000751c  jnb     short loc_14000752E
0x14000751e  lea     rax, ds:0[rbx*8]
0x140007526  mov     rbx, rax
0x140007529  cmp     rax, rcx
0x14000752c  jnb     short loc_140007531
0x14000752e  mov     rbx, rcx
0x140007531  mov     rax, 0FFFFFFFFFFFFFFFh
0x14000753b  bsr     rcx, rax
0x14000753f  mov     rax, rbp
0x140007542  shl     rax, cl
0x140007545  cmp     rbx, rax
0x140007548  jbe     short loc_140007558
0x14000754a  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x140007551  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140007558  lea     rax, [rbx-1]
0x14000755c  mov     rdi, rbp
0x14000755f  mov     rbx, [rsi+8]
0x140007563  or      rax, rbp
0x140007566  bsr     rcx, rax
0x14000756a  mov     r8, rbx
0x14000756d  inc     ecx
0x14000756f  shl     rdi, cl
0x140007572  lea     rcx, [rsi+18h]
0x140007576  lea     rdx, [rdi+rdi]
0x14000757a  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>)
0x14000757f  lea     rax, [rdi-1]
0x140007583  mov     [rsi+38h], rdi
0x140007587  mov     [rsi+30h], rax
0x14000758b  mov     rax, [rsi+8]
0x14000758f  mov     rax, [rax]
0x140007592  mov     rdx, rax
0x140007595  cmp     rax, rbx
0x140007598  jz      loc_1400076A5
0x14000759e  mov     r12, 0CBF29CE484222325h
0x1400075a8  mov     r13, 100000001B3h
0x1400075b2  mov     rdx, [rdx]
0x1400075b5  mov     r9, r12
0x1400075b8  xor     r8d, r8d
0x1400075bb  movzx   ecx, byte ptr [rax+r8+10h]
0x1400075c1  add     r8, rbp
0x1400075c4  xor     r9, rcx
0x1400075c7  imul    r9, r13
0x1400075cb  cmp     r8, 8
0x1400075cf  jb      short loc_1400075BB
0x1400075d1  mov     r11, r12
0x1400075d4  xor     r8d, r8d
0x1400075d7  movzx   ecx, byte ptr [rax+r8+18h]
0x1400075dd  add     r8, rbp
0x1400075e0  xor     r11, rcx
0x1400075e3  imul    r11, r13
0x1400075e7  cmp     r8, 8
0x1400075eb  jb      short loc_1400075D7
0x1400075ed  mov     rdi, [rsi+18h]
0x1400075f1  xor     r11, r9
0x1400075f4  and     r11, [rsi+30h]
0x1400075f8  add     r11, r11
0x1400075fb  cmp     [rdi+r11*8], rbx
0x1400075ff  jnz     short loc_14000760F
0x140007601  mov     [rdi+r11*8], rax
0x140007605  mov     [rdi+r11*8+8], rax
0x14000760a  jmp     loc_140007699
0x14000760f  mov     rcx, [rdi+r11*8+8]
0x140007614  mov     r8, [rax+10h]
0x140007618  cmp     r8, [rcx+10h]
0x14000761c  jnz     short loc_14000766E
0x14000761e  mov     r8, [rax+18h]
0x140007622  cmp     r8, [rcx+18h]
0x140007626  jnz     short loc_14000766E
0x140007628  mov     r10, [rcx]
0x14000762b  cmp     r10, rax
0x14000762e  jz      short loc_140007605
0x140007630  mov     r9, [rax+8]
0x140007634  mov     [r9], rdx
0x140007637  mov     r8, [rdx+8]
0x14000763b  mov     [r8], r10
0x14000763e  mov     rcx, [r10+8]
0x140007642  mov     [rcx], rax
0x140007645  mov     [r10+8], r8
0x140007649  mov     [rdx+8], r9
0x14000764d  mov     [rax+8], rcx
0x140007651  jmp     short loc_140007605
0x140007653  mov     r9, [rcx+8]
0x140007657  mov     r8, [rax+10h]
0x14000765b  mov     rcx, r9
0x14000765e  cmp     r8, [r9+10h]
0x140007662  jnz     short loc_14000766E
0x140007664  mov     r8, [rax+18h]
0x140007668  cmp     r8, [r9+18h]
0x14000766c  jz      short loc_1400076CF
0x14000766e  cmp     [rdi+r11*8], rcx
0x140007672  jnz     short loc_140007653
0x140007674  mov     r10, [rax+8]
0x140007678  mov     [r10], rdx
0x14000767b  mov     r9, [rdx+8]
0x14000767f  mov     [r9], rcx
0x140007682  mov     r8, [rcx+8]
0x140007686  mov     [r8], rax
0x140007689  mov     [rcx+8], r9
0x14000768d  mov     [rdx+8], r10
0x140007691  mov     [rax+8], r8
0x140007695  mov     [rdi+r11*8], rax
0x140007699  mov     rax, rdx
0x14000769c  cmp     rdx, rbx
0x14000769f  jnz     loc_1400075B2
0x1400076a5  lea     rcx, [rsp+58h+var_38]
0x1400076aa  mov     [rsp+58h+var_38], 0
0x1400076b3  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::_Clear_guard::~_Clear_guard(void)
0x1400076b8  mov     rbx, [rsp+58h+arg_8]
0x1400076bd  mov     rbp, [rsp+58h+arg_10]
0x1400076c2  add     rsp, 30h
0x1400076c6  pop     r14
0x1400076c8  pop     r13
0x1400076ca  pop     r12
0x1400076cc  pop     rdi
0x1400076cd  pop     rsi
0x1400076ce  retn
0x1400076cf  mov     r10, [r9]
0x1400076d2  mov     r9, [rax+8]
0x1400076d6  mov     [r9], rdx
0x1400076d9  mov     r8, [rdx+8]
0x1400076dd  mov     [r8], r10
0x1400076e0  mov     rcx, [r10+8]
0x1400076e4  mov     [rcx], rax
0x1400076e7  mov     [r10+8], r8
0x1400076eb  mov     [rdx+8], r9
0x1400076ef  mov     [rax+8], rcx
0x1400076f3  jmp     short loc_140007699
```
