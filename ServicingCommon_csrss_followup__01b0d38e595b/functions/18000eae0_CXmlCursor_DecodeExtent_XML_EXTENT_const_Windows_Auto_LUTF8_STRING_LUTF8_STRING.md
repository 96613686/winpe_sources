# CXmlCursor::DecodeExtent(_XML_EXTENT const &,Windows::Auto<_LUTF8_STRING> *,_LUTF8_STRING *)

- ea: `0x18000eae0`
- end: `0x18000eccb`
- name: `?DecodeExtent@CXmlCursor@@QEAAJAEBU_XML_EXTENT@@PEAV?$Auto@U_LUTF8_STRING@@@Windows@@PEAU_LUTF8_STRING@@@Z`
- size: `491`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000db80`
- `0x18000e030`
- `0x18000e5ec`
- `0x18000e924`
- `0x18006350c`

## callees

- `0x180004a8c`
- `0x18000c3d0`
- `0x18000eae0`
- `0x18001b214`
- `0x18001f840`
- `0x18002d2b0`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18000ecbe`
- `ntdll!RtlRaiseStatus` at `0x18000ecbe`

## string_xrefs

- `0x18000ebdd`: `onecore\base\xml\udom_xmlcursor.cpp`
- `0x18000ec82`: `onecore\base\xml\udom_xmlcursor.cpp`
- `0x18000ebf4`: `CXmlCursor::DecodeExtent`
- `0x18000ec99`: `CXmlCursor::DecodeExtent`
- `0x18000ec02`: `::RtlXmlExtentToUtf8String( 0, &m_State.ParseState.RawTokenState, &Src, TempString.GetMutablePointer(), &cRequired)`

## pseudocode

```c
__int64 __fastcall CXmlCursor::DecodeExtent(__int64 a1, __int64 *a2, _QWORD *a3, _QWORD *a4)
{
  int v6; // edi
  int v7; // esi
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 result; // rax
  int v11; // eax
  int v12; // ecx
  int v13; // r15d
  int v14; // eax
  unsigned int v15; // ebx
  __int128 v16; // xmm2
  __int64 v17; // xmm3_8
  __int64 v18; // xmm1_8
  unsigned __int64 v19; // [rsp+30h] [rbp-29h] BYREF
  __int128 v20; // [rsp+38h] [rbp-21h] BYREF
  __int64 v21; // [rsp+48h] [rbp-11h]
  const char *v22; // [rsp+50h] [rbp-9h] BYREF
  const char *v23; // [rsp+58h] [rbp-1h]
  __int64 v24; // [rsp+60h] [rbp+7h]
  const char *v25; // [rsp+68h] [rbp+Fh]
  int v26; // [rsp+70h] [rbp+17h] BYREF

  v6 = (int)a2;
  v7 = a1;
  v26 = 0;
  if ( *(_BYTE *)(a1 + 9376) )
  {
    v8 = *a2;
    v9 = a2[1];
    a4[1] = v9;
    *a4 = v9;
    a4[2] = v8;
    return 0;
  }
  v19 = 0;
  if ( a3[2] || (result = RtlAllocateLBlob(a2[1], a3), (int)result >= 0) )
  {
    *a3 = 0;
    v11 = RtlXmlExtentToUtf8String(a1, v7, v6, (_DWORD)a3, (__int64)&v19);
    if ( v11 == -1073741789 )
    {
      v20 = 0;
      v21 = 0;
      v13 = RtlAllocateLBlob(v19, &v20);
      if ( v13 < 0 )
      {
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v20);
        return (unsigned int)v13;
      }
      v14 = RtlXmlExtentToUtf8String(v12, v7, v6, (unsigned int)&v20, (__int64)&v19);
      if ( v14 < 0 )
      {
        v24 = 119;
        v22 = "onecore\\base\\xml\\udom_xmlcursor.cpp";
        v23 = "CXmlCursor::DecodeExtent";
        v25 = "::RtlXmlExtentToUtf8String( 0, &m_State.ParseState.RawTokenState, &Src, TempString.GetMutablePointer(), &cRequired)";
        v15 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                &v26,
                &v22,
                (unsigned int)v14);
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v20);
        return v15;
      }
      if ( v19 <= *((_QWORD *)&v20 + 1) )
      {
        v16 = *(_OWORD *)a3;
        v17 = a3[2];
        v18 = v21;
        *(_OWORD *)a3 = v20;
        a3[2] = v18;
        v20 = v16;
        v21 = v17;
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v20);
LABEL_14:
        *(_OWORD *)a4 = *(_OWORD *)a3;
        a4[2] = a3[2];
        return 0;
      }
    }
    else
    {
      if ( !v11 )
        goto LABEL_14;
      if ( v11 < 0 )
      {
        v24 = 126;
        v22 = "onecore\\base\\xml\\udom_xmlcursor.cpp";
        v25 = 0;
        v23 = "CXmlCursor::DecodeExtent";
        return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                 &v26,
                 &v22,
                 (unsigned int)v11);
      }
    }
    RtlRaiseStatus(-1073741595);
  }
  return result;
}

```

