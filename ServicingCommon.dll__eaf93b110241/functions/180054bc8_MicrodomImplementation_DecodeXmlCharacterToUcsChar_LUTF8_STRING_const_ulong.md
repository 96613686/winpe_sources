# MicrodomImplementation::DecodeXmlCharacterToUcsChar(_LUTF8_STRING const &,ulong *)

- ea: `0x180054bc8`
- end: `0x180054db3`
- name: `?DecodeXmlCharacterToUcsChar@MicrodomImplementation@@YAJAEBU_LUTF8_STRING@@PEAK@Z`
- size: `491`
- prototype: `__int64 __fastcall(MicrodomImplementation *__hidden this, const struct _LUTF8_STRING *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012aa0`

## callees

- `0x18000d660`
- `0x18001f4ac`
- `0x18001f5d4`
- `0x18001fd10`
- `0x1800293a0`
- `0x180053e14`
- `0x180054bc8`

## string_xrefs

- `0x180054c10`: `onecore\base\xml\udom_microdom.cpp`
- `0x180054c78`: `onecore\base\xml\udom_microdom.cpp`
- `0x180054d3b`: `onecore\base\xml\udom_microdom.cpp`
- `0x180054d6a`: `onecore\base\xml\udom_microdom.cpp`
- `0x180054c23`: `MicrodomImplementation::DecodeXmlCharacterToUcsChar`
- `0x180054c8b`: `MicrodomImplementation::DecodeXmlCharacterToUcsChar`
- `0x180054d4e`: `MicrodomImplementation::DecodeXmlCharacterToUcsChar`
- `0x180054d81`: `MicrodomImplementation::DecodeXmlCharacterToUcsChar`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::DecodeXmlCharacterToUcsChar(
        MicrodomImplementation *this,
        const struct _LUTF8_STRING *a2,
        unsigned int *a3)
{
  _BYTE *v3; // rax
  unsigned int v4; // ebx
  unsigned __int64 v6; // rcx
  const char *v7; // rax
  __int64 result; // rax
  _BYTE *v9; // r10
  unsigned int v10; // edi
  _BYTE *v11; // rsi
  __int64 v12; // rax
  int v13; // ecx
  __int64 v14; // r10
  unsigned int v15; // r11d
  int v16; // r11d
  unsigned int v17; // [rsp+20h] [rbp-40h] BYREF
  const char *v18; // [rsp+28h] [rbp-38h] BYREF
  const char *v19; // [rsp+30h] [rbp-30h]
  __int64 v20; // [rsp+38h] [rbp-28h]
  const char *v21; // [rsp+40h] [rbp-20h]
  int v22; // [rsp+48h] [rbp-18h] BYREF

  v3 = (_BYTE *)*((_QWORD *)this + 2);
  v4 = 0;
  v22 = 0;
  v17 = 0;
  if ( *v3 != 35 )
    goto LABEL_28;
  v6 = *(_QWORD *)this;
  if ( v6 < 2 )
  {
    v20 = 192;
    v18 = "onecore\\base\\xml\\udom_microdom.cpp";
    v19 = "MicrodomImplementation::DecodeXmlCharacterToUcsChar";
    v7 = "Source.Length >= 2";
    goto LABEL_4;
  }
  v9 = v3 + 1;
  if ( v3[1] == 120 )
  {
    if ( v6 < 3 )
    {
      v20 = 198;
      v18 = "onecore\\base\\xml\\udom_microdom.cpp";
      v19 = "MicrodomImplementation::DecodeXmlCharacterToUcsChar";
      v7 = "Source.Length >= 3";
      goto LABEL_4;
    }
    v9 = v3 + 2;
    v10 = 16;
  }
  else
  {
    v10 = 10;
  }
  v11 = &v3[v6];
  while ( 1 )
  {
    if ( v9 == v11 )
    {
      *(_DWORD *)a2 = v4;
      return 0;
    }
    v12 = RtlDecodeUtf8(&v18, v9, v11);
    v13 = *(_DWORD *)v12;
    v14 = *(_QWORD *)(v12 + 8);
    if ( *(_DWORD *)v12 == -1 )
    {
      if ( (int)v14 < 0 )
      {
        v20 = 208;
        v18 = "onecore\\base\\xml\\udom_microdom.cpp";
        v19 = "MicrodomImplementation::DecodeXmlCharacterToUcsChar";
        v21 = "__rv.UcsCharacter != (0xffffffff)";
        return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                 &v22,
                 &v18,
                 (unsigned int)v14);
      }
LABEL_28:
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x180054DB2LL);
    }
    v15 = v13 - 48;
    if ( (unsigned int)(v13 - 48) > 9 )
    {
      if ( (unsigned int)(v13 - 97) > 5 )
      {
        v15 = 0;
        if ( (unsigned int)(v13 - 65) <= 5 )
          v15 = v13 - 55;
      }
      else
      {
        v15 = v13 - 87;
      }
    }
    if ( v15 >= v10 )
      break;
    result = BUCL::Rtl::Multiply<unsigned long>(v4, v10, &v17);
    if ( (int)result < 0 )
      return result;
    v4 = v17 + v16;
    if ( v17 + v16 < v17 )
      return 3221225621LL;
    v17 += v16;
  }
  v20 = 224;
  v18 = "onecore\\base\\xml\\udom_microdom.cpp";
  v19 = "MicrodomImplementation::DecodeXmlCharacterToUcsChar";
  v7 = "ulValue < MultFactor";
