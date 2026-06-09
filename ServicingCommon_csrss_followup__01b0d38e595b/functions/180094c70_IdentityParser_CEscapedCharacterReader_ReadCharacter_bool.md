# IdentityParser::CEscapedCharacterReader::ReadCharacter(bool &)

- ea: `0x180094c70`
- end: `0x180094ef8`
- name: `?ReadCharacter@CEscapedCharacterReader@IdentityParser@@AEAAJAEA_N@Z`
- size: `648`
- prototype: `__int64 __fastcall(IdentityParser::CEscapedCharacterReader *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180094204`

## callees

- `0x180014440`
- `0x18001f840`
- `0x18002d2b0`
- `0x180094c70`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180094ea3`
- `ntdll!RtlRaiseStatus` at `0x180094ea3`

## string_xrefs

- `0x180094cd7`: `IdentityParser::CEscapedCharacterReader::ReadCharacter`
- `0x180094e1d`: `IdentityParser::CEscapedCharacterReader::ReadCharacter`
- `0x180094e3d`: `IdentityParser::CEscapedCharacterReader::ReadCharacter`
- `0x180094e86`: `IdentityParser::CEscapedCharacterReader::ReadCharacter`
- `0x180094e91`: `(chTemp <= (0x0010FFFF)) && ((chTemp < 0xd800) || (chTemp > 0xdfff))`
- `0x180094e48`: `(chTemp & 0xf0000000) == 0`

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
  __int64 v13; // rcx
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  __int64 v17; // rax
  int v18; // edx
  int v19; // ebx
  int v20; // ebx
  const char *v21; // rax
  const char *v22; // [rsp+20h] [rbp-30h] BYREF
  const char *v23; // [rsp+28h] [rbp-28h]
  __int64 v24; // [rsp+30h] [rbp-20h]
  const char *v25; // [rsp+38h] [rbp-18h]
  int v26; // [rsp+40h] [rbp-10h] BYREF

  *a2 = 0;
  v3 = *((_QWORD *)this + 2);
  v5 = *((_QWORD *)this + 1);
  v26 = 0;
  v6 = RtlDecodeUtf16LE(&v22, v5, v3);
  v7 = *(_DWORD *)v6;
  v8 = *(_QWORD *)(v6 + 8);
  if ( *(_DWORD *)v6 == -1 )
  {
    if ( (int)v8 < 0 )
    {
      v24 = 148;
      v9 = (unsigned int)v8;
LABEL_4:
      v22 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
      v23 = "IdentityParser::CEscapedCharacterReader::ReadCharacter";
      v25 = "__rv.UcsCharacter != (0xffffffff)";
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
               &v26,
               &v22,
               v9);
    }
LABEL_44:
    RtlRaiseStatus(-1073741595);
  }
  *((_QWORD *)this + 1) = v8;
  if ( v7 != 92 )
  {
LABEL_50:
    *(_DWORD *)this = v7;
    return 0;
  }
  v11 = RtlDecodeUtf16LE(&v22, v8, *((_QWORD *)this + 2));
  i = *(_DWORD *)v11;
  v13 = *(_QWORD *)(v11 + 8);
  if ( *(_DWORD *)v11 == -1 )
  {
    if ( (int)v13 >= 0 )
      goto LABEL_44;
    v24 = 152;
    goto LABEL_10;
  }
  *((_QWORD *)this + 1) = v13;
  if ( i <= 0x5C )
  {
    if ( i == 92 || i == 34 || i == 39 || i == 44 || i == 47 || i == 61 )
      goto LABEL_49;
LABEL_23:
    v24 = 199;
    goto LABEL_36;
  }
  v14 = i - 110;
  if ( !v14 )
  {
    i = 10;
    goto LABEL_49;
  }
  v15 = v14 - 4;
  if ( !v15 )
  {
    i = 13;
    goto LABEL_49;
  }
  v16 = v15 - 2;
  if ( !v16 )
  {
    i = 9;
LABEL_49:
    *a2 = 1;
    v7 = i | 0x80000000;
    goto LABEL_50;
  }
  if ( v16 != 1 )
    goto LABEL_23;
  for ( i = 0; ; i = v18 + v20 )
  {
    v17 = RtlDecodeUtf16LE(&v22, v13, *((_QWORD *)this + 2));
    v18 = *(_DWORD *)v17;
    v13 = *(_QWORD *)(v17 + 8);
    if ( *(_DWORD *)v17 == -1 )
    {
      if ( (int)v13 >= 0 )
        goto LABEL_44;
      v24 = 175;
LABEL_10:
      v9 = (unsigned int)v13;
      goto LABEL_4;
    }
    *((_QWORD *)this + 1) = v13;
    if ( v18 == 59 )
    {
      if ( i - 55296 > 0x7FF && i < 0x110000 )
        goto LABEL_49;
      v24 = 194;
      v22 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
      v23 = "IdentityParser::CEscapedCharacterReader::ReadCharacter";
      v21 = "(chTemp <= (0x0010FFFF)) && ((chTemp < 0xd800) || (chTemp > 0xdfff))";
LABEL_38:
      v25 = v21;
      goto LABEL_39;
    }
    if ( (i & 0xF0000000) != 0 )
    {
      v24 = 180;
      v22 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
      v23 = "IdentityParser::CEscapedCharacterReader::ReadCharacter";
      v21 = "(chTemp & 0xf0000000) == 0";
      goto LABEL_38;
    }
    v19 = 16 * i;
    if ( (unsigned int)(v18 - 48) <= 9 )
    {
      v20 = v19 - 48;
      continue;
    }
    if ( (unsigned int)(v18 - 97) <= 5 )
    {
      v20 = v19 - 87;
      continue;
    }
    if ( (unsigned int)(v18 - 65) > 5 )
      break;
    v20 = v19 - 60;
  }
  v24 = 191;
LABEL_36:
  v25 = 0;
  v22 = "onecore\\base\\wcp\\identity\\id_authority_helpers.cpp";
  v23 = "IdentityParser::CEscapedCharacterReader::ReadCharacter";
LABEL_39:
  v9 = 3221225825LL;
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
           &v26,
           &v22,
           v9);
}

```

