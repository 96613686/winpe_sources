# IdentityParser::CEscapedCharacterReader::ReadCharacter(bool &)

- ea: `0x180096b5c`
- end: `0x180096dd4`
- name: `?ReadCharacter@CEscapedCharacterReader@IdentityParser@@AEAAJAEA_N@Z`
- size: `632`
- prototype: `__int64 __fastcall(IdentityParser::CEscapedCharacterReader *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180096044`

## callees

- `0x18000b600`
- `0x18001f5d4`
- `0x18001fd10`
- `0x1800293a0`
- `0x180096b5c`

## string_xrefs

- `0x180096bcd`: `IdentityParser::CEscapedCharacterReader::ReadCharacter`
- `0x180096cff`: `IdentityParser::CEscapedCharacterReader::ReadCharacter`
- `0x180096d1f`: `IdentityParser::CEscapedCharacterReader::ReadCharacter`
- `0x180096d68`: `IdentityParser::CEscapedCharacterReader::ReadCharacter`
- `0x180096d2a`: `(chTemp & 0xf0000000) == 0`
- `0x180096d73`: `(chTemp <= (0x0010FFFF)) && ((chTemp < 0xd800) || (chTemp > 0xdfff))`

## pseudocode

```c
__int64 __fastcall IdentityParser::CEscapedCharacterReader::ReadCharacter(
        IdentityParser::CEscapedCharacterReader *this,
        bool *a2)
{
  __int64 v3; // r8
  __int64 v5; // rdx
  __int64 v6; // rax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v11; // rax
  unsigned int i; // ebx
  unsigned __int64 v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  __int64 v20; // rax
  int v21; // ecx
  const char *v22; // rax
  const char *v23; // [rsp+20h] [rbp-30h] BYREF
  const char *v24; // [rsp+28h] [rbp-28h]
  __int64 v25; // [rsp+30h] [rbp-20h]
  const char *v26; // [rsp+38h] [rbp-18h]
  int v27; // [rsp+40h] [rbp-10h] BYREF

  *a2 = 0;
  v3 = *((_QWORD *)this + 2);
  v5 = *((_QWORD *)this + 1);
  v27 = 0;
  v6 = RtlDecodeUtf16LE(&v23, v5, v3);
  v7 = *(_DWORD *)v6;
  v8 = *(_QWORD *)(v6 + 8);
  if ( *(_DWORD *)v6 == -1 )
  {
    if ( (int)v8 < 0 )
    {
      v25 = 148;
LABEL_4:
      v9 = (unsigned int)v8;
      v23 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
      v24 = "IdentityParser::CEscapedCharacterReader::ReadCharacter";
      v26 = "__rv.UcsCharacter != (0xffffffff)";
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
               &v27,
               &v23,
               v9);
    }
    goto LABEL_45;
  }
  *((_QWORD *)this + 1) = v8;
  if ( v7 != 92 )
  {
LABEL_44:
    *(_DWORD *)this = v7;
    return 0;
  }
  v11 = RtlDecodeUtf16LE(&v23, v8, *((_QWORD *)this + 2));
  i = *(_DWORD *)v11;
  v8 = *(_QWORD *)(v11 + 8);
  if ( *(_DWORD *)v11 == -1 )
  {
    if ( (int)v8 < 0 )
    {
      v25 = 152;
      goto LABEL_4;
    }
LABEL_45:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x180096DD3LL);
  }
  *((_QWORD *)this + 1) = v8;
  if ( i <= 0x5C )
  {
    v13 = i - 34;
    if ( (unsigned int)v13 <= 0x3A )
    {
      v14 = 0x400000008002421LL;
      if ( _bittest64(&v14, v13) )
        goto LABEL_43;
    }
LABEL_18:
    v25 = 199;
    goto LABEL_33;
  }
  v15 = i - 110;
  if ( !v15 )
  {
    i = 10;
    goto LABEL_43;
  }
  v16 = v15 - 4;
  if ( !v16 )
  {
    i = 13;
    goto LABEL_43;
  }
  v17 = v16 - 2;
  if ( !v17 )
  {
    i = 9;
LABEL_43:
    *a2 = 1;
    v7 = i | 0x80000000;
    goto LABEL_44;
  }
  if ( v17 != 1 )
    goto LABEL_18;
  for ( i = 0; ; i = v21 + v19 )
  {
    v20 = RtlDecodeUtf16LE(&v23, v8, *((_QWORD *)this + 2));
    v21 = *(_DWORD *)v20;
    v8 = *(_QWORD *)(v20 + 8);
    if ( *(_DWORD *)v20 == -1 )
    {
      if ( (int)v8 < 0 )
      {
        v25 = 175;
        goto LABEL_4;
      }
      goto LABEL_45;
    }
    *((_QWORD *)this + 1) = v8;
    if ( v21 == 59 )
    {
      if ( i < 0x110000 && i - 55296 > 0x7FF )
        goto LABEL_43;
      v25 = 194;
      v23 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
      v24 = "IdentityParser::CEscapedCharacterReader::ReadCharacter";
      v22 = "(chTemp <= (0x0010FFFF)) && ((chTemp < 0xd800) || (chTemp > 0xdfff))";
LABEL_35:
      v26 = v22;
      goto LABEL_36;
    }
    if ( (i & 0xF0000000) != 0 )
    {
      v25 = 180;
      v23 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
      v24 = "IdentityParser::CEscapedCharacterReader::ReadCharacter";
      v22 = "(chTemp & 0xf0000000) == 0";
      goto LABEL_35;
    }
    v18 = 16 * i;
    if ( (unsigned int)(v21 - 48) <= 9 )
    {
      v19 = v18 - 48;
      continue;
    }
    if ( (unsigned int)(v21 - 97) <= 5 )
    {
      v19 = v18 - 87;
      continue;
    }
    if ( (unsigned int)(v21 - 65) > 5 )
      break;
    v19 = v18 - 60;
  }
  v25 = 191;
LABEL_33:
  v26 = 0;
  v23 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
  v24 = "IdentityParser::CEscapedCharacterReader::ReadCharacter";
LABEL_36:
  v9 = 3221225825LL;
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
           &v27,
           &v23,
           v9);
}

```

