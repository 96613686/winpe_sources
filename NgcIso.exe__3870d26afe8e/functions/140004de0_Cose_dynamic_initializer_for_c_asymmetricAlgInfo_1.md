# Cose::_dynamic_initializer_for__c_asymmetricAlgInfo___1

- ea: `0x140004de0`
- end: `0x140005048`
- name: `Cose::_dynamic_initializer_for__c_asymmetricAlgInfo___1`
- size: `616`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140004de0`
- `0x14000c0d8`
- `0x14001194c`

## string_xrefs

- `0x140004e08`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140004e54`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140004eab`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140004eec`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140004f38`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140004f80`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140004fcc`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x140005014`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`

## pseudocode

```c
__int64 Cose::_dynamic_initializer_for__c_asymmetricAlgInfo___1()
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
  qword_14009C4B8 = (__int64)L"HKDF";
  qword_14009C4C0 = v0;
  qword_14009C4C8 = 913;
  v2 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA256", 7);
  if ( v2 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v3);
  qword_14009C4D0 = (__int64)L"SHA256";
  qword_14009C4D8 = v2;
  qword_14009C4E0 = 32;
  qword_14009C4E8 = -7;
  v4 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"ECDSA", 6);
  if ( v4 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v5);
  qword_14009C4F0 = (__int64)L"ECDSA";
  qword_14009C4F8 = v4;
  qword_14009C500 = 0;
  v6 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA256", 7);
  if ( v6 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v7);
  qword_14009C508 = (__int64)L"SHA256";
  qword_14009C510 = v6;
  qword_14009C518 = 32;
  qword_14009C520 = -35;
  v8 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"ECDSA", 6);
  if ( v8 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v9);
  qword_14009C528 = (__int64)L"ECDSA";
  qword_14009C530 = v8;
  qword_14009C538 = 0;
  v10 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA384", 7);
  if ( v10 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v11);
  qword_14009C540 = (__int64)L"SHA384";
  qword_14009C548 = v10;
  qword_14009C550 = 48;
  qword_14009C558 = -36;
  v12 = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"ECDSA", 6);
  if ( v12 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v13);
  qword_14009C560 = (__int64)L"ECDSA";
  qword_14009C568 = v12;
  qword_14009C570 = 0;
  result = std::_Traits_find_ch<std::char_traits<unsigned short>>(L"SHA512", 7);
  if ( result == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
      v15);
  qword_14009C578 = (__int64)L"SHA512";
  qword_14009C580 = result;
  qword_14009C588 = 64;
  return result;
}

