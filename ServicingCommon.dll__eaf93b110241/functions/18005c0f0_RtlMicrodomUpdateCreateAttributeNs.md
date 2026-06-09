# RtlMicrodomUpdateCreateAttributeNs

- ea: `0x18005c0f0`
- end: `0x18005c2b8`
- name: `RtlMicrodomUpdateCreateAttributeNs`
- size: `456`
- prototype: `__int64 __fastcall(CMicrodomUpdateContext *this, struct _LUTF8_STRING *, struct _LUTF8_STRING *, struct _LUTF8_STRING *, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000f860`
- `0x18001f4ac`
- `0x18001fd10`
- `0x1800293a0`
- `0x180059f50`
- `0x18005a774`
- `0x18005c0f0`

## string_xrefs

- `0x18005c13e`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c18a`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c1c2`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c1f8`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c227`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c15c`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x18005c24d`: `Not-null check failed: pUpdateCookie`
- `0x18005c151`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateAttributeNs`
- `0x18005c19d`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateAttributeNs`
- `0x18005c1d5`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateAttributeNs`
- `0x18005c20b`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateAttributeNs`
- `0x18005c23e`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateAttributeNs`

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
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x18005C2B7LL);
      }
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
0x18005c0f0  push    rbp
0x18005c0f2  push    rbx
0x18005c0f3  push    rsi
0x18005c0f4  push    rdi
0x18005c0f5  push    r14
0x18005c0f7  push    r15
0x18005c0f9  mov     rbp, rsp
0x18005c0fc  sub     rsp, 68h
0x18005c100  mov     rax, cs:__security_cookie
0x18005c107  xor     rax, rsp
0x18005c10a  mov     [rbp+var_18], rax
0x18005c10e  mov     rdi, [rbp+arg_20]
0x18005c112  mov     r15, r9
0x18005c115  mov     [rbp+var_20], 0
0x18005c11c  mov     r14, r8
0x18005c11f  mov     [rbp+var_28], 0
0x18005c127  mov     rsi, rdx
0x18005c12a  mov     rbx, rcx
0x18005c12d  test    rdi, rdi
0x18005c130  jz      short loc_18005C139
0x18005c132  mov     qword ptr [rdi], 0
0x18005c139  test    rbx, rbx
0x18005c13c  jnz     short loc_18005C179
0x18005c13e  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c145  mov     [rbp+var_38], 61Eh
0x18005c14d  mov     [rbp+var_48], rax
0x18005c151  lea     rax, aWindowsUdomRtl_5; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005c158  mov     [rbp+var_40], rax
0x18005c15c  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18005c163  lea     rdx, [rbp+var_48]
0x18005c167  mov     [rbp+var_30], rax
0x18005c16b  lea     rcx, [rbp+var_20]
0x18005c16f  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005c174  jmp     loc_18005C293
0x18005c179  test    rsi, rsi
0x18005c17c  jz      short loc_18005C1B1
0x18005c17e  mov     rcx, rsi
0x18005c181  call    RtlIsLUtf8StringValid
0x18005c186  test    al, al
0x18005c188  jnz     short loc_18005C1B1
0x18005c18a  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c191  mov     [rbp+var_38], 61Fh
0x18005c199  mov     [rbp+var_48], rax
0x18005c19d  lea     rax, aWindowsUdomRtl_5; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005c1a4  mov     [rbp+var_40], rax
0x18005c1a8  lea     rax, aNamespace0Rtli; "(Namespace == 0) || RtlIsLUtf8StringVal"...
0x18005c1af  jmp     short loc_18005C163
0x18005c1b1  test    r14, r14
0x18005c1b4  jz      short loc_18005C1EC
0x18005c1b6  mov     rcx, r14
0x18005c1b9  call    RtlIsLUtf8StringValid
0x18005c1be  test    al, al
0x18005c1c0  jnz     short loc_18005C1EC
0x18005c1c2  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c1c9  mov     [rbp+var_38], 620h
0x18005c1d1  mov     [rbp+var_48], rax
0x18005c1d5  lea     rax, aWindowsUdomRtl_5; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005c1dc  mov     [rbp+var_40], rax
0x18005c1e0  lea     rax, aPrefix0Rtlislu; "(Prefix == 0) || RtlIsLUtf8StringValid("...
0x18005c1e7  jmp     loc_18005C163
0x18005c1ec  mov     rcx, r15
0x18005c1ef  call    RtlIsLUtf8StringValid
0x18005c1f4  test    al, al
0x18005c1f6  jnz     short loc_18005C222
0x18005c1f8  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c1ff  mov     [rbp+var_38], 621h
0x18005c207  mov     [rbp+var_48], rax
0x18005c20b  lea     rax, aWindowsUdomRtl_5; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005c212  mov     [rbp+var_40], rax
0x18005c216  lea     rax, aRtlislutf8stri_0; "RtlIsLUtf8StringValid(LocalName)"
0x18005c21d  jmp     loc_18005C163
0x18005c222  test    rdi, rdi
0x18005c225  jnz     short loc_18005C25F
0x18005c227  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c22e  mov     [rbp+var_38], 622h
0x18005c236  mov     [rbp+var_48], rax
0x18005c23a  lea     rdx, [rbp+var_48]
0x18005c23e  lea     rax, aWindowsUdomRtl_5; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005c245  mov     [rbp+var_40], rax
0x18005c249  lea     rcx, [rbp+var_20]
0x18005c24d  lea     rax, aNotNullCheckFa_53; "Not-null check failed: pUpdateCookie"
0x18005c254  mov     [rbp+var_30], rax
0x18005c258  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005c25d  jmp     short loc_18005C293
0x18005c25f  lea     rdx, [rbp+var_28]; struct CChildNode **
0x18005c263  mov     rcx, rbx; this
0x18005c266  call    ?CreateVirtualAttribute@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::CreateVirtualAttribute(CChildNode * &)
0x18005c26b  test    eax, eax
0x18005c26d  js      short loc_18005C293
0x18005c26f  mov     rbx, [rbp+var_28]
0x18005c273  test    rbx, rbx
0x18005c276  jz      short loc_18005C2AD
0x18005c278  mov     rcx, [rbx+38h]; this
0x18005c27c  mov     r9, r15; struct _LUTF8_STRING *
0x18005c27f  mov     r8, rsi; struct _LUTF8_STRING *
0x18005c282  mov     rdx, r14; struct _LUTF8_STRING *
0x18005c285  call    ?ForceNameSetting@CBasicNodeType@@QEAAJPEBU_LUTF8_STRING@@00@Z; CBasicNodeType::ForceNameSetting(_LUTF8_STRING const *,_LUTF8_STRING const *,_LUTF8_STRING const *)
0x18005c28a  test    eax, eax
0x18005c28c  js      short loc_18005C293
0x18005c28e  mov     [rdi], rbx
0x18005c291  xor     eax, eax
0x18005c293  mov     rcx, [rbp+var_18]
0x18005c297  xor     rcx, rsp; StackCookie
0x18005c29a  call    __security_check_cookie
0x18005c29f  add     rsp, 68h
0x18005c2a3  pop     r15
0x18005c2a5  pop     r14
0x18005c2a7  pop     rdi
0x18005c2a8  pop     rsi
0x18005c2a9  pop     rbx
0x18005c2aa  pop     rbp
0x18005c2ab  retn
0x18005c2ad  mov     ecx, 0C00000E5h; int
0x18005c2b2  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