LABEL_4:
  v21 = v7;
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
           &v22,
           &v18);
}

```

## disassembly

```asm
0x180054bc8  mov     [rsp-18h+arg_10], rbx
0x180054bcd  mov     [rsp-18h+arg_18], rsi
0x180054bd2  push    rbp
0x180054bd3  push    rdi
0x180054bd4  push    r14
0x180054bd6  mov     rbp, rsp
0x180054bd9  sub     rsp, 60h
0x180054bdd  mov     rax, cs:__security_cookie
0x180054be4  xor     rax, rsp
0x180054be7  mov     [rbp+var_10], rax
0x180054beb  mov     rax, [rcx+10h]
0x180054bef  xor     ebx, ebx
0x180054bf1  mov     r14, rdx
0x180054bf4  mov     [rbp+var_18], 0
0x180054bfb  mov     [rbp+var_40], ebx
0x180054bfe  cmp     byte ptr [rax], 23h ; '#'
0x180054c01  jnz     loc_180054DA8
0x180054c07  mov     rcx, [rcx]
0x180054c0a  cmp     rcx, 2
0x180054c0e  jnb     short loc_180054C68
0x180054c10  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180054c17  mov     [rbp+var_28], 0C0h
0x180054c1f  mov     [rbp+var_38], rax
0x180054c23  lea     rax, aMicrodomimplem_11; "MicrodomImplementation::DecodeXmlCharac"...
0x180054c2a  mov     [rbp+var_30], rax
0x180054c2e  lea     rax, aSourceLength2; "Source.Length >= 2"
0x180054c35  lea     rdx, [rbp+var_38]
0x180054c39  mov     [rbp+var_20], rax
0x180054c3d  lea     rcx, [rbp+var_18]
0x180054c41  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180054c46  mov     rcx, [rbp+var_10]
0x180054c4a  xor     rcx, rsp; StackCookie
0x180054c4d  call    __security_check_cookie
0x180054c52  lea     r11, [rsp+60h+var_s0]
0x180054c57  mov     rbx, [r11+30h]
0x180054c5b  mov     rsi, [r11+38h]
0x180054c5f  mov     rsp, r11
0x180054c62  pop     r14
0x180054c64  pop     rdi
0x180054c65  pop     rbp
0x180054c66  retn
0x180054c68  lea     r10, [rax+1]
0x180054c6c  cmp     byte ptr [r10], 78h ; 'x'
0x180054c70  jnz     short loc_180054CAA
0x180054c72  cmp     rcx, 3
0x180054c76  jnb     short loc_180054C9F
0x180054c78  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180054c7f  mov     [rbp+var_28], 0C6h
0x180054c87  mov     [rbp+var_38], rax
0x180054c8b  lea     rax, aMicrodomimplem_11; "MicrodomImplementation::DecodeXmlCharac"...
0x180054c92  mov     [rbp+var_30], rax
0x180054c96  lea     rax, aSourceLength3; "Source.Length >= 3"
0x180054c9d  jmp     short loc_180054C35
0x180054c9f  lea     r10, [rax+2]
0x180054ca3  mov     edi, 10h
0x180054ca8  jmp     short loc_180054CAF
0x180054caa  mov     edi, 0Ah
0x180054caf  lea     rsi, [rcx+rax]
0x180054cb3  jmp     short loc_180054D22
0x180054cb5  mov     r8, rsi
0x180054cb8  lea     rcx, [rbp+var_38]
0x180054cbc  mov     rdx, r10
0x180054cbf  call    RtlDecodeUtf8
0x180054cc4  mov     ecx, [rax]
0x180054cc6  mov     r10, [rax+8]
0x180054cca  cmp     ecx, 0FFFFFFFFh
0x180054ccd  jz      loc_180054D65
0x180054cd3  lea     r11d, [rcx-30h]
0x180054cd7  cmp     r11d, 9
0x180054cdb  jbe     short loc_180054CFA
0x180054cdd  lea     eax, [rcx-61h]
0x180054ce0  cmp     eax, 5
0x180054ce3  ja      short loc_180054CEB
0x180054ce5  lea     r11d, [rcx-57h]
0x180054ce9  jmp     short loc_180054CFA
0x180054ceb  xor     r11d, r11d
0x180054cee  lea     eax, [rcx-41h]
0x180054cf1  cmp     eax, 5
0x180054cf4  ja      short loc_180054CFA
0x180054cf6  lea     r11d, [rcx-37h]
0x180054cfa  cmp     r11d, edi
0x180054cfd  jnb     short loc_180054D3B
0x180054cff  lea     r8, [rbp+var_40]
0x180054d03  mov     edx, edi
0x180054d05  mov     ecx, ebx
0x180054d07  call    ??$Multiply@K@Rtl@BUCL@@YAJKKAEAK@Z; BUCL::Rtl::Multiply<ulong>(ulong,ulong,ulong &)
0x180054d0c  test    eax, eax
0x180054d0e  js      loc_180054C46
0x180054d14  mov     eax, [rbp+var_40]
0x180054d17  lea     ebx, [rax+r11]
0x180054d1b  cmp     ebx, eax
0x180054d1d  jb      short loc_180054D31
0x180054d1f  mov     [rbp+var_40], ebx
0x180054d22  cmp     r10, rsi
0x180054d25  jnz     short loc_180054CB5
0x180054d27  mov     [r14], ebx
0x180054d2a  xor     eax, eax
0x180054d2c  jmp     loc_180054C46
0x180054d31  mov     eax, 0C0000095h
0x180054d36  jmp     loc_180054C46
0x180054d3b  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180054d42  mov     [rbp+var_28], 0E0h
0x180054d4a  mov     [rbp+var_38], rax
0x180054d4e  lea     rax, aMicrodomimplem_11; "MicrodomImplementation::DecodeXmlCharac"...
0x180054d55  mov     [rbp+var_30], rax
0x180054d59  lea     rax, aUlvalueMultfac; "ulValue < MultFactor"
0x180054d60  jmp     loc_180054C35
0x180054d65  test    r10d, r10d
0x180054d68  jns     short loc_180054DA8
0x180054d6a  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180054d71  mov     [rbp+var_28], 0D0h
0x180054d79  mov     [rbp+var_38], rax
0x180054d7d  lea     rdx, [rbp+var_38]
0x180054d81  lea     rax, aMicrodomimplem_11; "MicrodomImplementation::DecodeXmlCharac"...
0x180054d88  mov     r8d, r10d
0x180054d8b  mov     [rbp+var_30], rax
0x180054d8f  lea     rcx, [rbp+var_18]
0x180054d93  lea     rax, aRvUcscharacter_0; "__rv.UcsCharacter != (0xffffffff)"
0x180054d9a  mov     [rbp+var_20], rax
0x180054d9e  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180054da3  jmp     loc_180054C46
0x180054da8  mov     ecx, 0C00000E5h; int
0x180054dad  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
