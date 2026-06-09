# RtlCreateMicrodomUpdateContext

- ea: `0x18005cba0`
- end: `0x18005cd56`
- name: `RtlCreateMicrodomUpdateContext`
- size: `438`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18001f1d8`
- `0x1800217cc`
- `0x180026dc0`
- `0x18002d2b0`
- `0x18005a128`
- `0x18005ab04`
- `0x18005cba0`

## string_xrefs

- `0x18005cbda`: `onecore\base\xml\udom_modify.cpp`
- `0x18005cc1a`: `onecore\base\xml\udom_modify.cpp`
- `0x18005cc46`: `onecore\base\xml\udom_modify.cpp`
- `0x18005ccd6`: `onecore\base\xml\udom_modify.cpp`
- `0x18005cbed`: `Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext`
- `0x18005cc2d`: `Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext`
- `0x18005cc5d`: `Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext`
- `0x18005cced`: `Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext`
- `0x18005cc6c`: `Not-null check failed: UpdateContext`

## pseudocode

```c
__int64 __fastcall RtlCreateMicrodomUpdateContext(
        int a1,
        struct Windows::Microdom::Rtl::IRtlMicrodom *a2,
        CMicrodomUpdateContext **a3)
{
  const char *v5; // rax
  CMicrodomUpdateContext *v7; // rax
  CMicrodomUpdateContext *v8; // rbx
  int v9; // eax
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
  v7 = (CMicrodomUpdateContext *)operator new(0x40u);
  v8 = v7;
  if ( v7 )
  {
    *(_QWORD *)v7 = 0;
    *((_QWORD *)v7 + 4) = 0;
    *((_QWORD *)v7 + 1) = (char *)v7 + 8;
    *((_QWORD *)v7 + 2) = (char *)v7 + 8;
    *((_QWORD *)v7 + 3) = (char *)v7 + 8;
    *((_QWORD *)v7 + 5) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *((_QWORD *)v7 + 7) = 0;
  }
  else
  {
    v8 = 0;
  }
  v15 = v8;
  if ( v8 )
  {
    v9 = CMicrodomUpdateContext::Construct(v8, a2);
    if ( v9 >= 0 )
    {
      *a3 = v8;
      v10 = 0;
      v15 = 0;
      goto LABEL_18;
    }
  }
  else
  {
    v13 = 1433;
    v11 = "onecore\\base\\xml\\udom_modify.cpp";
    v12 = "Windows::uDom::Rtl::RtlCreateMicrodomUpdateContext";
    v14 = "NewContext.Allocate()";
    v9 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
           &v16,
           &v11);
  }
  v10 = v9;
LABEL_18:
  Windows::Auto<CMicrodomUpdateContext *>::~Auto<CMicrodomUpdateContext *>(&v15);
  return v10;
}

