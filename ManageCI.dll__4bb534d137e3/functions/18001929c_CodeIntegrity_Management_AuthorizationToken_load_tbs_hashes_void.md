# CodeIntegrity::Management::AuthorizationToken::load_tbs_hashes(void)

- ea: `0x18001929c`
- end: `0x180019412`
- name: `?load_tbs_hashes@AuthorizationToken@Management@CodeIntegrity@@AEAAXXZ`
- size: `374`
- prototype: `void __fastcall(CodeIntegrity::Management::AuthorizationToken *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018b50`

## callees

- `0x18000830c`
- `0x180008390`
- `0x18000d450`
- `0x180016b80`
- `0x180016c38`
- `0x180017f6c`
- `0x180018214`
- `0x180018490`
- `0x18001929c`

## string_xrefs

- `0x180019380`: `onecore\base\ci\management\dll\authorizationtoken.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CodeIntegrity::Management::AuthorizationToken::load_tbs_hashes(
        CodeIntegrity::Management::AuthorizationToken *this)
{
  unsigned int dword; // eax
  unsigned int v3; // edi
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r10
  unsigned __int64 v7; // rax
  int v8; // [rsp+20h] [rbp-48h]
  __int128 v9; // [rsp+30h] [rbp-38h] BYREF
  __int64 v10; // [rsp+40h] [rbp-28h]
  __int64 v11; // [rsp+48h] [rbp-20h] BYREF
  __int64 v12; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v15; // [rsp+78h] [rbp+10h] BYREF

  try
  {
    dword = CodeIntegrity::Management::detail::SbcpTokenView::get_dword(
              this,
              -2130706432,
              L"SupplementalPolicyAuthorization",
              L"CertTBSHashCount");
    v9 = 0;
    v3 = 0;
    v10 = 0;
    std::vector<std::array<unsigned char,32>>::_Construct_n<>(&v9, dword);
    CodeIntegrity::Management::detail::SbcpTokenView::get_binary(
      (__int64)this,
      (__int64)&v11,
      -2130706432,
      L"SupplementalPolicyAuthorization",
      (PCWSTR)L"CertTBSHashes");
    v4 = v12;
    v5 = v11;
    if ( (((_BYTE)v12 - (_BYTE)v11) & 0x1F) != 0 )
    {
      *((_WORD *)this + 4) |= 0x1000u;
      std::vector<unsigned char>::_Tidy((__int64)&v11);
      std::vector<std::array<unsigned char,32>>::_Tidy(&v9);
    }
    else
    {
      while ( 1 )
      {
        v6 = v3;
        if ( v3 >= (unsigned __int64)(v4 - v5) >> 5 )
          break;
        v7 = 32LL * ++v3;
        if ( v7 > 0xFFFFFFFF )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xAD,
            (int)"onecore\\base\\ci\\management\\dll\\authorizationtoken.cpp",
            v7 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
            v8);
        std::copy<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>,std::_Array_iterator<unsigned char,64>>(
          &v15,
          (const void *)(v5 + 32 * v3 - 32),
          v5 + 32 * v3,
          (char *)(v9 + 32 * v6));
        v4 = v12;
        v5 = v11;
      }
      if ( (__int128 *)((char *)this + 136) != &v9 )
        std::vector<std::array<unsigned char,32>>::_Assign_counted_range<std::array<unsigned char,32> *>(
          (char *)this + 136,
          v9,
          (__int64)(*((_QWORD *)&v9 + 1) - v9) >> 5);
      std::vector<unsigned char>::_Tidy((__int64)&v11);
      std::vector<std::array<unsigned char,32>>::_Tidy(&v9);
    }
  }
  catch ( std::exception )
  {
    *((_WORD *)this + 4) |= 0x1000u;
  }
}

```

## disassembly

