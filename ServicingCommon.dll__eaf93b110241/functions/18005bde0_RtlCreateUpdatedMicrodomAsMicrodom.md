# RtlCreateUpdatedMicrodomAsMicrodom

- ea: `0x18005bde0`
- end: `0x18005bf08`
- name: `RtlCreateUpdatedMicrodomAsMicrodom`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002564`
- `0x18001f4ac`
- `0x1800293a0`
- `0x180058630`
- `0x18005bde0`
- `0x18005bf10`

## string_xrefs

- `0x18005be1c`: `onecore\base\xml\udom_modify.cpp`
- `0x18005be59`: `onecore\base\xml\udom_modify.cpp`
- `0x18005be7f`: `RtlIsMicrodomUpdateContextValid(TheContext)`
- `0x18005be33`: `Windows::uDom::Rtl::RtlCreateUpdatedMicrodomAsMicrodom`
- `0x18005be70`: `Windows::uDom::Rtl::RtlCreateUpdatedMicrodomAsMicrodom`

## pseudocode

```c
__int64 __fastcall RtlCreateUpdatedMicrodomAsMicrodom(CMicrodomUpdateContext *a1, int a2, __int64 a3)
{
  int UpdatedMicrodomAsUtf8; // eax
  unsigned int v5; // ebx
  _QWORD v7[4]; // [rsp+20h] [rbp-49h] BYREF
  _QWORD v8[4]; // [rsp+40h] [rbp-29h] BYREF
  _DWORD v9[2]; // [rsp+60h] [rbp-9h] BYREF
  __int128 *v10; // [rsp+68h] [rbp-1h]
  __int64 v11; // [rsp+80h] [rbp+17h]
  __int64 v12; // [rsp+88h] [rbp+1Fh]
  __int16 v13; // [rsp+90h] [rbp+27h]
  char v14; // [rsp+92h] [rbp+29h]
  int v15; // [rsp+98h] [rbp+2Fh] BYREF
  __int128 v16; // [rsp+A0h] [rbp+37h] BYREF
  __int64 v17; // [rsp+B0h] [rbp+47h]

  v15 = 0;
  v17 = 0;
  v16 = 0;
  if ( a3 )
  {
    if ( a1 )
    {
      UpdatedMicrodomAsUtf8 = RtlCreateUpdatedMicrodomAsUtf8(a1, a2, (__int64)&v16);
      if ( UpdatedMicrodomAsUtf8 >= 0 )
      {
        v13 = 0;
        v9[1] = 1;
        v9[0] = 1;
        v14 = 0;
        v10 = &v16;
        v12 = 0;
        v11 = 0;
        UpdatedMicrodomAsUtf8 = RtlCreateMicrodom((__int64)v9, a3);
        if ( UpdatedMicrodomAsUtf8 >= 0 )
        {
          v5 = 0;
          goto LABEL_9;
        }
      }
    }
    else
    {
      v8[2] = 2155;
      v8[0] = "onecore\\base\\xml\\udom_modify.cpp";
      v8[1] = "Windows::uDom::Rtl::RtlCreateUpdatedMicrodomAsMicrodom";
      v8[3] = "RtlIsMicrodomUpdateContextValid(TheContext)";
      UpdatedMicrodomAsUtf8 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
                                &v15,
                                v8);
    }
  }
  else
  {
    v7[2] = 2154;
    v7[0] = "onecore\\base\\xml\\udom_modify.cpp";
    v7[1] = "Windows::uDom::Rtl::RtlCreateUpdatedMicrodomAsMicrodom";
    v7[3] = "Not-null check failed: NewMicrodom";
    UpdatedMicrodomAsUtf8 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
                              &v15,
                              v7);
  }
  v5 = UpdatedMicrodomAsUtf8;
LABEL_9:
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v16);
  return v5;
}

