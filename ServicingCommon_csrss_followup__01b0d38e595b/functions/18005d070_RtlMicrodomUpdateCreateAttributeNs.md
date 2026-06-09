# RtlMicrodomUpdateCreateAttributeNs

- ea: `0x18005d070`
- end: `0x18005d23f`
- name: `RtlMicrodomUpdateCreateAttributeNs`
- size: `463`
- prototype: `__int64 __fastcall(CMicrodomUpdateContext *this, struct _LUTF8_STRING *, struct _LUTF8_STRING *, struct _LUTF8_STRING *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002630`
- `0x18001f1d8`
- `0x18002d2b0`
- `0x18005aea0`
- `0x18005b70c`
- `0x18005d070`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18005d1fd`
- `ntdll!RtlRaiseStatus` at `0x18005d1fd`

## string_xrefs

- `0x18005d0be`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d10a`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d142`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d178`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d1a7`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d0dc`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x18005d1cd`: `Not-null check failed: pUpdateCookie`
- `0x18005d0d1`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateAttributeNs`
- `0x18005d11d`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateAttributeNs`
- `0x18005d155`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateAttributeNs`
- `0x18005d18b`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateAttributeNs`
- `0x18005d1be`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateAttributeNs`

## pseudocode

```c
__int64 __fastcall RtlMicrodomUpdateCreateAttributeNs(
        CMicrodomUpdateContext *this,
        struct _LUTF8_STRING *a2,
        struct _LUTF8_STRING *a3,
        struct _LUTF8_STRING *a4,
        struct CChildNode **a5)
{
  const char *v9; // rax
  __int64 result; // rax
  struct CChildNode *v11; // rbx
  const char *v12; // [rsp+20h] [rbp-48h] BYREF
  const char *v13; // [rsp+28h] [rbp-40h]
  __int64 v14; // [rsp+30h] [rbp-38h]
  const char *v15; // [rsp+38h] [rbp-30h]
  struct CChildNode *v16; // [rsp+40h] [rbp-28h] BYREF
  int v17; // [rsp+48h] [rbp-20h] BYREF

  v17 = 0;
  v16 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !this )
  {
    v14 = 1566;
    v12 = "onecore\\base\\xml\\udom_modify.cpp";
    v13 = "Windows::uDom::Rtl::RtlMicrodomUpdateCreateAttributeNs";
    v9 = "RtlIsMicrodomUpdateContextValid(HostUpdate)";
LABEL_5:
    v15 = v9;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v17,
             &v12);
  }
  if ( a2 && !(unsigned __int8)RtlIsLUtf8StringValid(a2) )
  {
    v14 = 1567;
    v12 = "onecore\\base\\xml\\udom_modify.cpp";
    v13 = "Windows::uDom::Rtl::RtlMicrodomUpdateCreateAttributeNs";
    v9 = "(Namespace == 0) || RtlIsLUtf8StringValid(Namespace)";
    goto LABEL_5;
  }
  if ( a3 && !(unsigned __int8)RtlIsLUtf8StringValid(a3) )
  {
    v14 = 1568;
    v12 = "onecore\\base\\xml\\udom_modify.cpp";
    v13 = "Windows::uDom::Rtl::RtlMicrodomUpdateCreateAttributeNs";
    v9 = "(Prefix == 0) || RtlIsLUtf8StringValid(Prefix)";
    goto LABEL_5;
  }
  if ( !(unsigned __int8)RtlIsLUtf8StringValid(a4) )
  {
    v14 = 1569;
    v12 = "onecore\\base\\xml\\udom_modify.cpp";
    v13 = "Windows::uDom::Rtl::RtlMicrodomUpdateCreateAttributeNs";
    v9 = "RtlIsLUtf8StringValid(LocalName)";
    goto LABEL_5;
  }
  if ( a5 )
  {
    result = CMicrodomUpdateContext::CreateVirtualAttribute(this, &v16);
    if ( (int)result >= 0 )
    {
      v11 = v16;
      if ( !v16 )
        RtlRaiseStatus(-1073741595);
      result = CBasicNodeType::ForceNameSetting(*((CBasicNodeType **)v16 + 7), a3, a2, a4);
      if ( (int)result >= 0 )
      {
        *a5 = v11;
        return 0;
      }
    }
  }
  else
  {
    v14 = 1570;
    v12 = "onecore\\base\\xml\\udom_modify.cpp";
    v13 = "Windows::uDom::Rtl::RtlMicrodomUpdateCreateAttributeNs";
    v15 = "Not-null check failed: pUpdateCookie";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v17,
             &v12);
  }
  return result;
}

```

## disassembly

