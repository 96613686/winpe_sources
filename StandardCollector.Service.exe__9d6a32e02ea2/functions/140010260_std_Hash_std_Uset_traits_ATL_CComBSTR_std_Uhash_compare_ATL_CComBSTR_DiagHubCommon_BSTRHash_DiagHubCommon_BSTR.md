# std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::insert(ATL::CComBSTR &&)

- ea: `0x140010260`
- end: `0x140010405`
- name: `?insert@?$_Hash@V?$_Uset_traits@VCComBSTR@ATL@@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@VCComBSTR@ATL@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@VCComBSTR@ATL@@@std@@@std@@@std@@_N@2@$$QEAVCComBSTR@ATL@@@Z`
- size: `421`
- prototype: `__int64 __fastcall(__int64, __int64, BSTR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000f9d4`

## callees

- `0x140006d10`
- `0x140010260`
- `0x140010408`
- `0x140010570`
- `0x140013834`

## import_xrefs

- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400102bf`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400102bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::insert(
        __int64 a1,
        __int64 a2,
        BSTR *a3)
{
  __int64 v5; // rbp
  __int64 v6; // rcx
  char v7; // si
  LPCWCH *v8; // rbx
  __int64 v9; // r9
  unsigned __int64 v10; // rcx
  float v11; // xmm0_4
  float v12; // xmm1_4
  __int64 v13; // rcx
  __int64 v14; // rdx
  LPCWCH **v15; // r8
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r9
  __int128 v20; // [rsp+20h] [rbp-48h] BYREF
  __int64 *v21; // [rsp+30h] [rbp-38h] BYREF
  LPCWCH *v22; // [rsp+38h] [rbp-30h]

  v5 = std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>::operator()<ATL::CComBSTR>(
         a1,
         a3);
  std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::_Find_last<ATL::CComBSTR>(
    v6,
    &v20,
    (LPCWCH *)a3,
    v5);
  v7 = 0;
  if ( !*((_QWORD *)&v20 + 1) )
  {
    if ( qword_140024AA0 == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("unordered_map/set too long");
    v21 = &qword_140024A98;
    v22 = 0;
    v8 = (LPCWCH *)operator new(0x18u);
    v22 = v8;
    v8[2] = *a3;
    *a3 = 0;
    v9 = qword_140024AA0;
    v10 = qword_140024AA0 + 1;
    if ( qword_140024AA0 + 1 < 0 )
      v11 = (float)(int)(v10 & 1 | (v10 >> 1)) + (float)(int)(v10 & 1 | (v10 >> 1));
    else
      v11 = (float)(int)v10;
    if ( qword_140024AC8 < 0 )
      v12 = (float)(qword_140024AC8 & 1 | (unsigned int)((unsigned __int64)qword_140024AC8 >> 1))
          + (float)(qword_140024AC8 & 1 | (unsigned int)((unsigned __int64)qword_140024AC8 >> 1));
    else
      v12 = (float)(int)qword_140024AC8;
    if ( (float)(v11 / v12) > *((float *)&qword_140024A90 + 1) )
    {
      std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::_Rehash_for_1();
      v20 = *(_OWORD *)std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::_Find_last<ATL::CComBSTR>(
                         v13,
                         &v21,
                         v8 + 2,
                         v5);
      v9 = qword_140024AA0;
    }
    v14 = v20;
    v15 = *(LPCWCH ***)(v20 + 8);
    qword_140024AA0 = v9 + 1;
    *v8 = (LPCWCH)v20;
    v8[1] = (LPCWCH)v15;
    *v15 = v8;
    *(_QWORD *)(v14 + 8) = v8;
    v16 = 2 * (v5 & qword_140024AC0);
    v17 = qword_140024AA8;
    v18 = *(_QWORD *)(qword_140024AA8 + 16 * (v5 & qword_140024AC0));
    if ( v18 == qword_140024A98 )
    {
      *(_QWORD *)(qword_140024AA8 + 16 * (v5 & qword_140024AC0)) = v8;
LABEL_18:
      *(_QWORD *)(v17 + 8 * v16 + 8) = v8;
      goto LABEL_19;
    }
    if ( v18 == v14 )
    {
      *(_QWORD *)(qword_140024AA8 + 16 * (v5 & qword_140024AC0)) = v8;
    }
    else if ( *(LPCWCH ***)(qword_140024AA8 + 16 * (v5 & qword_140024AC0) + 8) == v15 )
    {
      goto LABEL_18;
    }
LABEL_19:
    *(_QWORD *)a2 = v8;
    v7 = 1;
    goto LABEL_20;
  }
  *(_QWORD *)a2 = *((_QWORD *)&v20 + 1);
LABEL_20:
  *(_BYTE *)(a2 + 8) = v7;
  return a2;
}

```

## disassembly

