# std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Rehash_for_1(void)

- ea: `0x140006ed0`
- end: `0x140007141`
- name: `?_Rehash_for_1@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEAAXXZ`
- size: `625`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400051d0`

## callees

- `0x140004b0c`
- `0x140006ed0`
- `0x1400076f8`
- `0x140014c4b`

## import_xrefs

- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x140006f9d`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x140006f9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Rehash_for_1(
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
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // rcx
  __int64 v14; // rbx
  _QWORD *v15; // rcx
  _QWORD *v16; // rax
  __int64 v17; // r9
  unsigned __int64 i; // r8
  __int64 v19; // rdx
  __int64 v20; // r11
  unsigned __int64 j; // r8
  __int64 v22; // rdx
  __int64 v23; // rbx
  __int64 v24; // r11
  _QWORD *v25; // rdx
  _QWORD *v26; // r10
  _QWORD *v27; // r9
  _QWORD *v28; // r8
  _QWORD *v29; // rdx
  _QWORD *v30; // r9
  _QWORD *v31; // r10
  _QWORD *v32; // r9
  _QWORD *v33; // r8
  __int64 v34; // r10
  _QWORD *v35; // r9
  _QWORD *v36; // r8
  _QWORD *v37; // rdx
  unsigned __int64 *v38; // [rsp+20h] [rbp-38h] BYREF

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
  v12 = *(_QWORD *)(a1 + 8);
  _BitScanReverse64(&v13, (v4 - 1) | 1);
  v14 = 1LL << ((unsigned __int8)v13 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(
    a1 + 24,
    2 * v14,
    v12);
  *(_QWORD *)(a1 + 56) = v14;
  *(_QWORD *)(a1 + 48) = v14 - 1;
  v15 = **(_QWORD ***)(a1 + 8);
  if ( v15 != (_QWORD *)v12 )
  {
    v16 = **(_QWORD ***)(a1 + 8);
    do
    {
      v15 = (_QWORD *)*v15;
      v17 = 0xCBF29CE484222325uLL;
      for ( i = 0; i < 8; ++i )
      {
        v19 = *((unsigned __int8 *)v16 + i + 16);
        v17 = 0x100000001B3LL * (v19 ^ v17);
      }
      v20 = 0xCBF29CE484222325uLL;
      for ( j = 0; j < 8; ++j )
      {
        v22 = *((unsigned __int8 *)v16 + j + 24);
        v20 = 0x100000001B3LL * (v22 ^ v20);
      }
      v23 = *(_QWORD *)(a1 + 24);
      v24 = 2 * (*(_QWORD *)(a1 + 48) & (v17 ^ v20));
      if ( *(_QWORD *)(v23 + 8 * v24) == v12 )
      {
        *(_QWORD *)(v23 + 8 * v24) = v16;
      }
      else
      {
        v25 = *(_QWORD **)(v23 + 8 * v24 + 8);
        if ( v16[2] != v25[2] || v16[3] != v25[3] )
        {
          do
          {
            if ( *(_QWORD **)(v23 + 8 * v24) == v25 )
            {
              v31 = (_QWORD *)v16[1];
              *v31 = v15;
              v32 = (_QWORD *)v15[1];
              *v32 = v25;
              v33 = (_QWORD *)v25[1];
              *v33 = v16;
              v25[1] = v32;
              v15[1] = v31;
              v16[1] = v33;
              *(_QWORD *)(v23 + 8 * v24) = v16;
              goto LABEL_32;
            }
            v30 = (_QWORD *)v25[1];
            v25 = v30;
          }
          while ( v16[2] != v30[2] || v16[3] != v30[3] );
          v34 = *v30;
          v35 = (_QWORD *)v16[1];
          *v35 = v15;
          v36 = (_QWORD *)v15[1];
          *v36 = v34;
          v37 = *(_QWORD **)(v34 + 8);
          *v37 = v16;
          *(_QWORD *)(v34 + 8) = v36;
          v15[1] = v35;
          v16[1] = v37;
          goto LABEL_32;
        }
        v26 = (_QWORD *)*v25;
        if ( (_QWORD *)*v25 != v16 )
        {
          v27 = (_QWORD *)v16[1];
          *v27 = v15;
          v28 = (_QWORD *)v15[1];
          *v28 = v26;
          v29 = (_QWORD *)v26[1];
          *v29 = v16;
          v26[1] = v28;
          v15[1] = v27;
          v16[1] = v29;
        }
      }
      *(_QWORD *)(v23 + 8 * v24 + 8) = v16;
LABEL_32:
      v16 = v15;
    }
    while ( v15 != (_QWORD *)v12 );
  }
  v38 = 0;
  std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Clear_guard::~_Clear_guard(&v38);
}

```

## disassembly

```asm
0x140006ed0  mov     [rsp+arg_8], rbx
0x140006ed5  mov     [rsp+arg_10], rbp
0x140006eda  push    rsi
0x140006edb  push    rdi
0x140006edc  push    r12
0x140006ede  push    r13
0x140006ee0  push    r14
0x140006ee2  sub     rsp, 30h
0x140006ee6  mov     rdx, [rcx+10h]
0x140006eea  mov     ebp, 1
0x140006eef  add     rdx, rbp
0x140006ef2  mov     rbx, [rcx+38h]
0x140006ef6  mov     rdi, rcx
0x140006ef9  xorps   xmm0, xmm0
0x140006efc  js      short loc_140006F05
0x140006efe  cvtsi2ss xmm0, rdx
0x140006f03  jmp     short loc_140006F1A
0x140006f05  mov     rax, rdx
0x140006f08  and     rdx, rbp
0x140006f0b  shr     rax, 1
0x140006f0e  or      rax, rdx
0x140006f11  cvtsi2ss xmm0, rax
0x140006f16  addss   xmm0, xmm0
0x140006f1a  divss   xmm0, dword ptr [rcx]; X
0x140006f1e  call    ceilf_0
0x140006f23  movss   xmm1, cs:__real@5f000000
0x140006f2b  xor     ecx, ecx
0x140006f2d  comiss  xmm0, xmm1
0x140006f30  jb      short loc_140006F48
0x140006f32  subss   xmm0, xmm1
0x140006f36  comiss  xmm0, xmm1
0x140006f39  jnb     short loc_140006F48
0x140006f3b  mov     rax, 8000000000000000h
0x140006f45  mov     rcx, rax
0x140006f48  cvttss2si rax, xmm0
0x140006f4d  add     rax, rcx
0x140006f50  mov     ecx, 8
0x140006f55  cmp     rax, rcx
0x140006f58  cmova   rcx, rax
0x140006f5c  cmp     rbx, rcx
0x140006f5f  jnb     short loc_140006F7D
0x140006f61  cmp     rbx, 200h
0x140006f68  jnb     short loc_140006F7A
0x140006f6a  lea     rax, ds:0[rbx*8]
0x140006f72  mov     rbx, rax
0x140006f75  cmp     rax, rcx
0x140006f78  jnb     short loc_140006F7D
0x140006f7a  mov     rbx, rcx
0x140006f7d  mov     rax, 0FFFFFFFFFFFFFFFh
0x140006f87  bsr     rcx, rax
0x140006f8b  mov     rax, rbp
0x140006f8e  shl     rax, cl
0x140006f91  cmp     rbx, rax
0x140006f94  jbe     short loc_140006FA4
0x140006f96  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x140006f9d  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140006fa4  mov     rsi, [rdi+8]
0x140006fa8  lea     rax, [rbx-1]
0x140006fac  or      rax, rbp
0x140006faf  mov     rbx, rbp
0x140006fb2  bsr     rcx, rax
0x140006fb6  mov     r8, rsi
0x140006fb9  inc     ecx
0x140006fbb  shl     rbx, cl
0x140006fbe  lea     rcx, [rdi+18h]
0x140006fc2  lea     rdx, [rbx+rbx]
0x140006fc6  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>)
0x140006fcb  mov     [rdi+38h], rbx
0x140006fcf  lea     rax, [rbx-1]
0x140006fd3  mov     [rdi+30h], rax
0x140006fd7  mov     rcx, [rdi+8]
0x140006fdb  mov     rcx, [rcx]
0x140006fde  cmp     rcx, rsi
0x140006fe1  jz      loc_1400070F1
0x140006fe7  mov     rax, rcx
0x140006fea  mov     r12, 0CBF29CE484222325h
0x140006ff4  mov     r13, 100000001B3h
0x140006ffe  mov     rcx, [rcx]
0x140007001  mov     r9, r12
0x140007004  xor     r8d, r8d
0x140007007  movzx   edx, byte ptr [rax+r8+10h]
0x14000700d  add     r8, rbp
0x140007010  xor     r9, rdx
0x140007013  imul    r9, r13
0x140007017  cmp     r8, 8
0x14000701b  jb      short loc_140007007
0x14000701d  mov     r11, r12
0x140007020  xor     r8d, r8d
0x140007023  movzx   edx, byte ptr [r8+rax+18h]
0x140007029  add     r8, rbp
0x14000702c  xor     r11, rdx
0x14000702f  imul    r11, r13
0x140007033  cmp     r8, 8
0x140007037  jb      short loc_140007023
0x140007039  mov     rbx, [rdi+18h]
0x14000703d  xor     r11, r9
0x140007040  and     r11, [rdi+30h]
0x140007044  add     r11, r11
0x140007047  cmp     [rbx+r11*8], rsi
0x14000704b  jnz     short loc_14000705B
0x14000704d  mov     [rbx+r11*8], rax
0x140007051  mov     [rbx+r11*8+8], rax
0x140007056  jmp     loc_1400070E5
0x14000705b  mov     rdx, [rbx+r11*8+8]
0x140007060  mov     r8, [rax+10h]
0x140007064  cmp     r8, [rdx+10h]
0x140007068  jnz     short loc_1400070BA
0x14000706a  mov     r8, [rax+18h]
0x14000706e  cmp     r8, [rdx+18h]
0x140007072  jnz     short loc_1400070BA
0x140007074  mov     r10, [rdx]
0x140007077  cmp     r10, rax
0x14000707a  jz      short loc_140007051
0x14000707c  mov     r9, [rax+8]
0x140007080  mov     [r9], rcx
0x140007083  mov     r8, [rcx+8]
0x140007087  mov     [r8], r10
0x14000708a  mov     rdx, [r10+8]
0x14000708e  mov     [rdx], rax
0x140007091  mov     [r10+8], r8
0x140007095  mov     [rcx+8], r9
0x140007099  mov     [rax+8], rdx
0x14000709d  jmp     short loc_140007051
0x14000709f  mov     r9, [rdx+8]
0x1400070a3  mov     r8, [rax+10h]
0x1400070a7  mov     rdx, r9
0x1400070aa  cmp     r8, [r9+10h]
0x1400070ae  jnz     short loc_1400070BA
0x1400070b0  mov     r8, [rax+18h]
0x1400070b4  cmp     r8, [r9+18h]
0x1400070b8  jz      short loc_14000711B
0x1400070ba  cmp     [rbx+r11*8], rdx
0x1400070be  jnz     short loc_14000709F
0x1400070c0  mov     r10, [rax+8]
0x1400070c4  mov     [r10], rcx
0x1400070c7  mov     r9, [rcx+8]
0x1400070cb  mov     [r9], rdx
0x1400070ce  mov     r8, [rdx+8]
0x1400070d2  mov     [r8], rax
0x1400070d5  mov     [rdx+8], r9
0x1400070d9  mov     [rcx+8], r10
0x1400070dd  mov     [rax+8], r8
0x1400070e1  mov     [rbx+r11*8], rax
0x1400070e5  mov     rax, rcx
0x1400070e8  cmp     rcx, rsi
0x1400070eb  jnz     loc_140006FFE
0x1400070f1  lea     rcx, [rsp+58h+var_38]
0x1400070f6  mov     [rsp+58h+var_38], 0
0x1400070ff  call    ??1_Clear_guard@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Clear_guard::~_Clear_guard(void)
0x140007104  mov     rbx, [rsp+58h+arg_8]
0x140007109  mov     rbp, [rsp+58h+arg_10]
0x14000710e  add     rsp, 30h
0x140007112  pop     r14
0x140007114  pop     r13
0x140007116  pop     r12
0x140007118  pop     rdi
0x140007119  pop     rsi
0x14000711a  retn
0x14000711b  mov     r10, [r9]
0x14000711e  mov     r9, [rax+8]
0x140007122  mov     [r9], rcx
0x140007125  mov     r8, [rcx+8]
0x140007129  mov     [r8], r10
0x14000712c  mov     rdx, [r10+8]
0x140007130  mov     [rdx], rax
0x140007133  mov     [r10+8], r8
0x140007137  mov     [rcx+8], r9
0x14000713b  mov     [rax+8], rdx
0x14000713f  jmp     short loc_1400070E5
```