```asm
0x18001929c  mov     [rsp+arg_10], rbx
0x1800192a1  mov     [rsp+arg_18], rsi
0x1800192a6  mov     [rsp+arg_0], rcx
0x1800192ab  push    rdi
0x1800192ac  sub     rsp, 60h
0x1800192b0  mov     rbx, rcx
0x1800192b3  lea     r9, aCerttbshashcou; "CertTBSHashCount"
0x1800192ba  lea     r8, SourceString; "SupplementalPolicyAuthorization"
0x1800192c1  mov     esi, 81000000h
0x1800192c6  mov     edx, esi; unsigned int
0x1800192c8  call    ?get_dword@SbcpTokenView@detail@Management@CodeIntegrity@@IEAAIIPEBG0@Z; CodeIntegrity::Management::detail::SbcpTokenView::get_dword(uint,ushort const *,ushort const *)
0x1800192cd  xorps   xmm0, xmm0
0x1800192d0  movdqu  [rsp+68h+var_38], xmm0
0x1800192d6  xor     edi, edi
0x1800192d8  mov     [rsp+68h+var_28], rdi
0x1800192dd  mov     edx, eax
0x1800192df  lea     rcx, [rsp+68h+var_38]
0x1800192e4  call    ??$_Construct_n@$$V@?$vector@V?$array@E$0CA@@std@@V?$allocator@V?$array@E$0CA@@std@@@2@@std@@AEAAX_K@Z; std::vector<std::array<uchar,32>>::_Construct_n<>(unsigned __int64)
0x1800192e9  nop
0x1800192ea  lea     rax, aCerttbshashes; "CertTBSHashes"
0x1800192f1  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800192f6  lea     r9, SourceString; "SupplementalPolicyAuthorization"
0x1800192fd  mov     r8d, esi
0x180019300  lea     rdx, [rsp+68h+var_20]
0x180019305  mov     rcx, rbx
0x180019308  call    ?get_binary@SbcpTokenView@detail@Management@CodeIntegrity@@IEAA?AV?$vector@EV?$allocator@E@std@@@std@@IPEBG0@Z; CodeIntegrity::Management::detail::SbcpTokenView::get_binary(uint,ushort const *,ushort const *)
0x18001930d  nop
0x18001930e  mov     rcx, [rsp+68h+var_18]
0x180019313  mov     al, cl
0x180019315  mov     rdx, [rsp+68h+var_20]
0x18001931a  sub     al, dl
0x18001931c  test    al, 1Fh
0x18001931e  jz      short loc_180019344
0x180019320  mov     eax, 1000h
0x180019325  or      [rbx+8], ax
0x180019329  lea     rcx, [rsp+68h+var_20]
0x18001932e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180019333  nop
0x180019334  lea     rcx, [rsp+68h+var_38]
0x180019339  call    ?_Tidy@?$vector@V?$array@E$0CA@@std@@V?$allocator@V?$array@E$0CA@@std@@@2@@std@@AEAAXXZ; std::vector<std::array<uchar,32>>::_Tidy(void)
0x18001933e  nop
0x18001933f  jmp     loc_180019400
0x180019344  mov     esi, 0FFFFFFFFh
0x180019349  mov     r10d, edi
0x18001934c  sub     rcx, rdx
0x18001934f  shr     rcx, 5
0x180019353  cmp     r10, rcx
0x180019356  jnb     short loc_1800193C0
0x180019358  inc     edi
0x18001935a  mov     eax, edi
0x18001935c  shl     rax, 5
0x180019360  cmp     rax, rsi
0x180019363  mov     ecx, eax
0x180019365  jbe     short loc_180019369
0x180019367  mov     ecx, esi
0x180019369  cmp     rsi, rax
0x18001936c  sbb     r9d, r9d
0x18001936f  and     r9d, 80070216h; char *
0x180019376  mov     r11, [rsp+68h]
0x18001937b  cmp     rax, rsi
0x18001937e  jbe     short loc_180019394
0x180019380  lea     r8, aOnecoreBaseCiM_5; "onecore\\base\\ci\\management\\dll\\aut"...
0x180019387  mov     edx, 0ADh; void *
0x18001938c  mov     rcx, r11; this
0x18001938f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180019394  mov     r8d, ecx
0x180019397  add     r8, rdx
0x18001939a  shl     r10, 5
0x18001939e  add     r10, qword ptr [rsp+68h+var_38]
0x1800193a3  lea     rdx, [r8-20h]
0x1800193a7  mov     r9, r10
0x1800193aa  lea     rcx, [rsp+68h+arg_8]
0x1800193af  call    ??$copy@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@V?$_Array_iterator@E$0EA@@2@@std@@YA?AV?$_Array_iterator@E$0EA@@0@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@0@0V10@@Z; std::copy<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Array_iterator<uchar,64>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Array_iterator<uchar,64>)
0x1800193b4  mov     rcx, [rsp+68h+var_18]
0x1800193b9  mov     rdx, [rsp+68h+var_20]
0x1800193be  jmp     short loc_180019349
0x1800193c0  lea     rcx, [rbx+88h]
0x1800193c7  lea     rax, [rsp+68h+var_38]
0x1800193cc  cmp     rcx, rax
0x1800193cf  jz      short loc_1800193E8
0x1800193d1  mov     rdx, qword ptr [rsp+68h+var_38]
0x1800193d6  mov     r8, qword ptr [rsp+68h+var_38+8]
0x1800193db  sub     r8, rdx
0x1800193de  sar     r8, 5
0x1800193e2  call    ??$_Assign_counted_range@PEAV?$array@E$0CA@@std@@@?$vector@V?$array@E$0CA@@std@@V?$allocator@V?$array@E$0CA@@std@@@2@@std@@AEAAXPEAV?$array@E$0CA@@1@_K@Z; std::vector<std::array<uchar,32>>::_Assign_counted_range<std::array<uchar,32> *>(std::array<uchar,32> *,unsigned __int64)
0x1800193e7  nop
0x1800193e8  lea     rcx, [rsp+68h+var_20]
0x1800193ed  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800193f2  nop
0x1800193f3  lea     rcx, [rsp+68h+var_38]
0x1800193f8  call    ?_Tidy@?$vector@V?$array@E$0CA@@std@@V?$allocator@V?$array@E$0CA@@std@@@2@@std@@AEAAXXZ; std::vector<std::array<uchar,32>>::_Tidy(void)
0x1800193fd  nop
0x1800193fe  jmp     short $+2
0x180019400  lea     r11, [rsp+68h+var_8]
0x180019405  mov     rbx, [r11+20h]
0x180019409  mov     rsi, [r11+28h]
0x18001940d  mov     rsp, r11
0x180019410  pop     rdi
0x180019411  retn
```
