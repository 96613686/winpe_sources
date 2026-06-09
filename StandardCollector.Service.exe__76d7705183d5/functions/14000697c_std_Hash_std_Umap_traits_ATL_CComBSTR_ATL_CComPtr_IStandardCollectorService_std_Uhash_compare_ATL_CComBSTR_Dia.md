# std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::emplace<ATL::CComBSTR &,ATL::CComPtr<IStandardCollectorService> &>(ATL::CComBSTR &,ATL::CComPtr<IStandardCollectorService> &)

- ea: `0x14000697c`
- end: `0x140006b5a`
- name: `??$emplace@AEAVCComBSTR@ATL@@AEAV?$CComPtr@UIStandardCollectorService@@@2@@?$_Hash@V?$_Umap_traits@VCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@@std@@@std@@@std@@_N@1@AEAVCComBSTR@ATL@@AEAV?$CComPtr@UIStandardCollectorService@@@4@@Z`
- size: `478`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005b70`

## callees

- `0x140002e74`
- `0x14000697c`
- `0x140006d10`
- `0x140006dc0`
- `0x140007144`
- `0x140013834`
- `0x140014c70`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x140006a1e`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140006a1e`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140006a29`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140006a29`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400069eb`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400069eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::emplace<ATL::CComBSTR &,ATL::CComPtr<IStandardCollectorService> &>(
        __int64 a1,
        __int64 a2,
        LPCWCH *a3,
        LPCWCH *a4)
{
  __int64 v8; // r13
  LPCWCH *v9; // rbx
  BSTR v10; // rax
  UINT v11; // eax
  LPCWCH v12; // rcx
  __int64 v13; // rcx
  float v14; // xmm0_4
  __int64 v15; // rcx
  float v16; // xmm1_4
  __int64 v17; // rax
  __int64 v18; // rdx
  LPCWCH **v19; // r8
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r9
  __int128 v24; // [rsp+20h] [rbp-58h] BYREF
  __int64 v25; // [rsp+30h] [rbp-48h] BYREF
  LPCWCH *v26; // [rsp+38h] [rbp-40h]

  v8 = std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>::operator()<ATL::CComBSTR>(
         a1,
         a3);
  std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::_Find_last<ATL::CComBSTR>(
    (_QWORD *)a1,
    &v24,
    a3,
    v8);
  if ( !*((_QWORD *)&v24 + 1) )
  {
    if ( *(_QWORD *)(a1 + 16) == 0x7FFFFFFFFFFFFFFLL )
      std::_Xlength_error("unordered_map/set too long");
    v25 = a1 + 8;
    v26 = 0;
    v9 = (LPCWCH *)operator new(0x20u);
    v26 = v9;
    if ( *a3 )
    {
      v11 = SysStringByteLen((BSTR)*a3);
      v10 = SysAllocStringByteLen((LPCSTR)*a3, v11);
    }
    else
    {
      v10 = 0;
    }
    v9[2] = v10;
    if ( *a3 && !v10 )
      ATL::AtlThrowImpl(-2147024882);
    v12 = *a4;
    v9[3] = *a4;
    if ( v12 )
      (*(void (__fastcall **)(LPCWCH))(*(_QWORD *)v12 + 8LL))(v12);
    v13 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v13 < 0 )
      v14 = (float)(v13 & 1 | (unsigned int)((unsigned __int64)v13 >> 1))
          + (float)(v13 & 1 | (unsigned int)((unsigned __int64)v13 >> 1));
    else
      v14 = (float)(int)v13;
    v15 = *(_QWORD *)(a1 + 56);
    if ( v15 < 0 )
    {
      v17 = *(_QWORD *)(a1 + 56) & 1LL | ((unsigned __int64)v15 >> 1);
      v16 = (float)(int)v17 + (float)(int)v17;
    }
    else
    {
      v16 = (float)(int)v15;
    }
    if ( (float)(v14 / v16) > *(float *)(a1 + 4) )
    {
      std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::_Rehash_for_1(a1);
      v24 = *(_OWORD *)std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::_Find_last<ATL::CComBSTR>(
                         (_QWORD *)a1,
                         &v25,
                         v9 + 2,
                         v8);
    }
    v18 = v24;
    v19 = *(LPCWCH ***)(v24 + 8);
    ++*(_QWORD *)(a1 + 16);
    *v9 = (LPCWCH)v18;
    v9[1] = (LPCWCH)v19;
    *v19 = v9;
    *(_QWORD *)(v18 + 8) = v9;
    v20 = 2 * (v8 & *(_QWORD *)(a1 + 48));
    v21 = *(_QWORD *)(a1 + 24);
    v22 = *(_QWORD *)(v21 + 16 * (v8 & *(_QWORD *)(a1 + 48)));
    if ( v22 == *(_QWORD *)(a1 + 8) )
    {
      *(_QWORD *)(v21 + 16 * (v8 & *(_QWORD *)(a1 + 48))) = v9;
LABEL_25:
      *(_QWORD *)(v21 + 8 * v20 + 8) = v9;
      goto LABEL_26;
    }
    if ( v22 == v18 )
    {
      *(_QWORD *)(v21 + 16 * (v8 & *(_QWORD *)(a1 + 48))) = v9;
    }
    else if ( *(LPCWCH ***)(v21 + 16 * (v8 & *(_QWORD *)(a1 + 48)) + 8) == v19 )
    {
      goto LABEL_25;
    }
LABEL_26:
    *(_QWORD *)a2 = v9;
    *(_BYTE *)(a2 + 8) = 1;
    return a2;
  }
  *(_QWORD *)a2 = *((_QWORD *)&v24 + 1);
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x14000697c  mov     [rsp+arg_18], rbx
0x140006981  push    rbp
0x140006982  push    rsi
0x140006983  push    rdi
0x140006984  push    r12
0x140006986  push    r13
0x140006988  push    r14
0x14000698a  push    r15
0x14000698c  sub     rsp, 40h
0x140006990  mov     r12, r9
0x140006993  mov     r14, r8
0x140006996  mov     rdi, rdx
0x140006999  mov     rsi, rcx
0x14000699c  mov     rdx, r8
0x14000699f  call    ??$?RVCComBSTR@ATL@@@?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@QEBA_KAEBVCComBSTR@ATL@@@Z; std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>::operator()<ATL::CComBSTR>(ATL::CComBSTR const &)
0x1400069a4  mov     r13, rax
0x1400069a7  mov     r9, rax
0x1400069aa  mov     r8, r14
0x1400069ad  lea     rdx, [rsp+78h+var_58]
0x1400069b2  mov     rcx, rsi
0x1400069b5  call    ??$_Find_last@VCComBSTR@ATL@@@?$_Hash@V?$_Umap_traits@VCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@PEAX@std@@@1@AEBVCComBSTR@ATL@@_K@Z; std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::_Find_last<ATL::CComBSTR>(ATL::CComBSTR const &,unsigned __int64)
0x1400069ba  mov     rcx, qword ptr [rsp+78h+var_58+8]
0x1400069bf  test    rcx, rcx
0x1400069c2  jz      short loc_1400069D0
0x1400069c4  mov     [rdi], rcx
0x1400069c7  mov     byte ptr [rdi+8], 0
0x1400069cb  jmp     loc_140006B34
0x1400069d0  lea     rbp, [rsi+8]
0x1400069d4  mov     rax, 7FFFFFFFFFFFFFFh
0x1400069de  cmp     [rbp+8], rax
0x1400069e2  jnz     short loc_1400069F2
0x1400069e4  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x1400069eb  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1400069f2  mov     [rsp+78h+var_48], rbp
0x1400069f7  mov     [rsp+78h+var_40], 0
0x140006a00  mov     ecx, 20h ; ' '; Size
0x140006a05  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140006a0a  mov     rbx, rax
0x140006a0d  mov     [rsp+78h+var_40], rax
0x140006a12  mov     rcx, [r14]; bstr
0x140006a15  test    rcx, rcx
0x140006a18  jnz     short loc_140006A1E
0x140006a1a  xor     eax, eax
0x140006a1c  jmp     short loc_140006A2F
0x140006a1e  call    cs:__imp_SysStringByteLen
0x140006a24  mov     edx, eax; len
0x140006a26  mov     rcx, [r14]; psz
0x140006a29  call    cs:__imp_SysAllocStringByteLen
0x140006a2f  mov     [rbx+10h], rax
0x140006a33  cmp     qword ptr [r14], 0
0x140006a37  jz      short loc_140006A42
0x140006a39  test    rax, rax
0x140006a3c  jz      loc_140006B4F
0x140006a42  mov     rcx, [r12]
0x140006a46  mov     [rbx+18h], rcx
0x140006a4a  test    rcx, rcx
0x140006a4d  jz      short loc_140006A5D
0x140006a4f  mov     rax, [rcx]
0x140006a52  mov     rax, [rax+8]
0x140006a56  call    cs:__guard_dispatch_icall_fptr
0x140006a5c  nop
0x140006a5d  mov     rcx, [rsi+10h]
0x140006a61  add     rcx, 1
0x140006a65  xorps   xmm0, xmm0
0x140006a68  js      short loc_140006A71
0x140006a6a  cvtsi2ss xmm0, rcx
0x140006a6f  jmp     short loc_140006A86
0x140006a71  mov     rax, rcx
0x140006a74  shr     rax, 1
0x140006a77  and     ecx, 1
0x140006a7a  or      rax, rcx
0x140006a7d  cvtsi2ss xmm0, rax
0x140006a82  addss   xmm0, xmm0
0x140006a86  mov     rcx, [rsi+38h]
0x140006a8a  xorps   xmm1, xmm1
0x140006a8d  test    rcx, rcx
0x140006a90  js      short loc_140006A99
0x140006a92  cvtsi2ss xmm1, rcx
0x140006a97  jmp     short loc_140006AAE
0x140006a99  mov     rax, rcx
0x140006a9c  shr     rax, 1
0x140006a9f  and     ecx, 1
0x140006aa2  or      rax, rcx
0x140006aa5  cvtsi2ss xmm1, rax
0x140006aaa  addss   xmm1, xmm1
0x140006aae  divss   xmm0, xmm1
0x140006ab2  comiss  xmm0, dword ptr [rsi+4]
0x140006ab6  jbe     short loc_140006ADD
0x140006ab8  mov     rcx, rsi
0x140006abb  call    ?_Rehash_for_1@?$_Hash@V?$_Umap_traits@VCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@@5@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::_Rehash_for_1(void)
0x140006ac0  mov     r9, r13
0x140006ac3  lea     r8, [rbx+10h]
0x140006ac7  lea     rdx, [rsp+78h+var_48]
0x140006acc  mov     rcx, rsi
0x140006acf  call    ??$_Find_last@VCComBSTR@ATL@@@?$_Hash@V?$_Umap_traits@VCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@PEAX@std@@@1@AEBVCComBSTR@ATL@@_K@Z; std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::_Find_last<ATL::CComBSTR>(ATL::CComBSTR const &,unsigned __int64)
0x140006ad4  movups  xmm0, xmmword ptr [rax]
0x140006ad7  movdqu  [rsp+78h+var_58], xmm0
0x140006add  mov     rdx, qword ptr [rsp+78h+var_58]
0x140006ae2  mov     r8, [rdx+8]
0x140006ae6  inc     qword ptr [rsi+10h]
0x140006aea  mov     [rbx], rdx
0x140006aed  mov     [rbx+8], r8
0x140006af1  mov     [r8], rbx
0x140006af4  mov     [rdx+8], rbx
0x140006af8  mov     rax, [rsi+30h]
0x140006afc  and     rax, r13
0x140006aff  add     rax, rax
0x140006b02  mov     rcx, [rsi+18h]
0x140006b06  mov     r9, [rcx+rax*8]
0x140006b0a  cmp     r9, [rbp+0]
0x140006b0e  jnz     short loc_140006B16
0x140006b10  mov     [rcx+rax*8], rbx
0x140006b14  jmp     short loc_140006B28
0x140006b16  cmp     r9, rdx
0x140006b19  jnz     short loc_140006B21
0x140006b1b  mov     [rcx+rax*8], rbx
0x140006b1f  jmp     short loc_140006B2D
0x140006b21  cmp     [rcx+rax*8+8], r8
0x140006b26  jnz     short loc_140006B2D
0x140006b28  mov     [rcx+rax*8+8], rbx
0x140006b2d  mov     [rdi], rbx
0x140006b30  mov     byte ptr [rdi+8], 1
0x140006b34  mov     rax, rdi
0x140006b37  mov     rbx, [rsp+78h+arg_18]
0x140006b3f  add     rsp, 40h
0x140006b43  pop     r15
0x140006b45  pop     r14
0x140006b47  pop     r13
0x140006b49  pop     r12
0x140006b4b  pop     rdi
0x140006b4c  pop     rsi
0x140006b4d  pop     rbp
0x140006b4e  retn
0x140006b4f  mov     ecx, 8007000Eh; int
0x140006b54  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
