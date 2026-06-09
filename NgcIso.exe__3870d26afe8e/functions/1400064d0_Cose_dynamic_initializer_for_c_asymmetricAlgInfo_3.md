# Cose::_dynamic_initializer_for__c_asymmetricAlgInfo___3

- ea: `0x1400064d0`
- end: `0x140006738`
- name: `Cose::_dynamic_initializer_for__c_asymmetricAlgInfo___3`
- size: `616`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400064d0`
- `0x14000c0d8`
- `0x14001194c`

## string_xrefs

- `0x1400064f8`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140006544`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x14000659b`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x1400065dc`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140006628`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140006670`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x1400066bc`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140006704`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`

## pseudocode

```c
__int64 Cose::_dynamic_initializer_for__c_asymmetricAlgInfo___3()
{
  __int64 v0; // rax
  const char *v1; // r9
  __int64 v2; // rax
  const char *v3; // r9
  __int64 v4; // rax
  const char *v5; // r9
  __int64 v6; // rax
  const char *v7; // r9
  __int64 v8; // rax
  const char *v9; // r9
  __int64 v10; // rax
  const char *v11; // r9
  __int64 v12; // rax
  const char *v13; // r9
  __int64 result; // rax
  const char *v15; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v0 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"HKDF", 5);
  if ( v0 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v1);
  qword_14009D1F8 = (__int64)L"HKDF";
  qword_14009D200 = v0;
  qword_14009D208 = 913;
  v2 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA256", 7);
  if ( v2 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v3);
  qword_14009D210 = (__int64)L"SHA256";
  qword_14009D218 = v2;
  qword_14009D220 = 32;
  qword_14009D228 = -7;
  v4 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"ECDSA", 6);
  if ( v4 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v5);
  qword_14009D230 = (__int64)L"ECDSA";
  qword_14009D238 = v4;
  qword_14009D240 = 0;
  v6 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA256", 7);
  if ( v6 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v7);
  qword_14009D248 = (__int64)L"SHA256";
  qword_14009D250 = v6;
  qword_14009D258 = 32;
  qword_14009D260 = -35;
  v8 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"ECDSA", 6);
  if ( v8 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v9);
  qword_14009D268 = (__int64)L"ECDSA";
  qword_14009D270 = v8;
  qword_14009D278 = 0;
  v10 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA384", 7);
  if ( v10 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v11);
  qword_14009D280 = (__int64)L"SHA384";
  qword_14009D288 = v10;
  qword_14009D290 = 48;
  qword_14009D298 = -36;
  v12 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"ECDSA", 6);
  if ( v12 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v13);
  qword_14009D2A0 = (__int64)L"ECDSA";
  qword_14009D2A8 = v12;
  qword_14009D2B0 = 0;
  result = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA512", 7);
  if ( result == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v15);
  qword_14009D2B8 = (__int64)L"SHA512";
  qword_14009D2C0 = result;
  qword_14009D2C8 = 64;
  return result;
}