## disassembly

```asm
0x180096b5c  mov     [rsp-18h+arg_10], rbx
0x180096b61  mov     [rsp-18h+arg_18], rsi
0x180096b66  push    rbp
0x180096b67  push    rdi
0x180096b68  push    r15
0x180096b6a  mov     rbp, rsp
0x180096b6d  sub     rsp, 50h
0x180096b71  mov     rax, cs:__security_cookie
0x180096b78  xor     rax, rsp
0x180096b7b  mov     [rbp+var_8], rax
0x180096b7f  mov     byte ptr [rdx], 0
0x180096b82  mov     rsi, rdx
0x180096b85  mov     r8, [rcx+10h]
0x180096b89  mov     rdi, rcx
0x180096b8c  mov     rdx, [rcx+8]
0x180096b90  lea     rcx, [rbp+var_30]
0x180096b94  mov     [rbp+var_10], 0
0x180096b9b  call    RtlDecodeUtf16LE
0x180096ba0  or      r15d, 0FFFFFFFFh
0x180096ba4  mov     ebx, [rax]
0x180096ba6  mov     rdx, [rax+8]
0x180096baa  cmp     ebx, r15d
0x180096bad  jnz     short loc_180096BF5
0x180096baf  test    edx, edx
0x180096bb1  jns     loc_180096DC9
0x180096bb7  mov     [rbp+var_20], 94h
0x180096bbf  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x180096bc6  mov     r8d, edx
0x180096bc9  mov     [rbp+var_30], rax
0x180096bcd  lea     rax, aIdentityparser_1; "IdentityParser::CEscapedCharacterReader"...
0x180096bd4  mov     [rbp+var_28], rax
0x180096bd8  lea     rax, aRvUcscharacter_0; "__rv.UcsCharacter != (0xffffffff)"
0x180096bdf  mov     [rbp+var_18], rax
0x180096be3  lea     rdx, [rbp+var_30]
0x180096be7  lea     rcx, [rbp+var_10]
0x180096beb  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180096bf0  jmp     loc_180096DA7
0x180096bf5  mov     [rdi+8], rdx
0x180096bf9  cmp     ebx, 5Ch ; '\'
0x180096bfc  jnz     loc_180096DA3
0x180096c02  mov     r8, [rdi+10h]
0x180096c06  lea     rcx, [rbp+var_30]
0x180096c0a  call    RtlDecodeUtf16LE
0x180096c0f  mov     ebx, [rax]
0x180096c11  mov     rdx, [rax+8]
0x180096c15  cmp     ebx, r15d
0x180096c18  jnz     short loc_180096C2C
0x180096c1a  test    edx, edx
0x180096c1c  jns     loc_180096DC9
0x180096c22  mov     [rbp+var_20], 98h
0x180096c2a  jmp     short loc_180096BBF
0x180096c2c  mov     [rdi+8], rdx
0x180096c30  cmp     ebx, 5Ch ; '\'
0x180096c33  ja      short loc_180096C52
0x180096c35  lea     eax, [rbx-22h]
0x180096c38  cmp     eax, 3Ah ; ':'
0x180096c3b  ja      short loc_180096C72
0x180096c3d  mov     rcx, 400000008002421h
0x180096c47  bt      rcx, rax
0x180096c4b  jnb     short loc_180096C72
0x180096c4d  jmp     loc_180096D9C
0x180096c52  sub     ebx, 6Eh ; 'n'
0x180096c55  jz      loc_180096D97
0x180096c5b  sub     ebx, 4
0x180096c5e  jz      loc_180096D90
0x180096c64  sub     ebx, 2
0x180096c67  jz      loc_180096D89
0x180096c6d  cmp     ebx, 1
0x180096c70  jz      short loc_180096C7C
0x180096c72  mov     [rbp+var_20], 0C7h
0x180096c7a  jmp     short loc_180096CEC
0x180096c7c  xor     ebx, ebx
0x180096c7e  jmp     short loc_180096CBF
0x180096c80  mov     [rdi+8], rdx
0x180096c84  cmp     ecx, 3Bh ; ';'
0x180096c87  jz      loc_180096D40
0x180096c8d  test    ebx, 0F0000000h
0x180096c93  jnz     short loc_180096D0C
0x180096c95  shl     ebx, 4
0x180096c98  lea     eax, [rcx-30h]
0x180096c9b  cmp     eax, 9
0x180096c9e  ja      short loc_180096CA5
0x180096ca0  add     ebx, 0FFFFFFD0h
0x180096ca3  jmp     short loc_180096CBD
0x180096ca5  lea     eax, [rcx-61h]
0x180096ca8  cmp     eax, 5
0x180096cab  ja      short loc_180096CB2
0x180096cad  add     ebx, 0FFFFFFA9h
0x180096cb0  jmp     short loc_180096CBD
0x180096cb2  lea     eax, [rcx-41h]
0x180096cb5  cmp     eax, 5
0x180096cb8  ja      short loc_180096CE4
0x180096cba  add     ebx, 0FFFFFFC4h
0x180096cbd  add     ebx, ecx
0x180096cbf  mov     r8, [rdi+10h]
0x180096cc3  lea     rcx, [rbp+var_30]
0x180096cc7  call    RtlDecodeUtf16LE
0x180096ccc  mov     ecx, [rax]
0x180096cce  mov     rdx, [rax+8]
0x180096cd2  cmp     ecx, r15d
0x180096cd5  jnz     short loc_180096C80
0x180096cd7  test    edx, edx
0x180096cd9  jns     loc_180096DC9
0x180096cdf  jmp     loc_180096D7C
0x180096ce4  mov     [rbp+var_20], 0BFh
0x180096cec  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x180096cf3  mov     [rbp+var_18], 0
0x180096cfb  mov     [rbp+var_30], rax
0x180096cff  lea     rax, aIdentityparser_1; "IdentityParser::CEscapedCharacterReader"...
0x180096d06  mov     [rbp+var_28], rax
0x180096d0a  jmp     short loc_180096D35
0x180096d0c  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x180096d13  mov     [rbp+var_20], 0B4h
0x180096d1b  mov     [rbp+var_30], rax
0x180096d1f  lea     rax, aIdentityparser_1; "IdentityParser::CEscapedCharacterReader"...
0x180096d26  mov     [rbp+var_28], rax
0x180096d2a  lea     rax, aChtemp0xf00000; "(chTemp & 0xf0000000) == 0"
0x180096d31  mov     [rbp+var_18], rax
0x180096d35  mov     r8d, 0C0000161h
0x180096d3b  jmp     loc_180096BE3
0x180096d40  cmp     ebx, 110000h
0x180096d46  jnb     short loc_180096D55
0x180096d48  lea     eax, [rbx-0D800h]
0x180096d4e  cmp     eax, 7FFh
0x180096d53  ja      short loc_180096D9C
0x180096d55  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x180096d5c  mov     [rbp+var_20], 0C2h
0x180096d64  mov     [rbp+var_30], rax
0x180096d68  lea     rax, aIdentityparser_1; "IdentityParser::CEscapedCharacterReader"...
0x180096d6f  mov     [rbp+var_28], rax
0x180096d73  lea     rax, aChtemp0x0010ff; "(chTemp <= (0x0010FFFF)) && ((chTemp < "...
0x180096d7a  jmp     short loc_180096D31
0x180096d7c  mov     [rbp+var_20], 0AFh
0x180096d84  jmp     loc_180096BBF
0x180096d89  mov     ebx, 9
0x180096d8e  jmp     short loc_180096D9C
0x180096d90  mov     ebx, 0Dh
0x180096d95  jmp     short loc_180096D9C
0x180096d97  mov     ebx, 0Ah
0x180096d9c  mov     byte ptr [rsi], 1
0x180096d9f  bts     ebx, 1Fh
0x180096da3  mov     [rdi], ebx
0x180096da5  xor     eax, eax
0x180096da7  mov     rcx, [rbp+var_8]
0x180096dab  xor     rcx, rsp; StackCookie
0x180096dae  call    __security_check_cookie
0x180096db3  lea     r11, [rsp+50h+var_s0]
0x180096db8  mov     rbx, [r11+30h]
0x180096dbc  mov     rsi, [r11+38h]
0x180096dc0  mov     rsp, r11
0x180096dc3  pop     r15
0x180096dc5  pop     rdi
0x180096dc6  pop     rbp
0x180096dc7  retn
0x180096dc9  mov     ecx, 0C00000E5h; int
0x180096dce  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
