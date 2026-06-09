# RtlCreateMicrodomUpdateContext

- ea: `0x18005bc50`
- end: `0x18005bdcd`
- name: `RtlCreateMicrodomUpdateContext`
- size: `381`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18001f4ac`
- `0x18001f554`
- `0x1800293a0`
- `0x180058f64`
- `0x180059144`
- `0x180059bb8`
- `0x18005bc50`

## string_xrefs

- `0x18005bc8d`: `onecore\base\xml\udom_modify.cpp`
- `0x18005bccd`: `onecore\base\xml\udom_modify.cpp`
- `0x18005bcf9`: `onecore\base\xml\udom_modify.cpp`
- `0x18005bd47`: `onecore\base\xml\udom_modify.cpp`
- `0x18005bca0`: `Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext`
- `0x18005bce0`: `Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext`
- `0x18005bd10`: `Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext`
- `0x18005bd5e`: `Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext`
- `0x18005bd1f`: `Not-null check failed: UpdateContext`

## pseudocode

```c
__int64 __fastcall RtlCreateMicrodomUpdateContext(
        int a1,
        struct Windows::Microdom::Rtl::IRtlMicrodom *a2,
        CMicrodomUpdateContext **a3)
{
  const char *v5; // rax
  int v7; // eax
  struct Windows::Microdom::Rtl::IRtlMicrodom *v8; // rdx
  CMicrodomUpdateContext *v9; // rdi
  unsigned int v10; // ebx
  const char *v11; // [rsp+20h] [rbp-40h] BYREF
  const char *v12; // [rsp+28h] [rbp-38h]
  __int64 v13; // [rsp+30h] [rbp-30h]
  const char *v14; // [rsp+38h] [rbp-28h]
  CMicrodomUpdateContext *v15; // [rsp+40h] [rbp-20h] BYREF
  int v16; // [rsp+48h] [rbp-18h] BYREF

  v16 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a1 )
  {
    v13 = 1423;
    v11 = "onecore\\base\\xml\\udom_modify.cpp";
    v12 = "Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext";
    v5 = "ulFlags == 0";
LABEL_5:
    v14 = v5;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v16,
             &v11);
  }
  if ( !a2 )
  {
    v13 = 1424;
    v11 = "onecore\\base\\xml\\udom_modify.cpp";
    v12 = "Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext";
    v5 = "SourceMicrodom != 0";
    goto LABEL_5;
  }
  if ( !a3 )
  {
    v13 = 1425;
    v11 = "onecore\\base\\xml\\udom_modify.cpp";
    v12 = "Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext";
    v14 = "Not-null check failed: UpdateContext";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v16,
             &v11);
  }
  v15 = 0;
  if ( Windows::AutoNewPtr<CMicrodomUpdateContext>::Allocate<>(&v15) )
  {
    v8 = a2;
    v9 = v15;
    v7 = CMicrodomUpdateContext::Construct(v15, v8);
    if ( v7 >= 0 )
    {
      *a3 = v9;
      v10 = 0;
      v15 = 0;
      goto LABEL_15;
    }
  }
  else
  {
    v13 = 1433;
    v11 = "onecore\\base\\xml\\udom_modify.cpp";
    v12 = "Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext";
    v14 = "NewContext.Allocate()";
    v7 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
           &v16,
           &v11);
  }
  v10 = v7;
LABEL_15:
  Windows::Auto<CMicrodomUpdateContext *>::~Auto<CMicrodomUpdateContext *>(&v15);
  return v10;
}