```asm
0x18005d070  push    rbp
0x18005d072  push    rbx
0x18005d073  push    rsi
0x18005d074  push    rdi
0x18005d075  push    r14
0x18005d077  push    r15
0x18005d079  mov     rbp, rsp
0x18005d07c  sub     rsp, 68h
0x18005d080  mov     rax, cs:__security_cookie
0x18005d087  xor     rax, rsp
0x18005d08a  mov     [rbp+var_18], rax
0x18005d08e  mov     rdi, [rbp+arg_20]
0x18005d092  mov     r15, r9
0x18005d095  mov     [rbp+var_20], 0
0x18005d09c  mov     r14, r8
0x18005d09f  mov     [rbp+var_28], 0
0x18005d0a7  mov     rsi, rdx
0x18005d0aa  mov     rbx, rcx
0x18005d0ad  test    rdi, rdi
0x18005d0b0  jz      short loc_18005D0B9
0x18005d0b2  mov     qword ptr [rdi], 0
0x18005d0b9  test    rbx, rbx
0x18005d0bc  jnz     short loc_18005D0F9
0x18005d0be  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d0c5  mov     [rbp+var_38], 61Eh
0x18005d0cd  mov     [rbp+var_48], rax
0x18005d0d1  lea     rax, aWindowsUdomRtl_5; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005d0d8  mov     [rbp+var_40], rax
0x18005d0dc  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18005d0e3  lea     rdx, [rbp+var_48]
0x18005d0e7  mov     [rbp+var_30], rax
0x18005d0eb  lea     rcx, [rbp+var_20]
0x18005d0ef  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005d0f4  jmp     loc_18005D225
0x18005d0f9  test    rsi, rsi
0x18005d0fc  jz      short loc_18005D131
0x18005d0fe  mov     rcx, rsi
0x18005d101  call    RtlIsLUtf8StringValid
0x18005d106  test    al, al
0x18005d108  jnz     short loc_18005D131
0x18005d10a  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d111  mov     [rbp+var_38], 61Fh
0x18005d119  mov     [rbp+var_48], rax
0x18005d11d  lea     rax, aWindowsUdomRtl_5; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005d124  mov     [rbp+var_40], rax
0x18005d128  lea     rax, aNamespace0Rtli; "(Namespace == 0) || RtlIsLUtf8StringVal"...
0x18005d12f  jmp     short loc_18005D0E3
0x18005d131  test    r14, r14
0x18005d134  jz      short loc_18005D16C
0x18005d136  mov     rcx, r14
0x18005d139  call    RtlIsLUtf8StringValid
0x18005d13e  test    al, al
0x18005d140  jnz     short loc_18005D16C
0x18005d142  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d149  mov     [rbp+var_38], 620h
0x18005d151  mov     [rbp+var_48], rax
0x18005d155  lea     rax, aWindowsUdomRtl_5; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005d15c  mov     [rbp+var_40], rax
0x18005d160  lea     rax, aPrefix0Rtlislu; "(Prefix == 0) || RtlIsLUtf8StringValid("...
0x18005d167  jmp     loc_18005D0E3
0x18005d16c  mov     rcx, r15
0x18005d16f  call    RtlIsLUtf8StringValid
0x18005d174  test    al, al
0x18005d176  jnz     short loc_18005D1A2
0x18005d178  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d17f  mov     [rbp+var_38], 621h
0x18005d187  mov     [rbp+var_48], rax
0x18005d18b  lea     rax, aWindowsUdomRtl_5; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005d192  mov     [rbp+var_40], rax
0x18005d196  lea     rax, aRtlislutf8stri_0; "RtlIsLUtf8StringValid(LocalName)"
0x18005d19d  jmp     loc_18005D0E3
0x18005d1a2  test    rdi, rdi
0x18005d1a5  jnz     short loc_18005D1DF
0x18005d1a7  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d1ae  mov     [rbp+var_38], 622h
0x18005d1b6  mov     [rbp+var_48], rax
0x18005d1ba  lea     rdx, [rbp+var_48]
0x18005d1be  lea     rax, aWindowsUdomRtl_5; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005d1c5  mov     [rbp+var_40], rax
0x18005d1c9  lea     rcx, [rbp+var_20]
0x18005d1cd  lea     rax, aNotNullCheckFa_53; "Not-null check failed: pUpdateCookie"
0x18005d1d4  mov     [rbp+var_30], rax
0x18005d1d8  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005d1dd  jmp     short loc_18005D225
0x18005d1df  lea     rdx, [rbp+var_28]; struct CChildNode **
0x18005d1e3  mov     rcx, rbx; this
0x18005d1e6  call    ?CreateVirtualAttribute@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::CreateVirtualAttribute(CChildNode * &)
0x18005d1eb  test    eax, eax
0x18005d1ed  js      short loc_18005D225
0x18005d1ef  mov     rbx, [rbp+var_28]
0x18005d1f3  test    rbx, rbx
0x18005d1f6  jnz     short loc_18005D20A
0x18005d1f8  mov     ecx, 0C00000E5h; Status
0x18005d1fd  call    cs:__imp_RtlRaiseStatus
0x18005d204  nop     dword ptr [rax+rax+00h]
0x18005d209  int     3; Trap to Debugger
0x18005d20a  mov     rcx, [rbx+38h]; this
0x18005d20e  mov     r9, r15; struct _LUTF8_STRING *
0x18005d211  mov     r8, rsi; struct _LUTF8_STRING *
0x18005d214  mov     rdx, r14; struct _LUTF8_STRING *
0x18005d217  call    ?ForceNameSetting@CBasicNodeType@@QEAAJPEBU_LUTF8_STRING@@00@Z; CBasicNodeType::ForceNameSetting(_LUTF8_STRING const *,_LUTF8_STRING const *,_LUTF8_STRING const *)
0x18005d21c  test    eax, eax
0x18005d21e  js      short loc_18005D225
0x18005d220  mov     [rdi], rbx
0x18005d223  xor     eax, eax
0x18005d225  mov     rcx, [rbp+var_18]
0x18005d229  xor     rcx, rsp; StackCookie
0x18005d22c  call    __security_check_cookie
0x18005d231  add     rsp, 68h
0x18005d235  pop     r15
0x18005d237  pop     r14
0x18005d239  pop     rdi
0x18005d23a  pop     rsi
0x18005d23b  pop     rbx
0x18005d23c  pop     rbp
0x18005d23d  retn
```
