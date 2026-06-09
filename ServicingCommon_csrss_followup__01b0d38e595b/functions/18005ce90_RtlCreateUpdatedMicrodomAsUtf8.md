# RtlCreateUpdatedMicrodomAsUtf8

- ea: `0x18005ce90`
- end: `0x18005cfce`
- name: `RtlCreateUpdatedMicrodomAsUtf8`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005cd60`

## callees

- `0x180004a8c`
- `0x18001f1d8`
- `0x18002d2b0`
- `0x18005bb90`
- `0x18005ce90`

## string_xrefs

- `0x18005ceca`: `onecore\base\xml\udom_modify.cpp`
- `0x18005cf0d`: `onecore\base\xml\udom_modify.cpp`
- `0x18005cf39`: `onecore\base\xml\udom_modify.cpp`
- `0x18005cee8`: `RtlIsMicrodomUpdateContextValid(TheContext)`
- `0x18005cedd`: `Windows::uDom::Rtl::RtlCreateUpdatedMicrodomAsUtf8`
- `0x18005cf20`: `Windows::uDom::Rtl::RtlCreateUpdatedMicrodomAsUtf8`
- `0x18005cf50`: `Windows::uDom::Rtl::RtlCreateUpdatedMicrodomAsUtf8`
- `0x18005cf5f`: `Not-null check failed: NewXmlStream`

## pseudocode

```c
__int64 __fastcall RtlCreateUpdatedMicrodomAsUtf8(CMicrodomUpdateContext *a1, int a2, __int64 a3)
{
  const char *v4; // rax
  int UpdatedXml; // edi
  __int64 v7; // xmm2_8
  const char *v8; // [rsp+20h] [rbp-50h] BYREF
  const char *v9; // [rsp+28h] [rbp-48h]
  __int64 v10; // [rsp+30h] [rbp-40h]
  const char *v11; // [rsp+38h] [rbp-38h]
  int v12; // [rsp+40h] [rbp-30h] BYREF
  __int128 v13; // [rsp+48h] [rbp-28h] BYREF
  __int64 v14; // [rsp+58h] [rbp-18h]

  v12 = 0;
  if ( a3 )
  {
    *(_OWORD *)a3 = 0;
    *(_QWORD *)(a3 + 16) = 0;
  }
  if ( !a1 )
  {
    v10 = 2129;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlCreateUpdatedMicrodomAsUtf8";
    v4 = "RtlIsMicrodomUpdateContextValid(TheContext)";
LABEL_5:
    v11 = v4;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v12,
             &v8);
  }
  if ( (a2 & 0xFFFFFFFC) != 0 )
  {
    v10 = 2130;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlCreateUpdatedMicrodomAsUtf8";
    v4 = "Valid flags check failed: ulFlags";
    goto LABEL_5;
  }
  if ( a3 )
  {
    v14 = 0;
    v13 = 0;
    UpdatedXml = CMicrodomUpdateContext::GetUpdatedXml(a1);
    if ( UpdatedXml >= 0 )
    {
      v7 = v14;
      *(_OWORD *)a3 = v13;
      UpdatedXml = 0;
      v14 = 0;
      *(_QWORD *)(a3 + 16) = v7;
      v13 = 0;
    }
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v13);
    return (unsigned int)UpdatedXml;
  }
  else
  {
    v10 = 2131;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlCreateUpdatedMicrodomAsUtf8";
    v11 = "Not-null check failed: NewXmlStream";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v12,
             &v8);
  }
}