```

## disassembly

```asm
0x18005cba0  mov     [rsp-18h+arg_0], rbx
0x18005cba5  push    rbp
0x18005cba6  push    rsi
0x18005cba7  push    rdi
0x18005cba8  mov     rbp, rsp
0x18005cbab  sub     rsp, 60h
0x18005cbaf  mov     rax, cs:__security_cookie
0x18005cbb6  xor     rax, rsp
0x18005cbb9  mov     [rbp+var_10], rax
0x18005cbbd  mov     [rbp+var_18], 0
0x18005cbc4  mov     rdi, r8
0x18005cbc7  mov     rsi, rdx
0x18005cbca  test    r8, r8
0x18005cbcd  jz      short loc_18005CBD6
0x18005cbcf  mov     qword ptr [r8], 0
0x18005cbd6  test    ecx, ecx
0x18005cbd8  jz      short loc_18005CC15
0x18005cbda  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005cbe1  mov     [rbp+var_30], 58Fh
0x18005cbe9  mov     [rbp+var_40], rax
0x18005cbed  lea     rax, aWindowsUdomRtl_6; "Windows::uDom::Rtl::RtlCreateMicrodomUp"...
0x18005cbf4  mov     [rbp+var_38], rax
0x18005cbf8  lea     rax, aUlflags0; "ulFlags == 0"
0x18005cbff  lea     rdx, [rbp+var_40]
0x18005cc03  mov     [rbp+var_28], rax
0x18005cc07  lea     rcx, [rbp+var_18]
0x18005cc0b  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005cc10  jmp     loc_18005CD39
0x18005cc15  test    rsi, rsi
0x18005cc18  jnz     short loc_18005CC41
0x18005cc1a  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005cc21  mov     [rbp+var_30], 590h
0x18005cc29  mov     [rbp+var_40], rax
0x18005cc2d  lea     rax, aWindowsUdomRtl_6; "Windows::uDom::Rtl::RtlCreateMicrodomUp"...
0x18005cc34  mov     [rbp+var_38], rax
0x18005cc38  lea     rax, aSourcemicrodom; "SourceMicrodom != 0"
0x18005cc3f  jmp     short loc_18005CBFF
0x18005cc41  test    rdi, rdi
0x18005cc44  jnz     short loc_18005CC81
0x18005cc46  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005cc4d  mov     [rbp+var_30], 591h
0x18005cc55  mov     [rbp+var_40], rax
0x18005cc59  lea     rdx, [rbp+var_40]
0x18005cc5d  lea     rax, aWindowsUdomRtl_6; "Windows::uDom::Rtl::RtlCreateMicrodomUp"...
0x18005cc64  mov     [rbp+var_38], rax
0x18005cc68  lea     rcx, [rbp+var_18]
0x18005cc6c  lea     rax, aNotNullCheckFa_36; "Not-null check failed: UpdateContext"
0x18005cc73  mov     [rbp+var_28], rax
0x18005cc77  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005cc7c  jmp     loc_18005CD39
0x18005cc81  mov     ecx, 40h ; '@'; Size
0x18005cc86  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005cc8b  mov     rbx, rax
0x18005cc8e  test    rax, rax
0x18005cc91  jz      short loc_18005CCCB
0x18005cc93  mov     qword ptr [rax], 0
0x18005cc9a  lea     rcx, [rax+8]
0x18005cc9e  mov     qword ptr [rcx+18h], 0
0x18005cca6  mov     [rcx], rcx
0x18005cca9  mov     [rcx+8], rcx
0x18005ccad  mov     [rcx+10h], rcx
0x18005ccb1  mov     qword ptr [rax+28h], 0
0x18005ccb9  mov     qword ptr [rax+30h], 0
0x18005ccc1  mov     qword ptr [rax+38h], 0
0x18005ccc9  jmp     short loc_18005CCCD
0x18005cccb  xor     ebx, ebx
0x18005cccd  mov     [rbp+var_20], rbx
0x18005ccd1  test    rbx, rbx
0x18005ccd4  jnz     short loc_18005CD0E
0x18005ccd6  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005ccdd  mov     [rbp+var_30], 599h
0x18005cce5  mov     [rbp+var_40], rax
0x18005cce9  lea     rdx, [rbp+var_40]
0x18005cced  lea     rax, aWindowsUdomRtl_6; "Windows::uDom::Rtl::RtlCreateMicrodomUp"...
0x18005ccf4  mov     [rbp+var_38], rax
0x18005ccf8  lea     rcx, [rbp+var_18]
0x18005ccfc  lea     rax, aNewcontextAllo; "NewContext.Allocate()"
0x18005cd03  mov     [rbp+var_28], rax
0x18005cd07  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005cd0c  jmp     short loc_18005CD1D
0x18005cd0e  mov     rdx, rsi; struct Windows::Microdom::Rtl::IRtlMicrodom *
0x18005cd11  mov     rcx, rbx; this
0x18005cd14  call    ?Construct@CMicrodomUpdateContext@@QEAAJPEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Z; CMicrodomUpdateContext::Construct(Windows::Microdom::Rtl::IRtlMicrodom *)
0x18005cd19  test    eax, eax
0x18005cd1b  jns     short loc_18005CD21
0x18005cd1d  mov     ebx, eax
0x18005cd1f  jmp     short loc_18005CD2E
0x18005cd21  mov     [rdi], rbx
0x18005cd24  xor     ebx, ebx
0x18005cd26  mov     [rbp+var_20], 0
0x18005cd2e  lea     rcx, [rbp+var_20]
0x18005cd32  call    ??1?$Auto@PEAVCMicrodomUpdateContext@@@Windows@@QEAA@XZ; Windows::Auto<CMicrodomUpdateContext *>::~Auto<CMicrodomUpdateContext *>(void)
0x18005cd37  mov     eax, ebx
0x18005cd39  mov     rcx, [rbp+var_10]
0x18005cd3d  xor     rcx, rsp; StackCookie
0x18005cd40  call    __security_check_cookie
0x18005cd45  mov     rbx, [rsp+60h+arg_0]
0x18005cd4d  add     rsp, 60h
0x18005cd51  pop     rdi
0x18005cd52  pop     rsi
0x18005cd53  pop     rbp
0x18005cd54  retn
```
