# RtlCreateUpdatedMicrodomAsUtf8

- ea: `0x18005bf10`
- end: `0x18005c04e`
- name: `RtlCreateUpdatedMicrodomAsUtf8`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005bde0`

## callees

- `0x180002564`
- `0x18001f4ac`
- `0x1800293a0`
- `0x18005abe4`
- `0x18005bf10`

## string_xrefs

- `0x18005bf4a`: `onecore\base\xml\udom_modify.cpp`
- `0x18005bf8d`: `onecore\base\xml\udom_modify.cpp`
- `0x18005bfb9`: `onecore\base\xml\udom_modify.cpp`
- `0x18005bf68`: `RtlIsMicrodomUpdateContextValid(TheContext)`
- `0x18005bf5d`: `Windows::uDom::Rtl::RtlCreateUpdatedMicrodomAsUtf8`
- `0x18005bfa0`: `Windows::uDom::Rtl::RtlCreateUpdatedMicrodomAsUtf8`
- `0x18005bfd0`: `Windows::uDom::Rtl::RtlCreateUpdatedMicrodomAsUtf8`
- `0x18005bfdf`: `Not-null check failed: NewXmlStream`

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
0x18005bf10  push    rbp
0x18005bf12  push    rbx
0x18005bf13  push    rdi
0x18005bf14  mov     rbp, rsp
0x18005bf17  sub     rsp, 70h
0x18005bf1b  mov     rax, cs:__security_cookie
0x18005bf22  xor     rax, rsp
0x18005bf25  mov     [rbp+var_10], rax
0x18005bf29  xor     eax, eax
0x18005bf2b  mov     [rbp+var_30], 0
0x18005bf32  mov     rbx, r8
0x18005bf35  xorps   xmm0, xmm0
0x18005bf38  test    r8, r8
0x18005bf3b  jz      short loc_18005BF45
0x18005bf3d  movups  xmmword ptr [r8], xmm0
0x18005bf41  mov     [r8+10h], rax
0x18005bf45  test    rcx, rcx
0x18005bf48  jnz     short loc_18005BF85
0x18005bf4a  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005bf51  mov     [rbp+var_40], 851h
0x18005bf59  mov     [rbp+var_50], rax
0x18005bf5d  lea     rax, aWindowsUdomRtl_10; "Windows::uDom::Rtl::RtlCreateUpdatedMic"...
0x18005bf64  mov     [rbp+var_48], rax
0x18005bf68  lea     rax, aRtlismicrodomu; "RtlIsMicrodomUpdateContextValid(TheCont"...
0x18005bf6f  lea     rdx, [rbp+var_50]
0x18005bf73  mov     [rbp+var_38], rax
0x18005bf77  lea     rcx, [rbp+var_30]
0x18005bf7b  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005bf80  jmp     loc_18005C039
0x18005bf85  test    edx, 0FFFFFFFCh
0x18005bf8b  jz      short loc_18005BFB4
0x18005bf8d  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005bf94  mov     [rbp+var_40], 852h
0x18005bf9c  mov     [rbp+var_50], rax
0x18005bfa0  lea     rax, aWindowsUdomRtl_10; "Windows::uDom::Rtl::RtlCreateUpdatedMic"...
0x18005bfa7  mov     [rbp+var_48], rax
0x18005bfab  lea     rax, aValidFlagsChec_1; "Valid flags check failed: ulFlags"
0x18005bfb2  jmp     short loc_18005BF6F
0x18005bfb4  test    rbx, rbx
0x18005bfb7  jnz     short loc_18005BFF1
0x18005bfb9  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005bfc0  mov     [rbp+var_40], 853h
0x18005bfc8  mov     [rbp+var_50], rax
0x18005bfcc  lea     rdx, [rbp+var_50]
0x18005bfd0  lea     rax, aWindowsUdomRtl_10; "Windows::uDom::Rtl::RtlCreateUpdatedMic"...
0x18005bfd7  mov     [rbp+var_48], rax
0x18005bfdb  lea     rcx, [rbp+var_30]
0x18005bfdf  lea     rax, aNotNullCheckFa_21; "Not-null check failed: NewXmlStream"
0x18005bfe6  mov     [rbp+var_38], rax
0x18005bfea  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005bfef  jmp     short loc_18005C039
0x18005bff1  xorps   xmm0, xmm0
0x18005bff4  mov     [rbp+var_18], rax
0x18005bff8  mov     r8d, edx
0x18005bffb  lea     rdx, [rbp+var_28]
0x18005bfff  movups  [rbp+var_28], xmm0
0x18005c003  call    ?GetUpdatedXml@CMicrodomUpdateContext@@QEAAJPEAV?$Auto@U_LUTF8_STRING@@@Windows@@K@Z; CMicrodomUpdateContext::GetUpdatedXml(Windows::Auto<_LUTF8_STRING> *,ulong)
0x18005c008  mov     edi, eax
0x18005c00a  test    eax, eax
0x18005c00c  js      short loc_18005C02E
0x18005c00e  movups  xmm1, [rbp+var_28]
0x18005c012  xor     eax, eax
0x18005c014  movsd   xmm2, [rbp+var_18]
0x18005c019  xorps   xmm0, xmm0
0x18005c01c  movups  xmmword ptr [rbx], xmm1
0x18005c01f  xor     edi, edi
0x18005c021  mov     [rbp+var_18], rax
0x18005c025  movsd   qword ptr [rbx+10h], xmm2
0x18005c02a  movups  [rbp+var_28], xmm0
0x18005c02e  lea     rcx, [rbp+var_28]
0x18005c032  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18005c037  mov     eax, edi
0x18005c039  mov     rcx, [rbp+var_10]
0x18005c03d  xor     rcx, rsp; StackCookie
0x18005c040  call    __security_check_cookie
0x18005c045  add     rsp, 70h
0x18005c049  pop     rdi
0x18005c04a  pop     rbx
0x18005c04b  pop     rbp
0x18005c04c  retn
```