```

## disassembly

```asm
0x18005ce90  push    rbp
0x18005ce92  push    rbx
0x18005ce93  push    rdi
0x18005ce94  mov     rbp, rsp
0x18005ce97  sub     rsp, 70h
0x18005ce9b  mov     rax, cs:__security_cookie
0x18005cea2  xor     rax, rsp
0x18005cea5  mov     [rbp+var_10], rax
0x18005cea9  xor     eax, eax
0x18005ceab  mov     [rbp+var_30], 0
0x18005ceb2  mov     rbx, r8
0x18005ceb5  xorps   xmm0, xmm0
0x18005ceb8  test    r8, r8
0x18005cebb  jz      short loc_18005CEC5
0x18005cebd  movups  xmmword ptr [r8], xmm0
0x18005cec1  mov     [r8+10h], rax
0x18005cec5  test    rcx, rcx
0x18005cec8  jnz     short loc_18005CF05
0x18005ceca  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005ced1  mov     [rbp+var_40], 851h
0x18005ced9  mov     [rbp+var_50], rax
0x18005cedd  lea     rax, aWindowsUdomRtl_10; "Windows::uDom::Rtl::RtlCreateUpdatedMic"...
0x18005cee4  mov     [rbp+var_48], rax
0x18005cee8  lea     rax, aRtlismicrodomu; "RtlIsMicrodomUpdateContextValid(TheCont"...
0x18005ceef  lea     rdx, [rbp+var_50]
0x18005cef3  mov     [rbp+var_38], rax
0x18005cef7  lea     rcx, [rbp+var_30]
0x18005cefb  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005cf00  jmp     loc_18005CFB9
0x18005cf05  test    edx, 0FFFFFFFCh
0x18005cf0b  jz      short loc_18005CF34
0x18005cf0d  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005cf14  mov     [rbp+var_40], 852h
0x18005cf1c  mov     [rbp+var_50], rax
0x18005cf20  lea     rax, aWindowsUdomRtl_10; "Windows::uDom::Rtl::RtlCreateUpdatedMic"...
0x18005cf27  mov     [rbp+var_48], rax
0x18005cf2b  lea     rax, aValidFlagsChec_1; "Valid flags check failed: ulFlags"
0x18005cf32  jmp     short loc_18005CEEF
0x18005cf34  test    rbx, rbx
0x18005cf37  jnz     short loc_18005CF71
0x18005cf39  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005cf40  mov     [rbp+var_40], 853h
0x18005cf48  mov     [rbp+var_50], rax
0x18005cf4c  lea     rdx, [rbp+var_50]
0x18005cf50  lea     rax, aWindowsUdomRtl_10; "Windows::uDom::Rtl::RtlCreateUpdatedMic"...
0x18005cf57  mov     [rbp+var_48], rax
0x18005cf5b  lea     rcx, [rbp+var_30]
0x18005cf5f  lea     rax, aNotNullCheckFa_21; "Not-null check failed: NewXmlStream"
0x18005cf66  mov     [rbp+var_38], rax
0x18005cf6a  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005cf6f  jmp     short loc_18005CFB9
0x18005cf71  xorps   xmm0, xmm0
0x18005cf74  mov     [rbp+var_18], rax
0x18005cf78  mov     r8d, edx
0x18005cf7b  lea     rdx, [rbp+var_28]
0x18005cf7f  movups  [rbp+var_28], xmm0
0x18005cf83  call    ?GetUpdatedXml@CMicrodomUpdateContext@@QEAAJPEAV?$Auto@U_LUTF8_STRING@@@Windows@@K@Z; CMicrodomUpdateContext::GetUpdatedXml(Windows::Auto<_LUTF8_STRING> *,ulong)
0x18005cf88  mov     edi, eax
0x18005cf8a  test    eax, eax
0x18005cf8c  js      short loc_18005CFAE
0x18005cf8e  movups  xmm1, [rbp+var_28]
0x18005cf92  xor     eax, eax
0x18005cf94  movsd   xmm2, [rbp+var_18]
0x18005cf99  xorps   xmm0, xmm0
0x18005cf9c  movups  xmmword ptr [rbx], xmm1
0x18005cf9f  xor     edi, edi
0x18005cfa1  mov     [rbp+var_18], rax
0x18005cfa5  movsd   qword ptr [rbx+10h], xmm2
0x18005cfaa  movups  [rbp+var_28], xmm0
0x18005cfae  lea     rcx, [rbp+var_28]
0x18005cfb2  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18005cfb7  mov     eax, edi
0x18005cfb9  mov     rcx, [rbp+var_10]
0x18005cfbd  xor     rcx, rsp; StackCookie
0x18005cfc0  call    __security_check_cookie
0x18005cfc5  add     rsp, 70h
0x18005cfc9  pop     rdi
0x18005cfca  pop     rbx
0x18005cfcb  pop     rbp
0x18005cfcc  retn
```