```

## disassembly

```asm
0x18005bde0  mov     [rsp-8+arg_18], rbx
0x18005bde5  push    rbp
0x18005bde6  lea     rbp, [rsp-57h]
0x18005bdeb  sub     rsp, 0C0h
0x18005bdf2  mov     rax, cs:__security_cookie
0x18005bdf9  xor     rax, rsp
0x18005bdfc  mov     [rbp+57h+var_8], rax
0x18005be00  xor     eax, eax
0x18005be02  mov     [rbp+57h+var_28], 0
0x18005be09  mov     [rbp+57h+var_10], rax
0x18005be0d  xorps   xmm0, xmm0
0x18005be10  mov     rbx, r8
0x18005be13  movups  [rbp+57h+var_20], xmm0
0x18005be17  test    r8, r8
0x18005be1a  jnz     short loc_18005BE54
0x18005be1c  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005be23  mov     [rbp+57h+var_90], 86Ah
0x18005be2b  mov     [rbp+57h+var_A0], rax
0x18005be2f  lea     rdx, [rbp+57h+var_A0]
0x18005be33  lea     rax, aWindowsUdomRtl_0; "Windows::uDom::Rtl::RtlCreateUpdatedMic"...
0x18005be3a  mov     [rbp+57h+var_98], rax
0x18005be3e  lea     rcx, [rbp+57h+var_28]
0x18005be42  lea     rax, aNotNullCheckFa_31; "Not-null check failed: NewMicrodom"
0x18005be49  mov     [rbp+57h+var_88], rax
0x18005be4d  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005be52  jmp     short loc_18005BE8F
0x18005be54  test    rcx, rcx
0x18005be57  jnz     short loc_18005BE93
0x18005be59  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005be60  mov     [rbp+57h+var_70], 86Bh
0x18005be68  mov     [rbp+57h+var_80], rax
0x18005be6c  lea     rdx, [rbp+57h+var_80]
0x18005be70  lea     rax, aWindowsUdomRtl_0; "Windows::uDom::Rtl::RtlCreateUpdatedMic"...
0x18005be77  mov     [rbp+57h+var_78], rax
0x18005be7b  lea     rcx, [rbp+57h+var_28]
0x18005be7f  lea     rax, aRtlismicrodomu; "RtlIsMicrodomUpdateContextValid(TheCont"...
0x18005be86  mov     [rbp+57h+var_68], rax
0x18005be8a  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005be8f  mov     ebx, eax
0x18005be91  jmp     short loc_18005BEDF
0x18005be93  lea     r8, [rbp+57h+var_20]
0x18005be97  call    RtlCreateUpdatedMicrodomAsUtf8
0x18005be9c  test    eax, eax
0x18005be9e  js      short loc_18005BE8F
0x18005bea0  mov     eax, 1
0x18005bea5  mov     [rbp+57h+var_30], 0
0x18005beab  mov     [rbp+57h+var_5C], eax
0x18005beae  lea     rcx, [rbp+57h+var_60]
0x18005beb2  mov     [rbp+57h+var_60], eax
0x18005beb5  mov     rdx, rbx
0x18005beb8  lea     rax, [rbp+57h+var_20]
0x18005bebc  mov     [rbp+57h+var_2E], 0
0x18005bec0  mov     [rbp+57h+var_58], rax
0x18005bec4  mov     [rbp+57h+var_38], 0
0x18005becc  mov     [rbp+57h+var_40], 0
0x18005bed4  call    RtlCreateMicrodom
0x18005bed9  test    eax, eax
0x18005bedb  js      short loc_18005BE8F
0x18005bedd  xor     ebx, ebx
0x18005bedf  lea     rcx, [rbp+57h+var_20]
0x18005bee3  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18005bee8  mov     eax, ebx
0x18005beea  mov     rcx, [rbp+57h+var_8]
0x18005beee  xor     rcx, rsp; StackCookie
0x18005bef1  call    __security_check_cookie
0x18005bef6  mov     rbx, [rsp+0C0h+arg_18]
0x18005befe  add     rsp, 0C0h
0x18005bf05  pop     rbp
0x18005bf06  retn
```