```

## disassembly

```asm
0x1400064d0  push    rbx
0x1400064d2  push    rbp
0x1400064d3  push    rsi
0x1400064d4  push    rdi
0x1400064d5  sub     rsp, 28h
0x1400064d9  lea     rbx, aHkdf; "HKDF"
0x1400064e0  mov     edx, 5
0x1400064e5  mov     rcx, rbx
0x1400064e8  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x1400064ed  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400064f1  jnz     short loc_14000650A
0x1400064f3  mov     rcx, [rsp+48h]; this
0x1400064f8  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400064ff  mov     edx, 0EBh; void *
0x140006504  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000650a  mov     esi, 7
0x14000650f  mov     cs:qword_14009D1F8, rbx
0x140006516  lea     rdi, aSha256; "SHA256"
0x14000651d  mov     cs:qword_14009D200, rax
0x140006524  mov     edx, esi
0x140006526  mov     cs:qword_14009D208, 391h
0x140006531  mov     rcx, rdi
0x140006534  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140006539  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000653d  jnz     short loc_140006556
0x14000653f  mov     rcx, [rsp+48h]; this
0x140006544  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000654b  mov     edx, 0EBh; void *
0x140006550  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140006556  mov     ebp, 6
0x14000655b  mov     cs:qword_14009D210, rdi
0x140006562  lea     rbx, aEcdsa; "ECDSA"
0x140006569  mov     cs:qword_14009D218, rax
0x140006570  mov     edx, ebp
0x140006572  mov     cs:qword_14009D220, 20h ; ' '
0x14000657d  mov     rcx, rbx
0x140006580  mov     cs:qword_14009D228, 0FFFFFFFFFFFFFFF9h
0x14000658b  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140006590  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140006594  jnz     short loc_1400065AD
0x140006596  mov     rcx, [rsp+48h]; this
0x14000659b  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400065a2  mov     edx, 0EBh; void *
0x1400065a7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400065ad  mov     rdx, rsi
0x1400065b0  mov     cs:qword_14009D230, rbx
0x1400065b7  mov     rcx, rdi
0x1400065ba  mov     cs:qword_14009D238, rax
0x1400065c1  mov     cs:qword_14009D240, 0
0x1400065cc  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x1400065d1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400065d5  jnz     short loc_1400065EE
0x1400065d7  mov     rcx, [rsp+48h]; this
0x1400065dc  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400065e3  mov     edx, 0EBh; void *
0x1400065e8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400065ee  mov     rdx, rbp
0x1400065f1  mov     cs:qword_14009D248, rdi
0x1400065f8  mov     rcx, rbx
0x1400065fb  mov     cs:qword_14009D250, rax
0x140006602  mov     cs:qword_14009D258, 20h ; ' '
0x14000660d  mov     cs:qword_14009D260, 0FFFFFFFFFFFFFFDDh
0x140006618  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x14000661d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140006621  jnz     short loc_14000663A
0x140006623  mov     rcx, [rsp+48h]; this
0x140006628  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000662f  mov     edx, 0EBh; void *
0x140006634  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000663a  lea     rdi, aSha384; "SHA384"
0x140006641  mov     cs:qword_14009D268, rbx
0x140006648  mov     rcx, rdi
0x14000664b  mov     cs:qword_14009D270, rax
0x140006652  mov     rdx, rsi
0x140006655  mov     cs:qword_14009D278, 0
0x140006660  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140006665  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140006669  jnz     short loc_140006682
0x14000666b  mov     rcx, [rsp+48h]; this
0x140006670  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140006677  mov     edx, 0EBh; void *
0x14000667c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140006682  mov     rdx, rbp
0x140006685  mov     cs:qword_14009D280, rdi
0x14000668c  mov     rcx, rbx
0x14000668f  mov     cs:qword_14009D288, rax
0x140006696  mov     cs:qword_14009D290, 30h ; '0'
0x1400066a1  mov     cs:qword_14009D298, 0FFFFFFFFFFFFFFDCh
0x1400066ac  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x1400066b1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400066b5  jnz     short loc_1400066CE
0x1400066b7  mov     rcx, [rsp+48h]; this
0x1400066bc  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400066c3  mov     edx, 0EBh; void *
0x1400066c8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400066ce  mov     cs:qword_14009D2A0, rbx
0x1400066d5  mov     rdx, rsi
0x1400066d8  lea     rbx, aSha512; "SHA512"
0x1400066df  mov     cs:qword_14009D2A8, rax
0x1400066e6  mov     rcx, rbx
0x1400066e9  mov     cs:qword_14009D2B0, 0
0x1400066f4  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x1400066f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400066fd  jnz     short loc_140006716
0x1400066ff  mov     rcx, [rsp+48h]; this
0x140006704  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000670b  mov     edx, 0EBh; void *
0x140006710  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140006716  mov     cs:qword_14009D2B8, rbx
0x14000671d  mov     cs:qword_14009D2C0, rax
0x140006724  mov     cs:qword_14009D2C8, 40h ; '@'
0x14000672f  add     rsp, 28h
0x140006733  pop     rdi
0x140006734  pop     rsi
0x140006735  pop     rbp
0x140006736  pop     rbx
0x140006737  retn
```
