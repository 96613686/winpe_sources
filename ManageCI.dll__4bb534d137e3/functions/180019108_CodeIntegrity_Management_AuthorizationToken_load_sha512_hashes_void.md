# CodeIntegrity::Management::AuthorizationToken::load_sha512_hashes(void)

- ea: `0x180019108`
- end: `0x180019294`
- name: `?load_sha512_hashes@AuthorizationToken@Management@CodeIntegrity@@AEAAXXZ`
- size: `396`
- prototype: `void __fastcall(CodeIntegrity::Management::AuthorizationToken *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018b50`

## callees

- `0x18000830c`
- `0x180008430`
- `0x18000d450`
- `0x180016b80`
- `0x180016ce0`
- `0x180018118`
- `0x18001830c`
- `0x180018490`
- `0x180019108`

## string_xrefs

- `0x180019202`: `onecore\base\ci\management\dll\authorizationtoken.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CodeIntegrity::Management::AuthorizationToken::load_sha512_hashes(
        CodeIntegrity::Management::AuthorizationToken *this,
        __int64 a2)
{
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

  v3 = 0;
  LODWORD(v15) = 0;
  if ( (unsigned int)CodeIntegrity::Management::detail::SbcpTokenView::get_dword_nothrow(
                       this,
                       a2,
                       L"SupplementalPolicyAuthorization",
                       L"CertTBSSha512HashCount",
                       (unsigned int *)&v15) != -2147023728 )
  {
    v9 = 0;
    v10 = 0;
    try
    {
      std::vector<std::array<unsigned char,64>>::_Construct_n<>();
      CodeIntegrity::Management::detail::SbcpTokenView::get_binary(
        (__int64)this,
        (__int64)&v11,
        -2130706432,
        L"SupplementalPolicyAuthorization",
        (PCWSTR)L"CertTBSSha512Hashes");
      v4 = v12;
      v5 = v11;
      if ( (((_BYTE)v12 - (_BYTE)v11) & 0x3F) != 0 )
      {
        *((_WORD *)this + 4) |= 0x1000u;
        std::vector<unsigned char>::_Tidy((__int64)&v11);
        std::vector<std::array<unsigned char,64>>::_Tidy(&v9);
      }
      else
      {
        while ( 1 )
        {
          v6 = v3;
          if ( v3 >= (unsigned __int64)(v4 - v5) >> 6 )
            break;
          v7 = (unsigned __int64)++v3 << 6;
          if ( v7 > 0xFFFFFFFF )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x107,
              (int)"onecore\\base\\ci\\management\\dll\\authorizationtoken.cpp",
              v7 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
              v8);
          std::copy<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>,std::_Array_iterator<unsigned char,64>>(
            &v15,
            (const void *)(v5 + (v3 << 6) - 64),
            v5 + (v3 << 6),
            (char *)(v9 + (v6 << 6)));
          v4 = v12;
          v5 = v11;
        }
        if ( (__int128 *)((char *)this + 184) != &v9 )
          std::vector<std::array<unsigned char,64>>::_Assign_counted_range<std::array<unsigned char,64> *>(
            (char *)this + 184,
            v9,
            (__int64)(*((_QWORD *)&v9 + 1) - v9) >> 6);
        std::vector<unsigned char>::_Tidy((__int64)&v11);
        std::vector<std::array<unsigned char,64>>::_Tidy(&v9);
      }
    }
    catch ( std::exception )
    {
      *((_WORD *)this + 4) |= 0x1000u;
    }
  }
}

```

## disassembly