```asm
0x140010260  mov     [rsp+arg_0], rbx
0x140010265  push    rbp
0x140010266  push    rsi
0x140010267  push    rdi
0x140010268  push    r14
0x14001026a  push    r15
0x14001026c  sub     rsp, 40h
0x140010270  mov     r14, r8
0x140010273  mov     rdi, rdx
0x140010276  mov     rdx, r8
0x140010279  call    ??$?RVCComBSTR@ATL@@@?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@QEBA_KAEBVCComBSTR@ATL@@@Z; std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>::operator()<ATL::CComBSTR>(ATL::CComBSTR const &)
0x14001027e  mov     rbp, rax
0x140010281  mov     r9, rax
0x140010284  mov     r8, r14
0x140010287  lea     rdx, [rsp+68h+var_48]
0x14001028c  call    ??$_Find_last@VCComBSTR@ATL@@@?$_Hash@V?$_Uset_traits@VCComBSTR@ATL@@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@VCComBSTR@ATL@@@4@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@VCComBSTR@ATL@@PEAX@std@@@1@AEBVCComBSTR@ATL@@_K@Z; std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::_Find_last<ATL::CComBSTR>(ATL::CComBSTR const &,unsigned __int64)
0x140010291  mov     rax, qword ptr [rsp+68h+var_48+8]
0x140010296  xor     esi, esi
0x140010298  test    rax, rax
0x14001029b  jz      short loc_1400102A5
0x14001029d  mov     [rdi], rax
0x1400102a0  jmp     loc_1400103E5
0x1400102a5  mov     rax, 0AAAAAAAAAAAAAAAh
0x1400102af  cmp     cs:qword_140024AA0, rax
0x1400102b6  jnz     short loc_1400102C6
0x1400102b8  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x1400102bf  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1400102c6  lea     rax, qword_140024A98
0x1400102cd  mov     [rsp+68h+var_38], rax
0x1400102d2  mov     [rsp+68h+var_30], rsi
0x1400102d7  mov     ecx, 18h; Size
0x1400102dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400102e1  mov     rbx, rax
0x1400102e4  mov     [rsp+68h+var_30], rax
0x1400102e9  mov     rax, [r14]
0x1400102ec  mov     [rbx+10h], rax
0x1400102f0  mov     [r14], rsi
0x1400102f3  mov     r9, cs:qword_140024AA0
0x1400102fa  lea     rcx, [r9+1]
0x1400102fe  xorps   xmm0, xmm0
0x140010301  test    rcx, rcx
0x140010304  js      short loc_14001030D
0x140010306  cvtsi2ss xmm0, rcx
0x14001030b  jmp     short loc_140010322
0x14001030d  mov     rax, rcx
0x140010310  shr     rax, 1
0x140010313  and     ecx, 1
0x140010316  or      rax, rcx
0x140010319  cvtsi2ss xmm0, rax
0x14001031e  addss   xmm0, xmm0
0x140010322  mov     rcx, cs:qword_140024AC8
0x140010329  xorps   xmm1, xmm1
0x14001032c  test    rcx, rcx
0x14001032f  js      short loc_140010338
0x140010331  cvtsi2ss xmm1, rcx
0x140010336  jmp     short loc_14001034D
0x140010338  mov     rax, rcx
0x14001033b  shr     rax, 1
0x14001033e  and     ecx, 1
0x140010341  or      rax, rcx
0x140010344  cvtsi2ss xmm1, rax
0x140010349  addss   xmm1, xmm1
0x14001034d  divss   xmm0, xmm1
0x140010351  comiss  xmm0, dword ptr cs:qword_140024A90+4
0x140010358  jbe     short loc_140010380
0x14001035a  call    ?_Rehash_for_1@?$_Hash@V?$_Uset_traits@VCComBSTR@ATL@@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@VCComBSTR@ATL@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::_Rehash_for_1(void)
0x14001035f  mov     r9, rbp
0x140010362  lea     r8, [rbx+10h]
0x140010366  lea     rdx, [rsp+68h+var_38]
0x14001036b  call    ??$_Find_last@VCComBSTR@ATL@@@?$_Hash@V?$_Uset_traits@VCComBSTR@ATL@@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@VCComBSTR@ATL@@@4@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@VCComBSTR@ATL@@PEAX@std@@@1@AEBVCComBSTR@ATL@@_K@Z; std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::_Find_last<ATL::CComBSTR>(ATL::CComBSTR const &,unsigned __int64)
0x140010370  movups  xmm0, xmmword ptr [rax]
0x140010373  movdqu  [rsp+68h+var_48], xmm0
0x140010379  mov     r9, cs:qword_140024AA0
0x140010380  mov     rdx, qword ptr [rsp+68h+var_48]
0x140010385  mov     r8, [rdx+8]
0x140010389  inc     r9
0x14001038c  mov     cs:qword_140024AA0, r9
0x140010393  mov     [rbx], rdx
0x140010396  mov     [rbx+8], r8
0x14001039a  mov     [r8], rbx
0x14001039d  mov     [rdx+8], rbx
0x1400103a1  mov     rax, cs:qword_140024AC0
0x1400103a8  and     rax, rbp
0x1400103ab  add     rax, rax
0x1400103ae  mov     rcx, cs:qword_140024AA8
0x1400103b5  mov     r9, [rcx+rax*8]
0x1400103b9  cmp     r9, cs:qword_140024A98
0x1400103c0  jnz     short loc_1400103C8
0x1400103c2  mov     [rcx+rax*8], rbx
0x1400103c6  jmp     short loc_1400103DA
0x1400103c8  cmp     r9, rdx
0x1400103cb  jnz     short loc_1400103D3
0x1400103cd  mov     [rcx+rax*8], rbx
0x1400103d1  jmp     short loc_1400103DF
0x1400103d3  cmp     [rcx+rax*8+8], r8
0x1400103d8  jnz     short loc_1400103DF
0x1400103da  mov     [rcx+rax*8+8], rbx
0x1400103df  mov     [rdi], rbx
0x1400103e2  mov     sil, 1
0x1400103e5  mov     eax, 8
0x1400103ea  mov     rcx, rdi
0x1400103ed  mov     [rcx+rax], sil
0x1400103f1  mov     rax, rdi
0x1400103f4  mov     rbx, [rsp+68h+arg_0]
0x1400103f9  add     rsp, 40h
0x1400103fd  pop     r15
0x1400103ff  pop     r14
0x140010401  pop     rdi
0x140010402  pop     rsi
0x140010403  pop     rbp
0x140010404  retn
```
