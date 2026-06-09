# Cose::_dynamic_initializer_for__c_asymmetricAlgInfo__

- ea: `0x140003770`
- end: `0x1400039d8`
- name: `Cose::_dynamic_initializer_for__c_asymmetricAlgInfo__`
- size: `616`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140003770`
- `0x14000c0d8`
- `0x14001194c`

## string_xrefs

- `0x140003798`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x1400037e4`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x14000383b`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x14000387c`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x1400038c8`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140003910`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x14000395c`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x1400039a4`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`

## pseudocode

```c
__int64 Cose::_dynamic_initializer_for__c_asymmetricAlgInfo__()
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
  qword_14009BEC8 = (__int64)L"HKDF";
  qword_14009BED0 = v0;
  qword_14009BED8 = 913;
  v2 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA256", 7);
  if ( v2 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v3);
  qword_14009BEE0 = (__int64)L"SHA256";
  qword_14009BEE8 = v2;
  qword_14009BEF0 = 32;
  qword_14009BEF8 = -7;
  v4 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"ECDSA", 6);
  if ( v4 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v5);
  qword_14009BF00 = (__int64)L"ECDSA";
  qword_14009BF08 = v4;
  qword_14009BF10 = 0;
  v6 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA256", 7);
  if ( v6 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v7);
  qword_14009BF18 = (__int64)L"SHA256";
  qword_14009BF20 = v6;
  qword_14009BF28 = 32;
  qword_14009BF30 = -35;
  v8 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"ECDSA", 6);
  if ( v8 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v9);
  qword_14009BF38 = (__int64)L"ECDSA";
  qword_14009BF40 = v8;
  qword_14009BF48 = 0;
  v10 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA384", 7);
  if ( v10 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v11);
  qword_14009BF50 = (__int64)L"SHA384";
  qword_14009BF58 = v10;
  qword_14009BF60 = 48;
  qword_14009BF68 = -36;
  v12 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"ECDSA", 6);
  if ( v12 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v13);
  qword_14009BF70 = (__int64)L"ECDSA";
  qword_14009BF78 = v12;
  qword_14009BF80 = 0;
  result = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA512", 7);
  if ( result == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v15);
  qword_14009BF88 = (__int64)L"SHA512";
  qword_14009BF90 = result;
  qword_14009BF98 = 64;
  return result;
}

```

## disassembly

```asm
0x140003770  push    rbx
0x140003772  push    rbp
0x140003773  push    rsi
0x140003774  push    rdi
0x140003775  sub     rsp, 28h
0x140003779  lea     rbx, aHkdf; "HKDF"
0x140003780  mov     edx, 5
0x140003785  mov     rcx, rbx
0x140003788  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x14000378d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140003791  jnz     short loc_1400037AA
0x140003793  mov     rcx, [rsp+48h]; this
0x140003798  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000379f  mov     edx, 0EBh; void *
0x1400037a4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400037aa  mov     esi, 7
0x1400037af  mov     cs:qword_14009BEC8, rbx
0x1400037b6  lea     rdi, aSha256; "SHA256"
0x1400037bd  mov     cs:qword_14009BED0, rax
0x1400037c4  mov     edx, esi
0x1400037c6  mov     cs:qword_14009BED8, 391h
0x1400037d1  mov     rcx, rdi
0x1400037d4  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x1400037d9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400037dd  jnz     short loc_1400037F6
0x1400037df  mov     rcx, [rsp+48h]; this
0x1400037e4  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400037eb  mov     edx, 0EBh; void *
0x1400037f0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400037f6  mov     ebp, 6
0x1400037fb  mov     cs:qword_14009BEE0, rdi
0x140003802  lea     rbx, aEcdsa; "ECDSA"
0x140003809  mov     cs:qword_14009BEE8, rax
0x140003810  mov     edx, ebp
0x140003812  mov     cs:qword_14009BEF0, 20h ; ' '
0x14000381d  mov     rcx, rbx
0x140003820  mov     cs:qword_14009BEF8, 0FFFFFFFFFFFFFFF9h
0x14000382b  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140003830  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140003834  jnz     short loc_14000384D
0x140003836  mov     rcx, [rsp+48h]; this
0x14000383b  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003842  mov     edx, 0EBh; void *
0x140003847  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000384d  mov     rdx, rsi
0x140003850  mov     cs:qword_14009BF00, rbx
0x140003857  mov     rcx, rdi
0x14000385a  mov     cs:qword_14009BF08, rax
0x140003861  mov     cs:qword_14009BF10, 0
0x14000386c  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140003871  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140003875  jnz     short loc_14000388E
0x140003877  mov     rcx, [rsp+48h]; this
0x14000387c  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003883  mov     edx, 0EBh; void *
0x140003888  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000388e  mov     rdx, rbp
0x140003891  mov     cs:qword_14009BF18, rdi
0x140003898  mov     rcx, rbx
0x14000389b  mov     cs:qword_14009BF20, rax
0x1400038a2  mov     cs:qword_14009BF28, 20h ; ' '
0x1400038ad  mov     cs:qword_14009BF30, 0FFFFFFFFFFFFFFDDh
0x1400038b8  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x1400038bd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400038c1  jnz     short loc_1400038DA
0x1400038c3  mov     rcx, [rsp+48h]; this
0x1400038c8  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400038cf  mov     edx, 0EBh; void *
0x1400038d4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400038da  lea     rdi, aSha384; "SHA384"
0x1400038e1  mov     cs:qword_14009BF38, rbx
0x1400038e8  mov     rcx, rdi
0x1400038eb  mov     cs:qword_14009BF40, rax
0x1400038f2  mov     rdx, rsi
0x1400038f5  mov     cs:qword_14009BF48, 0
0x140003900  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140003905  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140003909  jnz     short loc_140003922
0x14000390b  mov     rcx, [rsp+48h]; this
0x140003910  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003917  mov     edx, 0EBh; void *
0x14000391c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140003922  mov     rdx, rbp
0x140003925  mov     cs:qword_14009BF50, rdi
0x14000392c  mov     rcx, rbx
0x14000392f  mov     cs:qword_14009BF58, rax
0x140003936  mov     cs:qword_14009BF60, 30h ; '0'
0x140003941  mov     cs:qword_14009BF68, 0FFFFFFFFFFFFFFDCh
0x14000394c  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140003951  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140003955  jnz     short loc_14000396E
0x140003957  mov     rcx, [rsp+48h]; this
0x14000395c  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003963  mov     edx, 0EBh; void *
0x140003968  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000396e  mov     cs:qword_14009BF70, rbx
0x140003975  mov     rdx, rsi
0x140003978  lea     rbx, aSha512; "SHA512"
0x14000397f  mov     cs:qword_14009BF78, rax
0x140003986  mov     rcx, rbx
0x140003989  mov     cs:qword_14009BF80, 0
0x140003994  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140003999  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000399d  jnz     short loc_1400039B6
0x14000399f  mov     rcx, [rsp+48h]; this
0x1400039a4  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400039ab  mov     edx, 0EBh; void *
0x1400039b0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400039b6  mov     cs:qword_14009BF88, rbx
0x1400039bd  mov     cs:qword_14009BF90, rax
0x1400039c4  mov     cs:qword_14009BF98, 40h ; '@'
0x1400039cf  add     rsp, 28h
0x1400039d3  pop     rdi
0x1400039d4  pop     rsi
0x1400039d5  pop     rbp
0x1400039d6  pop     rbx
0x1400039d7  retn
```