```asm
0x180019108  mov     rax, rsp
0x18001910b  mov     [rax+18h], rbx
0x18001910f  mov     [rax+20h], rsi
0x180019113  mov     [rax+8], rcx
0x180019117  push    rdi
0x180019118  sub     rsp, 60h
0x18001911c  mov     rbx, rcx
0x18001911f  xor     edi, edi
0x180019121  mov     [rax+10h], edi
0x180019124  lea     rax, [rax+10h]
0x180019128  mov     qword ptr [rsp+68h+var_48], rax; unsigned int *
0x18001912d  lea     r9, aCerttbssha512h; "CertTBSSha512HashCount"
0x180019134  lea     r8, SourceString; "SupplementalPolicyAuthorization"
0x18001913b  call    ?get_dword_nothrow@SbcpTokenView@detail@Management@CodeIntegrity@@IEAAJIPEBG0PEAI@Z; CodeIntegrity::Management::detail::SbcpTokenView::get_dword_nothrow(uint,ushort const *,ushort const *,uint *)
0x180019140  cmp     eax, 80070490h
0x180019145  jnz     short loc_18001914C
0x180019147  jmp     loc_180019282
0x18001914c  xorps   xmm0, xmm0
0x18001914f  movdqu  [rsp+68h+var_38], xmm0
0x180019155  mov     [rsp+68h+var_28], rdi
0x18001915a  mov     edx, dword ptr [rsp+68h+arg_8]
0x18001915e  lea     rcx, [rsp+68h+var_38]
0x180019163  call    ??$_Construct_n@$$V@?$vector@V?$array@E$0EA@@std@@V?$allocator@V?$array@E$0EA@@std@@@2@@std@@AEAAX_K@Z; std::vector<std::array<uchar,64>>::_Construct_n<>(unsigned __int64)
0x180019168  nop
0x180019169  lea     rax, aCerttbssha512h_0; "CertTBSSha512Hashes"
0x180019170  mov     qword ptr [rsp+68h+var_48], rax; int
0x180019175  lea     r9, SourceString; "SupplementalPolicyAuthorization"
0x18001917c  mov     r8d, 81000000h
0x180019182  lea     rdx, [rsp+68h+var_20]
0x180019187  mov     rcx, rbx
0x18001918a  call    ?get_binary@SbcpTokenView@detail@Management@CodeIntegrity@@IEAA?AV?$vector@EV?$allocator@E@std@@@std@@IPEBG0@Z; CodeIntegrity::Management::detail::SbcpTokenView::get_binary(uint,ushort const *,ushort const *)
0x18001918f  nop
0x180019190  mov     rcx, [rsp+68h+var_18]
0x180019195  mov     al, cl
0x180019197  mov     rdx, [rsp+68h+var_20]
0x18001919c  sub     al, dl
0x18001919e  test    al, 3Fh
0x1800191a0  jz      short loc_1800191C6
0x1800191a2  mov     eax, 1000h
0x1800191a7  or      [rbx+8], ax
0x1800191ab  lea     rcx, [rsp+68h+var_20]
0x1800191b0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800191b5  nop
0x1800191b6  lea     rcx, [rsp+68h+var_38]
0x1800191bb  call    ?_Tidy@?$vector@V?$array@E$0EA@@std@@V?$allocator@V?$array@E$0EA@@std@@@2@@std@@AEAAXXZ; std::vector<std::array<uchar,64>>::_Tidy(void)
0x1800191c0  nop
0x1800191c1  jmp     loc_180019282
0x1800191c6  mov     esi, 0FFFFFFFFh
0x1800191cb  mov     r10d, edi
0x1800191ce  sub     rcx, rdx
0x1800191d1  shr     rcx, 6
0x1800191d5  cmp     r10, rcx
0x1800191d8  jnb     short loc_180019242
0x1800191da  inc     edi
0x1800191dc  mov     eax, edi
0x1800191de  shl     rax, 6
0x1800191e2  cmp     rax, rsi
0x1800191e5  mov     ecx, eax
0x1800191e7  jbe     short loc_1800191EB
0x1800191e9  mov     ecx, esi
0x1800191eb  cmp     rsi, rax
0x1800191ee  sbb     r9d, r9d
0x1800191f1  and     r9d, 80070216h; char *
0x1800191f8  mov     r11, [rsp+68h]
0x1800191fd  cmp     rax, rsi
0x180019200  jbe     short loc_180019216
0x180019202  lea     r8, aOnecoreBaseCiM_5; "onecore\\base\\ci\\management\\dll\\aut"...
0x180019209  mov     edx, 107h; void *
0x18001920e  mov     rcx, r11; this
0x180019211  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180019216  mov     r8d, ecx
0x180019219  add     r8, rdx
0x18001921c  shl     r10, 6
0x180019220  add     r10, qword ptr [rsp+68h+var_38]
0x180019225  lea     rdx, [r8-40h]
0x180019229  mov     r9, r10
0x18001922c  lea     rcx, [rsp+68h+arg_8]
0x180019231  call    ??$copy@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@V?$_Array_iterator@E$0EA@@2@@std@@YA?AV?$_Array_iterator@E$0EA@@0@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@0@0V10@@Z; std::copy<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Array_iterator<uchar,64>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Array_iterator<uchar,64>)
0x180019236  mov     rcx, [rsp+68h+var_18]
0x18001923b  mov     rdx, [rsp+68h+var_20]
0x180019240  jmp     short loc_1800191CB
0x180019242  lea     rcx, [rbx+0B8h]
0x180019249  lea     rax, [rsp+68h+var_38]
0x18001924e  cmp     rcx, rax
0x180019251  jz      short loc_18001926A
0x180019253  mov     rdx, qword ptr [rsp+68h+var_38]
0x180019258  mov     r8, qword ptr [rsp+68h+var_38+8]
0x18001925d  sub     r8, rdx
0x180019260  sar     r8, 6
0x180019264  call    ??$_Assign_counted_range@PEAV?$array@E$0EA@@std@@@?$vector@V?$array@E$0EA@@std@@V?$allocator@V?$array@E$0EA@@std@@@2@@std@@AEAAXPEAV?$array@E$0EA@@1@_K@Z; std::vector<std::array<uchar,64>>::_Assign_counted_range<std::array<uchar,64> *>(std::array<uchar,64> *,unsigned __int64)
0x180019269  nop
0x18001926a  lea     rcx, [rsp+68h+var_20]
0x18001926f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180019274  nop
0x180019275  lea     rcx, [rsp+68h+var_38]
0x18001927a  call    ?_Tidy@?$vector@V?$array@E$0EA@@std@@V?$allocator@V?$array@E$0EA@@std@@@2@@std@@AEAAXXZ; std::vector<std::array<uchar,64>>::_Tidy(void)
0x18001927f  nop
0x180019280  jmp     short $+2
0x180019282  lea     r11, [rsp+68h+var_8]
0x180019287  mov     rbx, [r11+20h]
0x18001928b  mov     rsi, [r11+28h]
0x18001928f  mov     rsp, r11
0x180019292  pop     rdi
0x180019293  retn
```