## disassembly

```asm
0x180094c70  mov     [rsp-18h+arg_10], rbx
0x180094c75  push    rbp
0x180094c76  push    rsi
0x180094c77  push    rdi
0x180094c78  mov     rbp, rsp
0x180094c7b  sub     rsp, 50h
0x180094c7f  mov     rax, cs:__security_cookie
0x180094c86  xor     rax, rsp
0x180094c89  mov     [rbp+var_8], rax
0x180094c8d  mov     byte ptr [rdx], 0
0x180094c90  mov     rsi, rdx
0x180094c93  mov     r8, [rcx+10h]
0x180094c97  mov     rdi, rcx
0x180094c9a  mov     rdx, [rcx+8]
0x180094c9e  lea     rcx, [rbp+var_30]
0x180094ca2  mov     [rbp+var_10], 0
0x180094ca9  call    RtlDecodeUtf16LE
0x180094cae  mov     ebx, [rax]
0x180094cb0  mov     rdx, [rax+8]
0x180094cb4  cmp     ebx, 0FFFFFFFFh
0x180094cb7  jnz     short loc_180094CFF
0x180094cb9  test    edx, edx
0x180094cbb  jns     loc_180094E9E
0x180094cc1  mov     [rbp+var_20], 94h
0x180094cc9  mov     r8d, edx
0x180094ccc  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x180094cd3  mov     [rbp+var_30], rax
0x180094cd7  lea     rax, aIdentityparser_1; "IdentityParser::CEscapedCharacterReader"...
0x180094cde  mov     [rbp+var_28], rax
0x180094ce2  lea     rax, aRvUcscharacter_0; "__rv.UcsCharacter != (0xffffffff)"
0x180094ce9  mov     [rbp+var_18], rax
0x180094ced  lea     rdx, [rbp+var_30]
0x180094cf1  lea     rcx, [rbp+var_10]
0x180094cf5  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180094cfa  jmp     loc_180094EDB
0x180094cff  mov     [rdi+8], rdx
0x180094d03  cmp     ebx, 5Ch ; '\'
0x180094d06  jnz     loc_180094ED7
0x180094d0c  mov     r8, [rdi+10h]
0x180094d10  lea     rcx, [rbp+var_30]
0x180094d14  call    RtlDecodeUtf16LE
0x180094d19  mov     ebx, [rax]
0x180094d1b  mov     rcx, [rax+8]
0x180094d1f  cmp     ebx, 0FFFFFFFFh
0x180094d22  jnz     short loc_180094D39
0x180094d24  test    ecx, ecx
0x180094d26  jns     loc_180094E9E
0x180094d2c  mov     [rbp+var_20], 98h
0x180094d34  mov     r8d, ecx
0x180094d37  jmp     short loc_180094CCC
0x180094d39  mov     [rdi+8], rcx
0x180094d3d  cmp     ebx, 5Ch ; '\'
0x180094d40  ja      short loc_180094D76
0x180094d42  jz      loc_180094ED0
0x180094d48  cmp     ebx, 22h ; '"'
0x180094d4b  jz      loc_180094ED0
0x180094d51  cmp     ebx, 27h ; '''
0x180094d54  jz      loc_180094ED0
0x180094d5a  cmp     ebx, 2Ch ; ','
0x180094d5d  jz      loc_180094ED0
0x180094d63  cmp     ebx, 2Fh ; '/'
0x180094d66  jz      loc_180094ED0
0x180094d6c  cmp     ebx, 3Dh ; '='
0x180094d6f  jnz     short loc_180094D96
0x180094d71  jmp     loc_180094ED0
0x180094d76  sub     ebx, 6Eh ; 'n'
0x180094d79  jz      loc_180094ECB
0x180094d7f  sub     ebx, 4
0x180094d82  jz      loc_180094EC4
0x180094d88  sub     ebx, 2
0x180094d8b  jz      loc_180094EBD
0x180094d91  cmp     ebx, 1
0x180094d94  jz      short loc_180094DA0
0x180094d96  mov     [rbp+var_20], 0C7h
0x180094d9e  jmp     short loc_180094E0A
0x180094da0  xor     ebx, ebx
0x180094da2  mov     r8, [rdi+10h]
0x180094da6  mov     rdx, rcx
0x180094da9  lea     rcx, [rbp+var_30]
0x180094dad  call    RtlDecodeUtf16LE
0x180094db2  mov     edx, [rax]
0x180094db4  mov     rcx, [rax+8]
0x180094db8  cmp     edx, 0FFFFFFFFh
0x180094dbb  jz      loc_180094E9A
0x180094dc1  mov     [rdi+8], rcx
0x180094dc5  cmp     edx, 3Bh ; ';'
0x180094dc8  jz      loc_180094E5E
0x180094dce  test    ebx, 0F0000000h
0x180094dd4  jnz     short loc_180094E2A
0x180094dd6  shl     ebx, 4
0x180094dd9  lea     eax, [rdx-30h]
0x180094ddc  cmp     eax, 9
0x180094ddf  ja      short loc_180094DE6
0x180094de1  add     ebx, 0FFFFFFD0h
0x180094de4  jmp     short loc_180094DFE
0x180094de6  lea     eax, [rdx-61h]
0x180094de9  cmp     eax, 5
0x180094dec  ja      short loc_180094DF3
0x180094dee  add     ebx, 0FFFFFFA9h
0x180094df1  jmp     short loc_180094DFE
0x180094df3  lea     eax, [rdx-41h]
0x180094df6  cmp     eax, 5
0x180094df9  ja      short loc_180094E02
0x180094dfb  add     ebx, 0FFFFFFC4h
0x180094dfe  add     ebx, edx
0x180094e00  jmp     short loc_180094DA2
0x180094e02  mov     [rbp+var_20], 0BFh
0x180094e0a  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x180094e11  mov     [rbp+var_18], 0
0x180094e19  mov     [rbp+var_30], rax
0x180094e1d  lea     rax, aIdentityparser_1; "IdentityParser::CEscapedCharacterReader"...
0x180094e24  mov     [rbp+var_28], rax
0x180094e28  jmp     short loc_180094E53
0x180094e2a  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x180094e31  mov     [rbp+var_20], 0B4h
0x180094e39  mov     [rbp+var_30], rax
0x180094e3d  lea     rax, aIdentityparser_1; "IdentityParser::CEscapedCharacterReader"...
0x180094e44  mov     [rbp+var_28], rax
0x180094e48  lea     rax, aChtemp0xf00000; "(chTemp & 0xf0000000) == 0"
0x180094e4f  mov     [rbp+var_18], rax
0x180094e53  mov     r8d, 0C0000161h
0x180094e59  jmp     loc_180094CED
0x180094e5e  lea     eax, [rbx-0D800h]
0x180094e64  cmp     eax, 7FFh
0x180094e69  jbe     short loc_180094E73
0x180094e6b  cmp     ebx, 110000h
0x180094e71  jb      short loc_180094ED0
0x180094e73  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\identity\\id_author"...
0x180094e7a  mov     [rbp+var_20], 0C2h
0x180094e82  mov     [rbp+var_30], rax
0x180094e86  lea     rax, aIdentityparser_1; "IdentityParser::CEscapedCharacterReader"...
0x180094e8d  mov     [rbp+var_28], rax
0x180094e91  lea     rax, aChtemp0x0010ff; "(chTemp <= (0x0010FFFF)) && ((chTemp < "...
0x180094e98  jmp     short loc_180094E4F
0x180094e9a  test    ecx, ecx
0x180094e9c  js      short loc_180094EB0
0x180094e9e  mov     ecx, 0C00000E5h; Status
0x180094ea3  call    cs:__imp_RtlRaiseStatus
0x180094eaa  nop     dword ptr [rax+rax+00h]
0x180094eaf  int     3; Trap to Debugger
0x180094eb0  mov     [rbp+var_20], 0AFh
0x180094eb8  jmp     loc_180094D34
0x180094ebd  mov     ebx, 9
0x180094ec2  jmp     short loc_180094ED0
0x180094ec4  mov     ebx, 0Dh
0x180094ec9  jmp     short loc_180094ED0
0x180094ecb  mov     ebx, 0Ah
0x180094ed0  mov     byte ptr [rsi], 1
0x180094ed3  bts     ebx, 1Fh
0x180094ed7  mov     [rdi], ebx
0x180094ed9  xor     eax, eax
0x180094edb  mov     rcx, [rbp+var_8]
0x180094edf  xor     rcx, rsp; StackCookie
0x180094ee2  call    __security_check_cookie
0x180094ee7  mov     rbx, [rsp+50h+arg_10]
0x180094eef  add     rsp, 50h
0x180094ef3  pop     rdi
0x180094ef4  pop     rsi
0x180094ef5  pop     rbp
0x180094ef6  retn
```
