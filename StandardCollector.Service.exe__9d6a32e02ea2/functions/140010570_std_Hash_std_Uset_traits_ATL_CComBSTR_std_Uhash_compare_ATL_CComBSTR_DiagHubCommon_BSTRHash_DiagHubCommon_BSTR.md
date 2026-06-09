# std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::_Rehash_for_1(void)

- ea: `0x140010570`
- end: `0x1400107e2`
- name: `?_Rehash_for_1@?$_Hash@V?$_Uset_traits@VCComBSTR@ATL@@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@VCComBSTR@ATL@@@4@$0A@@std@@@std@@IEAAXXZ`
- size: `626`
- prototype: `void()`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140010260`

## callees

- `0x140004b0c`
- `0x140006d10`
- `0x140010570`
- `0x140010800`
- `0x140014c4b`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1400106f9`
- `KERNEL32!CompareStringOrdinal` at `0x140010747`
- `KERNEL32!CompareStringOrdinal` at `0x1400106f9`
- `KERNEL32!CompareStringOrdinal` at `0x140010747`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x14001064b`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x14001064b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::_Rehash_for_1()
{
  int v0; // ecx
  float v1; // xmm0_4
  float v2; // xmm0_4
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rcx
  __int64 v8; // r12
  unsigned __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 **v11; // rcx
  _QWORD *v12; // rdi
  _QWORD *v13; // rbx
  LPCWCH *v14; // r15
  __int64 v15; // rax
  __int64 v16; // rbp
  __int64 v17; // r14
  __int64 *v18; // rsi
  __int64 *v19; // r8
  _QWORD *v20; // rdx
  _QWORD *v21; // rax
  _QWORD *v22; // rdx
  _QWORD *v23; // rax
  __int64 *v24; // r8
  _QWORD *v25; // rdx
  _QWORD *v26; // rax
  unsigned __int64 *v27; // [rsp+30h] [rbp-38h] BYREF

  v0 = qword_140024AA0 + 1;
  if ( qword_140024AA0 + 1 < 0 )
    v1 = (float)(int)(v0 & 1 | ((unsigned __int64)(qword_140024AA0 + 1) >> 1))
       + (float)(int)(v0 & 1 | ((unsigned __int64)(qword_140024AA0 + 1) >> 1));
  else
    v1 = (float)v0;
  v2 = ceilf_0(v1 / *((float *)&qword_140024A90 + 1));
  v3 = 0;
  if ( v2 >= 9.223372e18 )
  {
    v2 = v2 - 9.223372e18;
    if ( v2 < 9.223372e18 )
      v3 = 0x8000000000000000uLL;
  }
  v4 = qword_140024AC8;
  v5 = v3 + (unsigned int)(int)v2;
  v6 = 8;
  if ( v5 > 8 )
    v6 = v5;
  if ( qword_140024AC8 < v6 )
  {
    if ( (unsigned __int64)qword_140024AC8 >= 0x200 || (v4 = 8 * qword_140024AC8, 8 * qword_140024AC8 < v6) )
      v4 = v6;
  }
  _BitScanReverse64(&v7, 0xFFFFFFFFFFFFFFFuLL);
  if ( v4 > 1LL << v7 )
    std::_Xlength_error("invalid hash bucket count");
  v8 = qword_140024A98;
  _BitScanReverse64(&v9, (v4 - 1) | 1);
  v10 = 1LL << ((unsigned __int8)v9 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(
    (__int64)&qword_140024AA8,
    2 * v10,
    qword_140024A98);
  qword_140024AC0 = v10 - 1;
  qword_140024AC8 = v10;
  v12 = *(_QWORD **)qword_140024A98;
  if ( *(_QWORD *)qword_140024A98 != v8 )
  {
    v13 = *(_QWORD **)qword_140024A98;
    do
    {
      v12 = (_QWORD *)*v12;
      v14 = (LPCWCH *)(v13 + 2);
      v15 = std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>::operator()<ATL::CComBSTR>(
              (__int64)v11,
              (BSTR *)v13 + 2);
      v16 = qword_140024AA8;
      v17 = 2 * (qword_140024AC0 & v15);
      if ( *(_QWORD *)(qword_140024AA8 + 16 * (qword_140024AC0 & v15)) == v8 )
      {
        *(_QWORD *)(qword_140024AA8 + 16 * (qword_140024AC0 & v15)) = v13;
      }
      else
      {
        v18 = *(__int64 **)(qword_140024AA8 + 16 * (qword_140024AC0 & v15) + 8);
        if ( CompareStringOrdinal(*v14, -1, (LPCWCH)v18[2], -1, 1) != 2 )
        {
          do
          {
            if ( *(__int64 **)(v16 + 8 * v17) == v18 )
            {
              v22 = (_QWORD *)v13[1];
              *v22 = v12;
              v11 = (__int64 **)v12[1];
              *v11 = v18;
              v23 = (_QWORD *)v18[1];
              *v23 = v13;
              v18[1] = (__int64)v11;
              v12[1] = v22;
              v13[1] = v23;
              *(_QWORD *)(v16 + 8 * v17) = v13;
              goto LABEL_26;
            }
            v18 = (__int64 *)v18[1];
          }
          while ( CompareStringOrdinal(*v14, -1, (LPCWCH)v18[2], -1, 1) != 2 );
          v24 = (__int64 *)*v18;
          v25 = (_QWORD *)v13[1];
          *v25 = v12;
          v11 = (__int64 **)v12[1];
          *v11 = v24;
          v26 = (_QWORD *)v24[1];
          *v26 = v13;
          v24[1] = (__int64)v11;
          v12[1] = v25;
          v13[1] = v26;
          goto LABEL_26;
        }
        v19 = (__int64 *)*v18;
        if ( (_QWORD *)*v18 != v13 )
        {
          v20 = (_QWORD *)v13[1];
          *v20 = v12;
          v11 = (__int64 **)v12[1];
          *v11 = v19;
          v21 = (_QWORD *)v19[1];
          *v21 = v13;
          v19[1] = (__int64)v11;
          v12[1] = v20;
          v13[1] = v21;
        }
      }
      *(_QWORD *)(v16 + 8 * v17 + 8) = v13;
LABEL_26:
      v13 = v12;
    }
    while ( v12 != (_QWORD *)v8 );
  }
  v27 = 0;
  std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::_Clear_guard::~_Clear_guard(&v27);
}

```