```

## disassembly

```asm
0x140004de0  push    rbx
0x140004de2  push    rbp
0x140004de3  push    rsi
0x140004de4  push    rdi
0x140004de5  sub     rsp, 28h
0x140004de9  lea     rbx, aHkdf; "HKDF"
0x140004df0  mov     edx, 5
0x140004df5  mov     rcx, rbx
0x140004df8  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140004dfd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140004e01  jnz     short loc_140004E1A
0x140004e03  mov     rcx, [rsp+48h]; this
0x140004e08  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140004e0f  mov     edx, 0EBh; void *
0x140004e14  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140004e1a  mov     esi, 7
0x140004e1f  mov     cs:qword_14009C4B8, rbx
0x140004e26  lea     rdi, aSha256; "SHA256"
0x140004e2d  mov     cs:qword_14009C4C0, rax
0x140004e34  mov     edx, esi
0x140004e36  mov     cs:qword_14009C4C8, 391h
0x140004e41  mov     rcx, rdi
0x140004e44  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140004e49  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140004e4d  jnz     short loc_140004E66
0x140004e4f  mov     rcx, [rsp+48h]; this
0x140004e54  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140004e5b  mov     edx, 0EBh; void *
0x140004e60  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140004e66  mov     ebp, 6
0x140004e6b  mov     cs:qword_14009C4D0, rdi
0x140004e72  lea     rbx, aEcdsa; "ECDSA"
0x140004e79  mov     cs:qword_14009C4D8, rax
0x140004e80  mov     edx, ebp
0x140004e82  mov     cs:qword_14009C4E0, 20h ; ' '
0x140004e8d  mov     rcx, rbx
0x140004e90  mov     cs:qword_14009C4E8, 0FFFFFFFFFFFFFFF9h
0x140004e9b  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140004ea0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140004ea4  jnz     short loc_140004EBD
0x140004ea6  mov     rcx, [rsp+48h]; this
0x140004eab  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140004eb2  mov     edx, 0EBh; void *
0x140004eb7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140004ebd  mov     rdx, rsi
0x140004ec0  mov     cs:qword_14009C4F0, rbx
0x140004ec7  mov     rcx, rdi
0x140004eca  mov     cs:qword_14009C4F8, rax
0x140004ed1  mov     cs:qword_14009C500, 0
0x140004edc  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140004ee1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140004ee5  jnz     short loc_140004EFE
0x140004ee7  mov     rcx, [rsp+48h]; this
0x140004eec  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140004ef3  mov     edx, 0EBh; void *
0x140004ef8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140004efe  mov     rdx, rbp
0x140004f01  mov     cs:qword_14009C508, rdi
0x140004f08  mov     rcx, rbx
0x140004f0b  mov     cs:qword_14009C510, rax
0x140004f12  mov     cs:qword_14009C518, 20h ; ' '
0x140004f1d  mov     cs:qword_14009C520, 0FFFFFFFFFFFFFFDDh
0x140004f28  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140004f2d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140004f31  jnz     short loc_140004F4A
0x140004f33  mov     rcx, [rsp+48h]; this
0x140004f38  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140004f3f  mov     edx, 0EBh; void *
0x140004f44  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140004f4a  lea     rdi, aSha384; "SHA384"
0x140004f51  mov     cs:qword_14009C528, rbx
0x140004f58  mov     rcx, rdi
0x140004f5b  mov     cs:qword_14009C530, rax
0x140004f62  mov     rdx, rsi
0x140004f65  mov     cs:qword_14009C538, 0
0x140004f70  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140004f75  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140004f79  jnz     short loc_140004F92
0x140004f7b  mov     rcx, [rsp+48h]; this
0x140004f80  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140004f87  mov     edx, 0EBh; void *
0x140004f8c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140004f92  mov     rdx, rbp
0x140004f95  mov     cs:qword_14009C540, rdi
0x140004f9c  mov     rcx, rbx
0x140004f9f  mov     cs:qword_14009C548, rax
0x140004fa6  mov     cs:qword_14009C550, 30h ; '0'
0x140004fb1  mov     cs:qword_14009C558, 0FFFFFFFFFFFFFFDCh
0x140004fbc  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140004fc1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140004fc5  jnz     short loc_140004FDE
0x140004fc7  mov     rcx, [rsp+48h]; this
0x140004fcc  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140004fd3  mov     edx, 0EBh; void *
0x140004fd8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140004fde  mov     cs:qword_14009C560, rbx
0x140004fe5  mov     rdx, rsi
0x140004fe8  lea     rbx, aSha512; "SHA512"
0x140004fef  mov     cs:qword_14009C568, rax
0x140004ff6  mov     rcx, rbx
0x140004ff9  mov     cs:qword_14009C570, 0
0x140005004  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x140005009  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000500d  jnz     short loc_140005026
0x14000500f  mov     rcx, [rsp+48h]; this
0x140005014  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000501b  mov     edx, 0EBh; void *
0x140005020  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140005026  mov     cs:qword_14009C578, rbx
0x14000502d  mov     cs:qword_14009C580, rax
0x140005034  mov     cs:qword_14009C588, 40h ; '@'
0x14000503f  add     rsp, 28h
0x140005043  pop     rdi
0x140005044  pop     rsi
0x140005045  pop     rbp
0x140005046  pop     rbx
0x140005047  retn
```