```

## disassembly

```asm
0x18005bc50  mov     [rsp-8+arg_0], rbx
0x18005bc55  mov     [rsp-8+arg_18], rdi
0x18005bc5a  push    rbp
0x18005bc5b  mov     rbp, rsp
0x18005bc5e  sub     rsp, 60h
0x18005bc62  mov     rax, cs:__security_cookie
0x18005bc69  xor     rax, rsp
0x18005bc6c  mov     [rbp+var_10], rax
0x18005bc70  mov     [rbp+var_18], 0
0x18005bc77  mov     rbx, r8
0x18005bc7a  mov     rdi, rdx
0x18005bc7d  test    r8, r8
0x18005bc80  jz      short loc_18005BC89
0x18005bc82  mov     qword ptr [r8], 0
0x18005bc89  test    ecx, ecx
0x18005bc8b  jz      short loc_18005BCC8
0x18005bc8d  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005bc94  mov     [rbp+var_30], 58Fh
0x18005bc9c  mov     [rbp+var_40], rax
0x18005bca0  lea     rax, aWindowsUdomRtl_6; "Windows::uDom::Rtl::RtlCreateMicrodomUp"...
0x18005bca7  mov     [rbp+var_38], rax
0x18005bcab  lea     rax, aUlflags0; "ulFlags == 0"
0x18005bcb2  lea     rdx, [rbp+var_40]
0x18005bcb6  mov     [rbp+var_28], rax
0x18005bcba  lea     rcx, [rbp+var_18]
0x18005bcbe  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005bcc3  jmp     loc_18005BDAE
0x18005bcc8  test    rdi, rdi
0x18005bccb  jnz     short loc_18005BCF4
0x18005bccd  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005bcd4  mov     [rbp+var_30], 590h
0x18005bcdc  mov     [rbp+var_40], rax
0x18005bce0  lea     rax, aWindowsUdomRtl_6; "Windows::uDom::Rtl::RtlCreateMicrodomUp"...
0x18005bce7  mov     [rbp+var_38], rax
0x18005bceb  lea     rax, aSourcemicrodom; "SourceMicrodom != 0"
0x18005bcf2  jmp     short loc_18005BCB2
0x18005bcf4  test    rbx, rbx
0x18005bcf7  jnz     short loc_18005BD31
0x18005bcf9  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005bd00  mov     [rbp+var_30], 591h
0x18005bd08  mov     [rbp+var_40], rax
0x18005bd0c  lea     rdx, [rbp+var_40]
0x18005bd10  lea     rax, aWindowsUdomRtl_6; "Windows::uDom::Rtl::RtlCreateMicrodomUp"...
0x18005bd17  mov     [rbp+var_38], rax
0x18005bd1b  lea     rcx, [rbp+var_18]
0x18005bd1f  lea     rax, aNotNullCheckFa_36; "Not-null check failed: UpdateContext"
0x18005bd26  mov     [rbp+var_28], rax
0x18005bd2a  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005bd2f  jmp     short loc_18005BDAE
0x18005bd31  lea     rcx, [rbp+var_20]
0x18005bd35  mov     [rbp+var_20], 0
0x18005bd3d  call    ??$Allocate@$$V@?$AutoNewPtr@VCMicrodomUpdateContext@@@Windows@@QEAAPEAVCMicrodomUpdateContext@@XZ; Windows::AutoNewPtr<CMicrodomUpdateContext>::Allocate<>(void)
0x18005bd42  test    rax, rax
0x18005bd45  jnz     short loc_18005BD7F
0x18005bd47  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005bd4e  mov     [rbp+var_30], 599h
0x18005bd56  mov     [rbp+var_40], rax
0x18005bd5a  lea     rdx, [rbp+var_40]
0x18005bd5e  lea     rax, aWindowsUdomRtl_6; "Windows::uDom::Rtl::RtlCreateMicrodomUp"...
0x18005bd65  mov     [rbp+var_38], rax
0x18005bd69  lea     rcx, [rbp+var_18]
0x18005bd6d  lea     rax, aNewcontextAllo; "NewContext.Allocate()"
0x18005bd74  mov     [rbp+var_28], rax
0x18005bd78  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005bd7d  jmp     short loc_18005BD92
0x18005bd7f  mov     rdx, rdi; struct Windows::Microdom::Rtl::IRtlMicrodom *
0x18005bd82  mov     rdi, [rbp+var_20]
0x18005bd86  mov     rcx, rdi; this
0x18005bd89  call    ?Construct@CMicrodomUpdateContext@@QEAAJPEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Z; CMicrodomUpdateContext::Construct(Windows::Microdom::Rtl::IRtlMicrodom *)
0x18005bd8e  test    eax, eax
0x18005bd90  jns     short loc_18005BD96
0x18005bd92  mov     ebx, eax
0x18005bd94  jmp     short loc_18005BDA3
0x18005bd96  mov     [rbx], rdi
0x18005bd99  xor     ebx, ebx
0x18005bd9b  mov     [rbp+var_20], 0
0x18005bda3  lea     rcx, [rbp+var_20]
0x18005bda7  call    ??1?$Auto@PEAVCMicrodomUpdateContext@@@Windows@@QEAA@XZ; Windows::Auto<CMicrodomUpdateContext *>::~Auto<CMicrodomUpdateContext *>(void)
0x18005bdac  mov     eax, ebx
0x18005bdae  mov     rcx, [rbp+var_10]
0x18005bdb2  xor     rcx, rsp; StackCookie
0x18005bdb5  call    __security_check_cookie
0x18005bdba  lea     r11, [rsp+60h+var_s0]
0x18005bdbf  mov     rbx, [r11+10h]
0x18005bdc3  mov     rdi, [r11+28h]
0x18005bdc7  mov     rsp, r11
0x18005bdca  pop     rbp
0x18005bdcb  retn
```
