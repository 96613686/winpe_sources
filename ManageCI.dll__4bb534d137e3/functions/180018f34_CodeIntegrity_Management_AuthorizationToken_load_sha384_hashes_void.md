# CodeIntegrity::Management::AuthorizationToken::load_sha384_hashes(void)

- ea: `0x180018f34`
- end: `0x1800190ff`
- name: `?load_sha384_hashes@AuthorizationToken@Management@CodeIntegrity@@AEAAXXZ`
- size: `459`
- prototype: `void __fastcall(CodeIntegrity::Management::AuthorizationToken *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018b50`

## callees

- `0x18000830c`
- `0x1800083d4`
- `0x18000d450`
- `0x180016b80`
- `0x180016ce0`
- `0x180018068`
- `0x180018290`
- `0x180018490`
- `0x180018f34`

## string_xrefs

- `0x18001905e`: `onecore\base\ci\management\dll\authorizationtoken.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CodeIntegrity::Management::AuthorizationToken::load_sha384_hashes(
        CodeIntegrity::Management::AuthorizationToken *this,
        __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // r8
  __int64 v5; // r10
  __int64 v6; // r11
  unsigned __int64 v7; // rcx
  unsigned int v8; // eax
  int v9; // [rsp+20h] [rbp-58h]
  __int128 v10; // [rsp+30h] [rbp-48h] BYREF
  __int64 v11; // [rsp+40h] [rbp-38h]
  __int64 v12; // [rsp+48h] [rbp-30h] BYREF
  __int64 v13; // [rsp+50h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v16; // [rsp+88h] [rbp+10h] BYREF

  LODWORD(v3) = 0;
  LODWORD(v16) = 0;
  if ( (unsigned int)CodeIntegrity::Management::detail::SbcpTokenView::get_dword_nothrow(
                       this,
                       a2,
                       L"SupplementalPolicyAuthorization",
                       L"CertTBSSha384HashCount",
                       (unsigned int *)&v16) != -2147023728 )
  {
    v10 = 0;
    v11 = 0;
    try
    {
      std::vector<std::array<unsigned char,48>>::_Construct_n<>();
      CodeIntegrity::Management::detail::SbcpTokenView::get_binary(
        (__int64)this,
        (__int64)&v12,
        -2130706432,
        L"SupplementalPolicyAuthorization",
        (PCWSTR)L"CertTBSSha384Hashes");
      v4 = v13;
      v5 = v12;
      if ( v13 - v12 == 48 * ((v13 - v12) / 0x30uLL) )
      {
        while ( 1 )
        {
          v6 = (unsigned int)v3;
          if ( (unsigned int)v3 >= (v4 - v5) / 0x30uLL )
            break;
          v3 = (unsigned int)(v3 + 1);
          v7 = 48 * v3;
          v8 = 48 * v3;
          if ( (unsigned __int64)(48 * v3) > 0xFFFFFFFF )
            v8 = -1;
          if ( v7 > 0xFFFFFFFF )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0xDA,
              (int)"onecore\\base\\ci\\management\\dll\\authorizationtoken.cpp",
              v7 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
              v9);
          std::copy<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>,std::_Array_iterator<unsigned char,64>>(
            &v16,
            (const void *)(v5 + v8 - 48),
            v5 + v8,
            (char *)(v10 + 48 * v6));
          v4 = v13;
          v5 = v12;
        }
        if ( (__int128 *)((char *)this + 160) != &v10 )
          std::vector<std::array<unsigned char,48>>::_Assign_counted_range<std::array<unsigned char,48> *>(
            (char *)this + 160,
            v10,
            0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v10 + 1) - v10) >> 4));
        std::vector<unsigned char>::_Tidy((__int64)&v12);
        std::vector<std::array<unsigned char,48>>::_Tidy(&v10);
      }
      else
      {
        *((_WORD *)this + 4) |= 0x1000u;
        std::vector<unsigned char>::_Tidy((__int64)&v12);
        std::vector<std::array<unsigned char,48>>::_Tidy(&v10);
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
0x180018f34  mov     rax, rsp
0x180018f37  mov     [rax+18h], rbx
0x180018f3b  mov     [rax+20h], rsi
0x180018f3f  mov     [rax+8], rcx
0x180018f43  push    rdi
0x180018f44  push    r14
0x180018f46  push    r15
0x180018f48  sub     rsp, 60h
0x180018f4c  mov     rbx, rcx
0x180018f4f  xor     edi, edi
0x180018f51  mov     [rax+10h], edi
0x180018f54  lea     rax, [rax+10h]
0x180018f58  mov     qword ptr [rsp+78h+var_58], rax; unsigned int *
0x180018f5d  lea     r9, aCerttbssha384h_0; "CertTBSSha384HashCount"
0x180018f64  lea     r8, SourceString; "SupplementalPolicyAuthorization"
0x180018f6b  call    ?get_dword_nothrow@SbcpTokenView@detail@Management@CodeIntegrity@@IEAAJIPEBG0PEAI@Z; CodeIntegrity::Management::detail::SbcpTokenView::get_dword_nothrow(uint,ushort const *,ushort const *,uint *)
0x180018f70  cmp     eax, 80070490h
0x180018f75  jnz     short loc_180018F7C
0x180018f77  jmp     loc_1800190E9
0x180018f7c  xorps   xmm0, xmm0
0x180018f7f  movdqu  [rsp+78h+var_48], xmm0
0x180018f85  mov     [rsp+78h+var_38], rdi
0x180018f8a  mov     edx, dword ptr [rsp+78h+arg_8]
0x180018f91  lea     rcx, [rsp+78h+var_48]
0x180018f96  call    ??$_Construct_n@$$V@?$vector@V?$array@E$0DA@@std@@V?$allocator@V?$array@E$0DA@@std@@@2@@std@@AEAAX_K@Z; std::vector<std::array<uchar,48>>::_Construct_n<>(unsigned __int64)
0x180018f9b  nop
0x180018f9c  lea     rax, aCerttbssha384h; "CertTBSSha384Hashes"
0x180018fa3  mov     qword ptr [rsp+78h+var_58], rax; int
0x180018fa8  lea     r9, SourceString; "SupplementalPolicyAuthorization"
0x180018faf  mov     r8d, 81000000h
0x180018fb5  lea     rdx, [rsp+78h+var_30]
0x180018fba  mov     rcx, rbx
0x180018fbd  call    ?get_binary@SbcpTokenView@detail@Management@CodeIntegrity@@IEAA?AV?$vector@EV?$allocator@E@std@@@std@@IPEBG0@Z; CodeIntegrity::Management::detail::SbcpTokenView::get_binary(uint,ushort const *,ushort const *)
0x180018fc2  nop
0x180018fc3  mov     r8, [rsp+78h+var_28]
0x180018fc8  mov     rcx, r8
0x180018fcb  mov     r10, [rsp+78h+var_30]
0x180018fd0  sub     rcx, r10
0x180018fd3  mov     r15, 0AAAAAAAAAAAAAAABh
0x180018fdd  mov     rax, r15
0x180018fe0  mul     rcx
0x180018fe3  shr     rdx, 5
0x180018fe7  lea     rax, [rdx+rdx*2]
0x180018feb  shl     rax, 4
0x180018fef  cmp     rcx, rax
0x180018ff2  jz      short loc_180019018
0x180018ff4  mov     eax, 1000h
0x180018ff9  or      [rbx+8], ax
0x180018ffd  lea     rcx, [rsp+78h+var_30]
0x180019002  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180019007  nop
0x180019008  lea     rcx, [rsp+78h+var_48]
0x18001900d  call    ?_Tidy@?$vector@V?$array@E$0DA@@std@@V?$allocator@V?$array@E$0DA@@std@@@2@@std@@AEAAXXZ; std::vector<std::array<uchar,48>>::_Tidy(void)
0x180019012  nop
0x180019013  jmp     loc_1800190E9
0x180019018  mov     r14d, 0FFFFFFFFh
0x18001901e  mov     r11d, edi
0x180019021  sub     r8, r10
0x180019024  mov     rax, r15
0x180019027  mul     r8
0x18001902a  shr     rdx, 5
0x18001902e  cmp     r11, rdx
0x180019031  jnb     short loc_1800190A5
0x180019033  inc     edi
0x180019035  lea     rcx, [rdi+rdi*2]
0x180019039  shl     rcx, 4
0x18001903d  cmp     rcx, r14
0x180019040  mov     eax, ecx
0x180019042  jbe     short loc_180019047
0x180019044  mov     eax, r14d
0x180019047  cmp     r14, rcx
0x18001904a  sbb     r9d, r9d
0x18001904d  and     r9d, 80070216h; char *
0x180019054  mov     rsi, [rsp+78h]
0x180019059  cmp     rcx, r14
0x18001905c  jbe     short loc_180019072
0x18001905e  lea     r8, aOnecoreBaseCiM_5; "onecore\\base\\ci\\management\\dll\\aut"...
0x180019065  mov     edx, 0DAh; void *
0x18001906a  mov     rcx, rsi; this
0x18001906d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180019072  mov     r8d, eax
0x180019075  add     r8, r10
0x180019078  lea     r9, [r11+r11*2]
0x18001907c  shl     r9, 4
0x180019080  add     r9, qword ptr [rsp+78h+var_48]
0x180019085  lea     rdx, [r8-30h]
0x180019089  lea     rcx, [rsp+78h+arg_8]
0x180019091  call    ??$copy@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@V?$_Array_iterator@E$0EA@@2@@std@@YA?AV?$_Array_iterator@E$0EA@@0@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@0@0V10@@Z; std::copy<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Array_iterator<uchar,64>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Array_iterator<uchar,64>)
0x180019096  mov     r8, [rsp+78h+var_28]
0x18001909b  mov     r10, [rsp+78h+var_30]
0x1800190a0  jmp     loc_18001901E
0x1800190a5  lea     rcx, [rbx+0A0h]
0x1800190ac  lea     rax, [rsp+78h+var_48]
0x1800190b1  cmp     rcx, rax
0x1800190b4  jz      short loc_1800190D1
0x1800190b6  mov     rdx, qword ptr [rsp+78h+var_48]
0x1800190bb  mov     r8, qword ptr [rsp+78h+var_48+8]
0x1800190c0  sub     r8, rdx
0x1800190c3  sar     r8, 4
0x1800190c7  imul    r8, r15
0x1800190cb  call    ??$_Assign_counted_range@PEAV?$array@E$0DA@@std@@@?$vector@V?$array@E$0DA@@std@@V?$allocator@V?$array@E$0DA@@std@@@2@@std@@AEAAXPEAV?$array@E$0DA@@1@_K@Z; std::vector<std::array<uchar,48>>::_Assign_counted_range<std::array<uchar,48> *>(std::array<uchar,48> *,unsigned __int64)
0x1800190d0  nop
0x1800190d1  lea     rcx, [rsp+78h+var_30]
0x1800190d6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800190db  nop
0x1800190dc  lea     rcx, [rsp+78h+var_48]
0x1800190e1  call    ?_Tidy@?$vector@V?$array@E$0DA@@std@@V?$allocator@V?$array@E$0DA@@std@@@2@@std@@AEAAXXZ; std::vector<std::array<uchar,48>>::_Tidy(void)
0x1800190e6  nop
0x1800190e7  jmp     short $+2
0x1800190e9  lea     r11, [rsp+78h+var_18]
0x1800190ee  mov     rbx, [r11+30h]
0x1800190f2  mov     rsi, [r11+38h]
0x1800190f6  mov     rsp, r11
0x1800190f9  pop     r15
0x1800190fb  pop     r14
0x1800190fd  pop     rdi
0x1800190fe  retn
```
