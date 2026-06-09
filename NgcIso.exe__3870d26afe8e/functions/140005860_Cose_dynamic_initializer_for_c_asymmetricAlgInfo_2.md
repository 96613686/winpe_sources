# Cose::_dynamic_initializer_for__c_asymmetricAlgInfo___2

- ea: `0x140005860`
- end: `0x140005ac8`
- name: `Cose::_dynamic_initializer_for__c_asymmetricAlgInfo___2`
- size: `616`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140005860`
- `0x14000c0d8`
- `0x14001194c`

## string_xrefs

- `0x140005888`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x1400058d4`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x14000592b`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x14000596c`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x1400059b8`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140005a00`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140005a4c`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140005a94`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`

## pseudocode

```c
__int64 Cose::_dynamic_initializer_for__c_asymmetricAlgInfo___2()
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
  qword_14009CBC8 = (__int64)L"HKDF";
  qword_14009CBD0 = v0;
  qword_14009CBD8 = 913;
  v2 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA256", 7);
  if ( v2 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v3);
  qword_14009CBE0 = (__int64)L"SHA256";
  qword_14009CBE8 = v2;
  qword_14009CBF0 = 32;
  qword_14009CBF8 = -7;
  v4 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"ECDSA", 6);
  if ( v4 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v5);
  qword_14009CC00 = (__int64)L"ECDSA";
  qword_14009CC08 = v4;
  qword_14009CC10 = 0;
  v6 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA256", 7);
  if ( v6 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v7);
  qword_14009CC18 = (__int64)L"SHA256";
  qword_14009CC20 = v6;
  qword_14009CC28 = 32;
  qword_14009CC30 = -35;
  v8 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"ECDSA", 6);
  if ( v8 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v9);
  qword_14009CC38 = (__int64)L"ECDSA";
  qword_14009CC40 = v8;
  qword_14009CC48 = 0;
  v10 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA384", 7);
  if ( v10 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v11);
  qword_14009CC50 = (__int64)L"SHA384";
  qword_14009CC58 = v10;
  qword_14009CC60 = 48;
  qword_14009CC68 = -36;
  v12 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"ECDSA", 6);
  if ( v12 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v13);
  qword_14009CC70 = (__int64)L"ECDSA";
  qword_14009CC78 = v12;
  qword_14009CC80 = 0;
  result = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA512", 7);
  if ( result == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v15);
  qword_14009CC88 = (__int64)L"SHA512";
  qword_14009CC90 = result;
  qword_14009CC98 = 64;
  return result;
}

