# std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::_Rehash_for_1(void)

- ea: `0x140007144`
- end: `0x1400073a9`
- name: `?_Rehash_for_1@?$_Hash@V?$_Umap_traits@VCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@@5@$0A@@std@@@std@@IEAAXXZ`
- size: `613`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000697c`

## callees

- `0x140004b0c`
- `0x140006d10`
- `0x140007144`
- `0x14000778c`
- `0x140014c4b`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1400072b5`
- `KERNEL32!CompareStringOrdinal` at `0x14000730c`
- `KERNEL32!CompareStringOrdinal` at `0x1400072b5`
- `KERNEL32!CompareStringOrdinal` at `0x14000730c`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x140007218`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x140007218`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::_Rehash_for_1(
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
  unsigned __int64 v12; // rbp
  __int64 *v13; // rsi
  unsigned __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 **v16; // rcx
  _QWORD *v17; // rbx
  _QWORD *i; // rdi
  LPCWCH *v19; // r12
  __int64 v20; // rax
  __int64 v21; // r15
  __int64 v22; // r14
  __int64 *v23; // rsi
  __int64 *v24; // r8
  _QWORD *v25; // rdx
  _QWORD *v26; // rax
  _QWORD *v27; // rdx
  _QWORD *v28; // rax
  __int64 *v29; // r8
  _QWORD *v30; // rdx
  _QWORD *v31; // rax
  unsigned __int64 *v32; // [rsp+30h] [rbp-38h] BYREF

  v1 = *(_QWORD *)(a1 + 16);
  v2 = v1 + 1 < 0;
  v3 = v1 + 1;
  v4 = *(_QWORD *)(a1 + 56);
  if ( v2 )
    v6 = (float)(int)(v3 & 1 | (v3 >> 1)) + (float)(int)(v3 & 1 | (v3 >> 1));
  else
    v6 = (float)(int)v3;
  v7 = ceilf_0(v6 / *(float *)(a1 + 4));
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
  v13 = (__int64 *)(a1 + 24);
  _BitScanReverse64(&v14, (v4 - 1) | 1);
  v15 = 1LL << ((unsigned __int8)v14 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(
    a1 + 24,
    2 * v15,
    v12);
  *(_QWORD *)(a1 + 56) = v15;
  *(_QWORD *)(a1 + 48) = v15 - 1;
  v17 = **(_QWORD ***)(a1 + 8);
  for ( i = v17; i != (_QWORD *)v12; v17 = i )
  {
    i = (_QWORD *)*i;
    v19 = (LPCWCH *)(v17 + 2);
    v20 = std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>::operator()<ATL::CComBSTR>(
            (__int64)v16,
            (BSTR *)v17 + 2);
    v21 = *v13;
    v22 = 2 * (*(_QWORD *)(a1 + 48) & v20);
    if ( *(_QWORD *)(*v13 + 16 * (*(_QWORD *)(a1 + 48) & v20)) == v12 )
    {
      *(_QWORD *)(v21 + 16 * (*(_QWORD *)(a1 + 48) & v20)) = v17;
      *(_QWORD *)(v21 + 8 * v22 + 8) = v17;
    }
    else
    {
      v23 = *(__int64 **)(v21 + 16 * (*(_QWORD *)(a1 + 48) & v20) + 8);
      if ( CompareStringOrdinal(*v19, -1, (LPCWCH)v23[2], -1, 1) == 2 )
      {
        v24 = (__int64 *)*v23;
        if ( (_QWORD *)*v23 != v17 )
        {
          v25 = (_QWORD *)v17[1];
          *v25 = i;
          v16 = (__int64 **)i[1];
          *v16 = v24;
          v26 = (_QWORD *)v24[1];
          *v26 = v17;
          v24[1] = (__int64)v16;
          i[1] = v25;
          v17[1] = v26;
        }
        *(_QWORD *)(v21 + 8 * v22 + 8) = v17;
      }
      else
      {
        do
        {
          if ( *(__int64 **)(v21 + 8 * v22) == v23 )
          {
            v27 = (_QWORD *)v17[1];
            *v27 = i;
            v16 = (__int64 **)i[1];
            *v16 = v23;
            v28 = (_QWORD *)v23[1];
            *v28 = v17;
            v23[1] = (__int64)v16;
            i[1] = v27;
            v17[1] = v28;
            *(_QWORD *)(v21 + 8 * v22) = v17;
            goto LABEL_25;
          }
          v23 = (__int64 *)v23[1];
        }
        while ( CompareStringOrdinal(*v19, -1, (LPCWCH)v23[2], -1, 1) != 2 );
        v29 = (__int64 *)*v23;
        v30 = (_QWORD *)v17[1];
        *v30 = i;
        v16 = (__int64 **)i[1];
        *v16 = v29;
        v31 = (_QWORD *)v29[1];
        *v31 = v17;
        v29[1] = (__int64)v16;
        i[1] = v30;
        v17[1] = v31;
      }
LABEL_25:
      v13 = (__int64 *)(a1 + 24);
    }
  }
  v32 = 0;
  std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::_Clear_guard::~_Clear_guard(&v32);
}

```

## disassembly

```asm
0x140007144  mov     [rsp+arg_8], rbx
0x140007149  mov     [rsp+arg_10], rbp
0x14000714e  mov     [rsp+arg_18], rsi
0x140007153  push    rdi
0x140007154  push    r12
0x140007156  push    r13
0x140007158  push    r14
0x14000715a  push    r15
0x14000715c  sub     rsp, 40h
0x140007160  mov     rdx, [rcx+10h]
0x140007164  mov     edi, 1
0x140007169  add     rdx, rdi
0x14000716c  mov     rbx, [rcx+38h]
0x140007170  mov     r13, rcx
0x140007173  xorps   xmm0, xmm0
0x140007176  js      short loc_14000717F
0x140007178  cvtsi2ss xmm0, rdx
0x14000717d  jmp     short loc_140007194
0x14000717f  mov     rax, rdx
0x140007182  and     rdx, rdi
0x140007185  shr     rax, 1
0x140007188  or      rax, rdx
0x14000718b  cvtsi2ss xmm0, rax
0x140007190  addss   xmm0, xmm0
0x140007194  divss   xmm0, dword ptr [rcx+4]; X
0x140007199  call    ceilf_0
0x14000719e  movss   xmm1, cs:__real@5f000000
0x1400071a6  xor     ecx, ecx
0x1400071a8  comiss  xmm0, xmm1
0x1400071ab  jb      short loc_1400071C3
0x1400071ad  subss   xmm0, xmm1
0x1400071b1  comiss  xmm0, xmm1
0x1400071b4  jnb     short loc_1400071C3
0x1400071b6  mov     rax, 8000000000000000h
0x1400071c0  mov     rcx, rax
0x1400071c3  cvttss2si rax, xmm0
0x1400071c8  add     rax, rcx
0x1400071cb  mov     ecx, 8
0x1400071d0  cmp     rax, rcx
0x1400071d3  cmova   rcx, rax
0x1400071d7  cmp     rbx, rcx
0x1400071da  jnb     short loc_1400071F8
0x1400071dc  cmp     rbx, 200h
0x1400071e3  jnb     short loc_1400071F5
0x1400071e5  lea     rax, ds:0[rbx*8]
0x1400071ed  mov     rbx, rax
0x1400071f0  cmp     rax, rcx
0x1400071f3  jnb     short loc_1400071F8
0x1400071f5  mov     rbx, rcx
0x1400071f8  mov     rax, 0FFFFFFFFFFFFFFFh
0x140007202  bsr     rcx, rax
0x140007206  mov     rax, rdi
0x140007209  shl     rax, cl
0x14000720c  cmp     rbx, rax
0x14000720f  jbe     short loc_14000721F
0x140007211  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x140007218  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x14000721f  mov     rbp, [r13+8]
0x140007223  lea     rax, [rbx-1]
0x140007227  or      rax, rdi
0x14000722a  lea     rsi, [r13+18h]
0x14000722e  bsr     rcx, rax
0x140007232  mov     rbx, rdi
0x140007235  mov     r8, rbp
0x140007238  inc     ecx
0x14000723a  shl     rbx, cl
0x14000723d  mov     rcx, rsi
0x140007240  lea     rdx, [rbx+rbx]
0x140007244  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>)
0x140007249  lea     rax, [rbx-1]
0x14000724d  mov     [r13+38h], rbx
0x140007251  mov     [r13+30h], rax
0x140007255  mov     rbx, [r13+8]
0x140007259  mov     rbx, [rbx]
0x14000725c  mov     rdi, rbx
0x14000725f  cmp     rbx, rbp
0x140007262  jz      loc_140007352
0x140007268  mov     rdi, [rdi]
0x14000726b  lea     r12, [rbx+10h]
0x14000726f  mov     rdx, r12
0x140007272  call    ??$?RVCComBSTR@ATL@@@?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@QEBA_KAEBVCComBSTR@ATL@@@Z; std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>::operator()<ATL::CComBSTR>(ATL::CComBSTR const &)
0x140007277  mov     r15, [rsi]
0x14000727a  mov     r14, rax
0x14000727d  and     r14, [r13+30h]
0x140007281  add     r14, r14
0x140007284  cmp     [r15+r14*8], rbp
0x140007288  jnz     short loc_140007298
0x14000728a  mov     [r15+r14*8], rbx
0x14000728e  mov     [r15+r14*8+8], rbx
0x140007293  jmp     loc_140007346
0x140007298  mov     rsi, [r15+r14*8+8]
0x14000729d  or      eax, 0FFFFFFFFh
0x1400072a0  mov     rcx, [r12]; lpString1
0x1400072a4  mov     r9d, eax; cchCount2
0x1400072a7  mov     edx, eax; cchCount1
0x1400072a9  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x1400072b1  mov     r8, [rsi+10h]; lpString2
0x1400072b5  call    cs:__imp_CompareStringOrdinal
0x1400072bb  cmp     eax, 2
0x1400072be  jnz     short loc_140007317
0x1400072c0  mov     r8, [rsi]
0x1400072c3  cmp     r8, rbx
0x1400072c6  jz      short loc_1400072E9
0x1400072c8  mov     rdx, [rbx+8]
0x1400072cc  mov     [rdx], rdi
0x1400072cf  mov     rcx, [rdi+8]
0x1400072d3  mov     [rcx], r8
0x1400072d6  mov     rax, [r8+8]
0x1400072da  mov     [rax], rbx
0x1400072dd  mov     [r8+8], rcx
0x1400072e1  mov     [rdi+8], rdx
0x1400072e5  mov     [rbx+8], rax
0x1400072e9  mov     [r15+r14*8+8], rbx
0x1400072ee  jmp     short loc_140007342
0x1400072f0  mov     rsi, [rsi+8]
0x1400072f4  or      eax, 0FFFFFFFFh
0x1400072f7  mov     rcx, [r12]; lpString1
0x1400072fb  mov     r9d, eax; cchCount2
0x1400072fe  mov     edx, eax; cchCount1
0x140007300  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x140007308  mov     r8, [rsi+10h]; lpString2
0x14000730c  call    cs:__imp_CompareStringOrdinal
0x140007312  cmp     eax, 2
0x140007315  jz      short loc_140007383
0x140007317  cmp     [r15+r14*8], rsi
0x14000731b  jnz     short loc_1400072F0
0x14000731d  mov     rdx, [rbx+8]
0x140007321  mov     [rdx], rdi
0x140007324  mov     rcx, [rdi+8]
0x140007328  mov     [rcx], rsi
0x14000732b  mov     rax, [rsi+8]
0x14000732f  mov     [rax], rbx
0x140007332  mov     [rsi+8], rcx
0x140007336  mov     [rdi+8], rdx
0x14000733a  mov     [rbx+8], rax
0x14000733e  mov     [r15+r14*8], rbx
0x140007342  lea     rsi, [r13+18h]
0x140007346  mov     rbx, rdi
0x140007349  cmp     rdi, rbp
0x14000734c  jnz     loc_140007268
0x140007352  lea     rcx, [rsp+68h+var_38]
0x140007357  mov     [rsp+68h+var_38], 0
0x140007360  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@VCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x140007365  lea     r11, [rsp+68h+var_28]
0x14000736a  mov     rbx, [r11+38h]
0x14000736e  mov     rbp, [r11+40h]
0x140007372  mov     rsi, [r11+48h]
0x140007376  mov     rsp, r11
0x140007379  pop     r15
0x14000737b  pop     r14
0x14000737d  pop     r13
0x14000737f  pop     r12
0x140007381  pop     rdi
0x140007382  retn
0x140007383  mov     r8, [rsi]
0x140007386  mov     rdx, [rbx+8]
0x14000738a  mov     [rdx], rdi
0x14000738d  mov     rcx, [rdi+8]
0x140007391  mov     [rcx], r8
0x140007394  mov     rax, [r8+8]
0x140007398  mov     [rax], rbx
0x14000739b  mov     [r8+8], rcx
0x14000739f  mov     [rdi+8], rdx
0x1400073a3  mov     [rbx+8], rax
0x1400073a7  jmp     short loc_140007342
```
