# Cose::_dynamic_initializer_for__c_asymmetricAlgInfo___0

- ea: `0x1400039e0`
- end: `0x140003c48`
- name: `Cose::_dynamic_initializer_for__c_asymmetricAlgInfo___0`
- size: `616`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400039e0`
- `0x14000c0d8`
- `0x14001194c`

## string_xrefs

- `0x140003a08`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140003a54`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140003aab`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140003aec`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140003b38`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140003b80`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140003bcc`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140003c14`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`

## pseudocode

```c
__int64 Cose::_dynamic_initializer_for__c_asymmetricAlgInfo___0()
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
  qword_14009C908 = (__int64)L"HKDF";
  qword_14009C910 = v0;
  qword_14009C918 = 913;
  v2 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA256", 7);
  if ( v2 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v3);
  qword_14009C920 = (__int64)L"SHA256";
  qword_14009C928 = v2;
  qword_14009C930 = 32;
  qword_14009C938 = -7;
  v4 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"ECDSA", 6);
  if ( v4 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v5);
  qword_14009C940 = (__int64)L"ECDSA";
  qword_14009C948 = v4;
  qword_14009C950 = 0;
  v6 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA256", 7);
  if ( v6 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v7);
  qword_14009C958 = (__int64)L"SHA256";
  qword_14009C960 = v6;
  qword_14009C968 = 32;
  qword_14009C970 = -35;
  v8 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"ECDSA", 6);
  if ( v8 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v9);
  qword_14009C978 = (__int64)L"ECDSA";
  qword_14009C980 = v8;
  qword_14009C988 = 0;
  v10 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA384", 7);
  if ( v10 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v11);
  qword_14009C990 = (__int64)L"SHA384";
  qword_14009C998 = v10;
  qword_14009C9A0 = 48;
  qword_14009C9A8 = -36;
  v12 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"ECDSA", 6);
  if ( v12 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v13);
  qword_14009C9B0 = (__int64)L"ECDSA";
  qword_14009C9B8 = v12;
  qword_14009C9C0 = 0;
  result = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA512", 7);
  if ( result == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v15);
  qword_14009C9C8 = (__int64)L"SHA512";
  qword_14009C9D0 = result;
  qword_14009C9D8 = 64;
  return result;
}

```

## disassembly

```asm
0x1400039e0  push    rbx
0x1400039e2  push    rbp
0x1400039e3  push    rsi
0x1400039e4  push    rdi
0x1400039e5  sub     rsp, 28h
0x1400039e9  lea     rbx, aHkdf; "HKDF"
0x1400039f0  mov     edx, 5
0x1400039f5  mov     rcx, rbx
0x1400039f8  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x1400039fd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140003a01  jnz     short loc_140003A1A
0x140003a03  mov     rcx, [rsp+48h]; this
0x140003a08  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003a0f  mov     edx, 0EBh; void *
0x140003a14  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140003a1a  mov     esi, 7
0x140003a1f  mov     cs:qword_14009C908, rbx
0x140003a26  lea     rdi, aSha256; "SHA256"
0x140003a2d  mov     cs:qword_14009C910, rax
0x140003a34  mov     edx, esi
0x140003a36  mov     cs:qword_14009C918, 391h
0x140003a41  mov     rcx, rdi
0x140003a44  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140003a49  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140003a4d  jnz     short loc_140003A66
0x140003a4f  mov     rcx, [rsp+48h]; this
0x140003a54  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003a5b  mov     edx, 0EBh; void *
0x140003a60  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140003a66  mov     ebp, 6
0x140003a6b  mov     cs:qword_14009C920, rdi
0x140003a72  lea     rbx, aEcdsa; "ECDSA"
0x140003a79  mov     cs:qword_14009C928, rax
0x140003a80  mov     edx, ebp
0x140003a82  mov     cs:qword_14009C930, 20h ; ' '
0x140003a8d  mov     rcx, rbx
0x140003a90  mov     cs:qword_14009C938, 0FFFFFFFFFFFFFFF9h
0x140003a9b  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140003aa0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140003aa4  jnz     short loc_140003ABD
0x140003aa6  mov     rcx, [rsp+48h]; this
0x140003aab  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003ab2  mov     edx, 0EBh; void *
0x140003ab7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140003abd  mov     rdx, rsi
0x140003ac0  mov     cs:qword_14009C940, rbx
0x140003ac7  mov     rcx, rdi
0x140003aca  mov     cs:qword_14009C948, rax
0x140003ad1  mov     cs:qword_14009C950, 0
0x140003adc  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140003ae1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140003ae5  jnz     short loc_140003AFE
0x140003ae7  mov     rcx, [rsp+48h]; this
0x140003aec  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003af3  mov     edx, 0EBh; void *
0x140003af8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140003afe  mov     rdx, rbp
0x140003b01  mov     cs:qword_14009C958, rdi
0x140003b08  mov     rcx, rbx
0x140003b0b  mov     cs:qword_14009C960, rax
0x140003b12  mov     cs:qword_14009C968, 20h ; ' '
0x140003b1d  mov     cs:qword_14009C970, 0FFFFFFFFFFFFFFDDh
0x140003b28  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140003b2d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140003b31  jnz     short loc_140003B4A
0x140003b33  mov     rcx, [rsp+48h]; this
0x140003b38  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003b3f  mov     edx, 0EBh; void *
0x140003b44  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140003b4a  lea     rdi, aSha384; "SHA384"
0x140003b51  mov     cs:qword_14009C978, rbx
0x140003b58  mov     rcx, rdi
0x140003b5b  mov     cs:qword_14009C980, rax
0x140003b62  mov     rdx, rsi
0x140003b65  mov     cs:qword_14009C988, 0
0x140003b70  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140003b75  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140003b79  jnz     short loc_140003B92
0x140003b7b  mov     rcx, [rsp+48h]; this
0x140003b80  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003b87  mov     edx, 0EBh; void *
0x140003b8c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140003b92  mov     rdx, rbp
0x140003b95  mov     cs:qword_14009C990, rdi
0x140003b9c  mov     rcx, rbx
0x140003b9f  mov     cs:qword_14009C998, rax
0x140003ba6  mov     cs:qword_14009C9A0, 30h ; '0'
0x140003bb1  mov     cs:qword_14009C9A8, 0FFFFFFFFFFFFFFDCh
0x140003bbc  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140003bc1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140003bc5  jnz     short loc_140003BDE
0x140003bc7  mov     rcx, [rsp+48h]; this
0x140003bcc  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003bd3  mov     edx, 0EBh; void *
0x140003bd8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140003bde  mov     cs:qword_14009C9B0, rbx
0x140003be5  mov     rdx, rsi
0x140003be8  lea     rbx, aSha512; "SHA512"
0x140003bef  mov     cs:qword_14009C9B8, rax
0x140003bf6  mov     rcx, rbx
0x140003bf9  mov     cs:qword_14009C9C0, 0
0x140003c04  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140003c09  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140003c0d  jnz     short loc_140003C26
0x140003c0f  mov     rcx, [rsp+48h]; this
0x140003c14  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003c1b  mov     edx, 0EBh; void *
0x140003c20  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140003c26  mov     cs:qword_14009C9C8, rbx
0x140003c2d  mov     cs:qword_14009C9D0, rax
0x140003c34  mov     cs:qword_14009C9D8, 40h ; '@'
0x140003c3f  add     rsp, 28h
0x140003c43  pop     rdi
0x140003c44  pop     rsi
0x140003c45  pop     rbp
0x140003c46  pop     rbx
0x140003c47  retn
```