## disassembly

```asm
0x18000eae0  push    rbp
0x18000eae2  push    rbx
0x18000eae3  push    rsi
0x18000eae4  push    rdi
0x18000eae5  push    r14
0x18000eae7  push    r15
0x18000eae9  lea     rbp, [rsp-2Fh]
0x18000eaee  sub     rsp, 88h
0x18000eaf5  mov     rax, cs:__security_cookie
0x18000eafc  xor     rax, rsp
0x18000eaff  mov     [rbp+57h+var_38], rax
0x18000eb03  xor     r15d, r15d
0x18000eb06  mov     rbx, r9
0x18000eb09  mov     r14, r8
0x18000eb0c  mov     rdi, rdx
0x18000eb0f  mov     rsi, rcx
0x18000eb12  mov     [rbp+57h+var_40], r15d
0x18000eb16  cmp     [rcx+24A0h], r15b
0x18000eb1d  jz      short loc_18000EB50
0x18000eb1f  mov     rcx, [rdx]
0x18000eb22  mov     rax, [rdx+8]
0x18000eb26  mov     [r9+8], rax
0x18000eb2a  mov     [r9], rax
0x18000eb2d  mov     [r9+10h], rcx
0x18000eb31  xor     eax, eax
0x18000eb33  mov     rcx, [rbp+57h+var_38]
0x18000eb37  xor     rcx, rsp; StackCookie
0x18000eb3a  call    __security_check_cookie
0x18000eb3f  add     rsp, 88h
0x18000eb46  pop     r15
0x18000eb48  pop     r14
0x18000eb4a  pop     rdi
0x18000eb4b  pop     rsi
0x18000eb4c  pop     rbx
0x18000eb4d  pop     rbp
0x18000eb4e  retn
0x18000eb50  mov     [rbp+57h+var_80], r15
0x18000eb54  cmp     [r8+10h], r15
0x18000eb58  jnz     short loc_18000EB6A
0x18000eb5a  mov     rcx, [rdi+8]
0x18000eb5e  mov     rdx, r14
0x18000eb61  call    RtlAllocateLBlob
0x18000eb66  test    eax, eax
0x18000eb68  js      short loc_18000EB33
0x18000eb6a  lea     rax, [rbp+57h+var_80]
0x18000eb6e  mov     [r14], r15
0x18000eb71  mov     r9, r14
0x18000eb74  mov     [rsp+0B0h+var_90], rax
0x18000eb79  mov     r8, rdi
0x18000eb7c  mov     rdx, rsi
0x18000eb7f  call    RtlXmlExtentToUtf8String
0x18000eb84  cmp     eax, 0C0000023h
0x18000eb89  jnz     loc_18000EC7C
0x18000eb8f  mov     rcx, [rbp+57h+var_80]
0x18000eb93  lea     rdx, [rbp+57h+var_78]
0x18000eb97  xorps   xmm0, xmm0
0x18000eb9a  xor     eax, eax
0x18000eb9c  movups  [rbp+57h+var_78], xmm0
0x18000eba0  mov     [rbp+57h+var_68], rax
0x18000eba4  call    RtlAllocateLBlob
0x18000eba9  mov     r15d, eax
0x18000ebac  test    eax, eax
0x18000ebae  jns     short loc_18000EBC1
0x18000ebb0  lea     rcx, [rbp+57h+var_78]
0x18000ebb4  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18000ebb9  mov     eax, r15d
0x18000ebbc  jmp     loc_18000EB33
0x18000ebc1  lea     rax, [rbp+57h+var_80]
0x18000ebc5  mov     r8, rdi
0x18000ebc8  lea     r9, [rbp+57h+var_78]
0x18000ebcc  mov     [rsp+0B0h+var_90], rax
0x18000ebd1  mov     rdx, rsi
0x18000ebd4  call    RtlXmlExtentToUtf8String
0x18000ebd9  test    eax, eax
0x18000ebdb  jns     short loc_18000EC28
0x18000ebdd  lea     rcx, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_xmlcursor.cpp"
0x18000ebe4  mov     [rbp+57h+var_50], 77h ; 'w'
0x18000ebec  mov     [rbp+57h+var_60], rcx
0x18000ebf0  lea     rdx, [rbp+57h+var_60]
0x18000ebf4  lea     rcx, aCxmlcursorDeco; "CXmlCursor::DecodeExtent"
0x18000ebfb  mov     r8d, eax
0x18000ebfe  mov     [rbp+57h+var_58], rcx
0x18000ec02  lea     rcx, aRtlxmlextentto_0; "::RtlXmlExtentToUtf8String( 0, &m_State"...
0x18000ec09  mov     [rbp+57h+var_48], rcx
0x18000ec0d  lea     rcx, [rbp+57h+var_40]
0x18000ec11  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18000ec16  lea     rcx, [rbp+57h+var_78]
0x18000ec1a  mov     ebx, eax
0x18000ec1c  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18000ec21  mov     eax, ebx
0x18000ec23  jmp     loc_18000EB33
0x18000ec28  mov     rax, qword ptr [rbp+57h+var_78+8]
0x18000ec2c  cmp     [rbp+57h+var_80], rax
0x18000ec30  ja      loc_18000ECB9
0x18000ec36  movups  xmm2, xmmword ptr [r14]
0x18000ec3a  lea     rcx, [rbp+57h+var_78]
0x18000ec3e  movsd   xmm3, qword ptr [r14+10h]
0x18000ec44  movups  xmm0, [rbp+57h+var_78]
0x18000ec48  movsd   xmm1, [rbp+57h+var_68]
0x18000ec4d  movups  xmmword ptr [r14], xmm0
0x18000ec51  movsd   qword ptr [r14+10h], xmm1
0x18000ec57  movups  [rbp+57h+var_78], xmm2
0x18000ec5b  movsd   [rbp+57h+var_68], xmm3
0x18000ec60  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18000ec65  movups  xmm0, xmmword ptr [r14]
0x18000ec69  movups  xmmword ptr [rbx], xmm0
0x18000ec6c  movsd   xmm1, qword ptr [r14+10h]
0x18000ec72  movsd   qword ptr [rbx+10h], xmm1
0x18000ec77  jmp     loc_18000EB31
0x18000ec7c  test    eax, eax
0x18000ec7e  jz      short loc_18000EC65
0x18000ec80  jns     short loc_18000ECB9
0x18000ec82  lea     rcx, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_xmlcursor.cpp"
0x18000ec89  mov     [rbp+57h+var_50], 7Eh ; '~'
0x18000ec91  mov     [rbp+57h+var_60], rcx
0x18000ec95  lea     rdx, [rbp+57h+var_60]
0x18000ec99  lea     rcx, aCxmlcursorDeco; "CXmlCursor::DecodeExtent"
0x18000eca0  mov     [rbp+57h+var_48], r15
0x18000eca4  mov     [rbp+57h+var_58], rcx
0x18000eca8  mov     r8d, eax
0x18000ecab  lea     rcx, [rbp+57h+var_40]
0x18000ecaf  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18000ecb4  jmp     loc_18000EB33
0x18000ecb9  mov     ecx, 0C00000E5h; Status
0x18000ecbe  call    cs:__imp_RtlRaiseStatus
0x18000ecc5  nop     dword ptr [rax+rax+00h]
0x18000ecca  int     3; Trap to Debugger
```