## disassembly

```asm
0x140010570  mov     [rsp+arg_0], rbx
0x140010575  mov     [rsp+arg_8], rbp
0x14001057a  mov     [rsp+arg_10], rsi
0x14001057f  push    rdi
0x140010580  push    r12
0x140010582  push    r13
0x140010584  push    r14
0x140010586  push    r15
0x140010588  sub     rsp, 40h
0x14001058c  mov     rcx, cs:qword_140024AA0
0x140010593  mov     r13d, 1
0x140010599  add     rcx, r13
0x14001059c  xorps   xmm0, xmm0
0x14001059f  js      short loc_1400105A8
0x1400105a1  cvtsi2ss xmm0, rcx
0x1400105a6  jmp     short loc_1400105BD
0x1400105a8  mov     rax, rcx
0x1400105ab  and     rcx, r13
0x1400105ae  shr     rax, 1
0x1400105b1  or      rax, rcx
0x1400105b4  cvtsi2ss xmm0, rax
0x1400105b9  addss   xmm0, xmm0
0x1400105bd  divss   xmm0, dword ptr cs:qword_140024A90+4; X
0x1400105c5  call    ceilf_0
0x1400105ca  movss   xmm1, cs:__real@5f000000
0x1400105d2  xor     ecx, ecx
0x1400105d4  comiss  xmm0, xmm1
0x1400105d7  jb      short loc_1400105EF
0x1400105d9  subss   xmm0, xmm1
0x1400105dd  comiss  xmm0, xmm1
0x1400105e0  jnb     short loc_1400105EF
0x1400105e2  mov     rax, 8000000000000000h
0x1400105ec  mov     rcx, rax
0x1400105ef  mov     rdx, cs:qword_140024AC8
0x1400105f6  cvttss2si rax, xmm0
0x1400105fb  add     rax, rcx
0x1400105fe  mov     ecx, 8
0x140010603  cmp     rax, rcx
0x140010606  cmova   rcx, rax
0x14001060a  cmp     rdx, rcx
0x14001060d  jnb     short loc_14001062B
0x14001060f  cmp     rdx, 200h
0x140010616  jnb     short loc_140010628
0x140010618  lea     rax, ds:0[rdx*8]
0x140010620  mov     rdx, rax
0x140010623  cmp     rax, rcx
0x140010626  jnb     short loc_14001062B
0x140010628  mov     rdx, rcx
0x14001062b  mov     rax, 0FFFFFFFFFFFFFFFh
0x140010635  bsr     rcx, rax
0x140010639  mov     rax, r13
0x14001063c  shl     rax, cl
0x14001063f  cmp     rdx, rax
0x140010642  jbe     short loc_140010652
0x140010644  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x14001064b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140010652  mov     r12, cs:qword_140024A98
0x140010659  lea     rax, [rdx-1]
0x14001065d  or      rax, r13
0x140010660  mov     rbx, r13
0x140010663  bsr     rcx, rax
0x140010667  mov     r8, r12
0x14001066a  inc     ecx
0x14001066c  shl     rbx, cl
0x14001066f  lea     rcx, qword_140024AA8
0x140010676  lea     rdx, [rbx+rbx]
0x14001067a  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>)
0x14001067f  mov     rdi, cs:qword_140024A98
0x140010686  lea     rax, [rbx-1]
0x14001068a  mov     cs:qword_140024AC0, rax
0x140010691  mov     cs:qword_140024AC8, rbx
0x140010698  mov     rdi, [rdi]
0x14001069b  cmp     rdi, r12
0x14001069e  jz      loc_14001078B
0x1400106a4  mov     rbx, rdi
0x1400106a7  mov     rdi, [rdi]
0x1400106aa  lea     r15, [rbx+10h]
0x1400106ae  mov     rdx, r15
0x1400106b1  call    ??$?RVCComBSTR@ATL@@@?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@QEBA_KAEBVCComBSTR@ATL@@@Z; std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>::operator()<ATL::CComBSTR>(ATL::CComBSTR const &)
0x1400106b6  mov     rbp, cs:qword_140024AA8
0x1400106bd  mov     r14, rax
0x1400106c0  and     r14, cs:qword_140024AC0
0x1400106c7  add     r14, r14
0x1400106ca  cmp     [rbp+r14*8+0], r12
0x1400106cf  jnz     short loc_1400106E0
0x1400106d1  mov     [rbp+r14*8+0], rbx
0x1400106d6  mov     [rbp+r14*8+8], rbx
0x1400106db  jmp     loc_14001077F
0x1400106e0  mov     rsi, [rbp+r14*8+8]
0x1400106e5  or      eax, 0FFFFFFFFh
0x1400106e8  mov     rcx, [r15]; lpString1
0x1400106eb  mov     r9d, eax; cchCount2
0x1400106ee  mov     edx, eax; cchCount1
0x1400106f0  mov     [rsp+68h+bIgnoreCase], r13d; bIgnoreCase
0x1400106f5  mov     r8, [rsi+10h]; lpString2
0x1400106f9  call    cs:__imp_CompareStringOrdinal
0x1400106ff  cmp     eax, 2
0x140010702  jnz     short loc_140010752
0x140010704  mov     r8, [rsi]
0x140010707  cmp     r8, rbx
0x14001070a  jz      short loc_1400106D6
0x14001070c  mov     rdx, [rbx+8]
0x140010710  mov     [rdx], rdi
0x140010713  mov     rcx, [rdi+8]
0x140010717  mov     [rcx], r8
0x14001071a  mov     rax, [r8+8]
0x14001071e  mov     [rax], rbx
0x140010721  mov     [r8+8], rcx
0x140010725  mov     [rdi+8], rdx
0x140010729  mov     [rbx+8], rax
0x14001072d  jmp     short loc_1400106D6
0x14001072f  mov     rsi, [rsi+8]
0x140010733  or      eax, 0FFFFFFFFh
0x140010736  mov     rcx, [r15]; lpString1
0x140010739  mov     r9d, eax; cchCount2
0x14001073c  mov     edx, eax; cchCount1
0x14001073e  mov     [rsp+68h+bIgnoreCase], r13d; bIgnoreCase
0x140010743  mov     r8, [rsi+10h]; lpString2
0x140010747  call    cs:__imp_CompareStringOrdinal
0x14001074d  cmp     eax, 2
0x140010750  jz      short loc_1400107BC
0x140010752  cmp     [rbp+r14*8+0], rsi
0x140010757  jnz     short loc_14001072F
0x140010759  mov     rdx, [rbx+8]
0x14001075d  mov     [rdx], rdi
0x140010760  mov     rcx, [rdi+8]
0x140010764  mov     [rcx], rsi
0x140010767  mov     rax, [rsi+8]
0x14001076b  mov     [rax], rbx
0x14001076e  mov     [rsi+8], rcx
0x140010772  mov     [rdi+8], rdx
0x140010776  mov     [rbx+8], rax
0x14001077a  mov     [rbp+r14*8+0], rbx
0x14001077f  mov     rbx, rdi
0x140010782  cmp     rdi, r12
0x140010785  jnz     loc_1400106A7
0x14001078b  lea     rcx, [rsp+68h+var_38]
0x140010790  mov     [rsp+68h+var_38], 0
0x140010799  call    ??1_Clear_guard@?$_Hash@V?$_Uset_traits@VCComBSTR@ATL@@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@VCComBSTR@ATL@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::_Clear_guard::~_Clear_guard(void)
0x14001079e  lea     r11, [rsp+68h+var_28]
0x1400107a3  mov     rbx, [r11+30h]
0x1400107a7  mov     rbp, [r11+38h]
0x1400107ab  mov     rsi, [r11+40h]
0x1400107af  mov     rsp, r11
0x1400107b2  pop     r15
0x1400107b4  pop     r14
0x1400107b6  pop     r13
0x1400107b8  pop     r12
0x1400107ba  pop     rdi
0x1400107bb  retn
0x1400107bc  mov     r8, [rsi]
0x1400107bf  mov     rdx, [rbx+8]
0x1400107c3  mov     [rdx], rdi
0x1400107c6  mov     rcx, [rdi+8]
0x1400107ca  mov     [rcx], r8
0x1400107cd  mov     rax, [r8+8]
0x1400107d1  mov     [rax], rbx
0x1400107d4  mov     [r8+8], rcx
0x1400107d8  mov     [rdi+8], rdx
0x1400107dc  mov     [rbx+8], rax
0x1400107e0  jmp     short loc_14001077F
```