```

## disassembly

```asm
0x140005860  push    rbx
0x140005862  push    rbp
0x140005863  push    rsi
0x140005864  push    rdi
0x140005865  sub     rsp, 28h
0x140005869  lea     rbx, aHkdf; "HKDF"
0x140005870  mov     edx, 5
0x140005875  mov     rcx, rbx
0x140005878  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x14000587d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140005881  jnz     short loc_14000589A
0x140005883  mov     rcx, [rsp+48h]; this
0x140005888  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000588f  mov     edx, 0EBh; void *
0x140005894  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000589a  mov     esi, 7
0x14000589f  mov     cs:qword_14009CBC8, rbx
0x1400058a6  lea     rdi, aSha256; "SHA256"
0x1400058ad  mov     cs:qword_14009CBD0, rax
0x1400058b4  mov     edx, esi
0x1400058b6  mov     cs:qword_14009CBD8, 391h
0x1400058c1  mov     rcx, rdi
0x1400058c4  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x1400058c9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400058cd  jnz     short loc_1400058E6
0x1400058cf  mov     rcx, [rsp+48h]; this
0x1400058d4  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400058db  mov     edx, 0EBh; void *
0x1400058e0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400058e6  mov     ebp, 6
0x1400058eb  mov     cs:qword_14009CBE0, rdi
0x1400058f2  lea     rbx, aEcdsa; "ECDSA"
0x1400058f9  mov     cs:qword_14009CBE8, rax
0x140005900  mov     edx, ebp
0x140005902  mov     cs:qword_14009CBF0, 20h ; ' '
0x14000590d  mov     rcx, rbx
0x140005910  mov     cs:qword_14009CBF8, 0FFFFFFFFFFFFFFF9h
0x14000591b  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140005920  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140005924  jnz     short loc_14000593D
0x140005926  mov     rcx, [rsp+48h]; this
0x14000592b  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005932  mov     edx, 0EBh; void *
0x140005937  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000593d  mov     rdx, rsi
0x140005940  mov     cs:qword_14009CC00, rbx
0x140005947  mov     rcx, rdi
0x14000594a  mov     cs:qword_14009CC08, rax
0x140005951  mov     cs:qword_14009CC10, 0
0x14000595c  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140005961  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140005965  jnz     short loc_14000597E
0x140005967  mov     rcx, [rsp+48h]; this
0x14000596c  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005973  mov     edx, 0EBh; void *
0x140005978  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000597e  mov     rdx, rbp
0x140005981  mov     cs:qword_14009CC18, rdi
0x140005988  mov     rcx, rbx
0x14000598b  mov     cs:qword_14009CC20, rax
0x140005992  mov     cs:qword_14009CC28, 20h ; ' '
0x14000599d  mov     cs:qword_14009CC30, 0FFFFFFFFFFFFFFDDh
0x1400059a8  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x1400059ad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400059b1  jnz     short loc_1400059CA
0x1400059b3  mov     rcx, [rsp+48h]; this
0x1400059b8  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400059bf  mov     edx, 0EBh; void *
0x1400059c4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400059ca  lea     rdi, aSha384; "SHA384"
0x1400059d1  mov     cs:qword_14009CC38, rbx
0x1400059d8  mov     rcx, rdi
0x1400059db  mov     cs:qword_14009CC40, rax
0x1400059e2  mov     rdx, rsi
0x1400059e5  mov     cs:qword_14009CC48, 0
0x1400059f0  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x1400059f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400059f9  jnz     short loc_140005A12
0x1400059fb  mov     rcx, [rsp+48h]; this
0x140005a00  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005a07  mov     edx, 0EBh; void *
0x140005a0c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140005a12  mov     rdx, rbp
0x140005a15  mov     cs:qword_14009CC50, rdi
0x140005a1c  mov     rcx, rbx
0x140005a1f  mov     cs:qword_14009CC58, rax
0x140005a26  mov     cs:qword_14009CC60, 30h ; '0'
0x140005a31  mov     cs:qword_14009CC68, 0FFFFFFFFFFFFFFDCh
0x140005a3c  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140005a41  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140005a45  jnz     short loc_140005A5E
0x140005a47  mov     rcx, [rsp+48h]; this
0x140005a4c  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005a53  mov     edx, 0EBh; void *
0x140005a58  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140005a5e  mov     cs:qword_14009CC70, rbx
0x140005a65  mov     rdx, rsi
0x140005a68  lea     rbx, aSha512; "SHA512"
0x140005a6f  mov     cs:qword_14009CC78, rax
0x140005a76  mov     rcx, rbx
0x140005a79  mov     cs:qword_14009CC80, 0
0x140005a84  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140005a89  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140005a8d  jnz     short loc_140005AA6
0x140005a8f  mov     rcx, [rsp+48h]; this
0x140005a94  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005a9b  mov     edx, 0EBh; void *
0x140005aa0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140005aa6  mov     cs:qword_14009CC88, rbx
0x140005aad  mov     cs:qword_14009CC90, rax
0x140005ab4  mov     cs:qword_14009CC98, 40h ; '@'
0x140005abf  add     rsp, 28h
0x140005ac3  pop     rdi
0x140005ac4  pop     rsi
0x140005ac5  pop     rbp
0x140005ac6  pop     rbx
0x140005ac7  retn
```
