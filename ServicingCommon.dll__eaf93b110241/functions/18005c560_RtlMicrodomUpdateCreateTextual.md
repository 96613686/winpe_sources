# RtlMicrodomUpdateCreateTextual

- ea: `0x18005c560`
- end: `0x18005c6ab`
- name: `RtlMicrodomUpdateCreateTextual`
- size: `331`
- prototype: `__int64 __fastcall(CMicrodomUpdateContext *this, struct _LUTF8_STRING *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000f860`
- `0x18001f4ac`
- `0x18001fd10`
- `0x1800293a0`
- `0x18005a36c`
- `0x18005a8e4`
- `0x18005c560`

## string_xrefs

- `0x18005c5a6`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c5f1`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c61d`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c5c4`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x18005c643`: `Not-null check failed: pUpdateCookie`
- `0x18005c5b9`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateTextual`
- `0x18005c604`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateTextual`
- `0x18005c634`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateTextual`

## pseudocode

```c
__int64 __fastcall RtlMicrodomUpdateCreateTextual(
        CMicrodomUpdateContext *this,
        struct _LUTF8_STRING *a2,
        struct CChildNode **a3)
{
  const char *v6; // rax
  __int64 result; // rax
  struct CChildNode *v8; // rbx
  const char *v9; // [rsp+20h] [rbp-40h] BYREF
  const char *v10; // [rsp+28h] [rbp-38h]
  __int64 v11; // [rsp+30h] [rbp-30h]
  const char *v12; // [rsp+38h] [rbp-28h]
  struct CChildNode *v13; // [rsp+40h] [rbp-20h] BYREF
  int v14; // [rsp+48h] [rbp-18h] BYREF

  v14 = 0;
  v13 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !this )
  {
    v11 = 1534;
    v9 = "onecore\\base\\xml\\udom_modify.cpp";
    v10 = "Windows::uDom::Rtl::RtlMicrodomUpdateCreateTextual";
    v6 = "RtlIsMicrodomUpdateContextValid(HostUpdate)";
LABEL_5:
    v12 = v6;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v14,
             &v9);
  }
  if ( !a2 && !(unsigned __int8)RtlIsLUtf8StringValid(0) )
  {
    v11 = 1535;
    v9 = "onecore\\base\\xml\\udom_modify.cpp";
    v10 = "Windows::uDom::Rtl::RtlMicrodomUpdateCreateTextual";
    v6 = "(Value != 0) || RtlIsLUtf8StringValid(Value)";
    goto LABEL_5;
  }
  if ( a3 )
  {
    result = CMicrodomUpdateContext::CreateVirtualTextual(this, &v13);
    if ( (int)result >= 0 )
    {
      v8 = v13;
      if ( !v13 )
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x18005C6AALL);
      }
      result = CBasicNodeType::ForceValue(*((CBasicNodeType **)v13 + 7), a2);
      if ( (int)result >= 0 )
      {
        *a3 = v8;
        return 0;
      }
    }
  }
  else
  {
    v11 = 1536;
    v9 = "onecore\\base\\xml\\udom_modify.cpp";
    v10 = "Windows::uDom::Rtl::RtlMicrodomUpdateCreateTextual";
    v12 = "Not-null check failed: pUpdateCookie";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v14,
             &v9);
  }
  return result;
}

```

## disassembly

```asm
0x18005c560  mov     [rsp-18h+arg_18], rbx
0x18005c565  push    rbp
0x18005c566  push    rsi
0x18005c567  push    rdi
0x18005c568  mov     rbp, rsp
0x18005c56b  sub     rsp, 60h
0x18005c56f  mov     rax, cs:__security_cookie
0x18005c576  xor     rax, rsp
0x18005c579  mov     [rbp+var_10], rax
0x18005c57d  mov     [rbp+var_18], 0
0x18005c584  mov     rdi, r8
0x18005c587  mov     [rbp+var_20], 0
0x18005c58f  mov     rsi, rdx
0x18005c592  mov     rbx, rcx
0x18005c595  test    r8, r8
0x18005c598  jz      short loc_18005C5A1
0x18005c59a  mov     qword ptr [r8], 0
0x18005c5a1  test    rbx, rbx
0x18005c5a4  jnz     short loc_18005C5E1
0x18005c5a6  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c5ad  mov     [rbp+var_30], 5FEh
0x18005c5b5  mov     [rbp+var_40], rax
0x18005c5b9  lea     rax, aWindowsUdomRtl_8; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005c5c0  mov     [rbp+var_38], rax
0x18005c5c4  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18005c5cb  lea     rdx, [rbp+var_40]
0x18005c5cf  mov     [rbp+var_28], rax
0x18005c5d3  lea     rcx, [rbp+var_18]
0x18005c5d7  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005c5dc  jmp     loc_18005C683
0x18005c5e1  test    rsi, rsi
0x18005c5e4  jnz     short loc_18005C618
0x18005c5e6  xor     ecx, ecx
0x18005c5e8  call    RtlIsLUtf8StringValid
0x18005c5ed  test    al, al
0x18005c5ef  jnz     short loc_18005C618
0x18005c5f1  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c5f8  mov     [rbp+var_30], 5FFh
0x18005c600  mov     [rbp+var_40], rax
0x18005c604  lea     rax, aWindowsUdomRtl_8; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005c60b  mov     [rbp+var_38], rax
0x18005c60f  lea     rax, aValue0Rtlislut_0; "(Value != 0) || RtlIsLUtf8StringValid(V"...
0x18005c616  jmp     short loc_18005C5CB
0x18005c618  test    rdi, rdi
0x18005c61b  jnz     short loc_18005C655
0x18005c61d  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c624  mov     [rbp+var_30], 600h
0x18005c62c  mov     [rbp+var_40], rax
0x18005c630  lea     rdx, [rbp+var_40]
0x18005c634  lea     rax, aWindowsUdomRtl_8; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005c63b  mov     [rbp+var_38], rax
0x18005c63f  lea     rcx, [rbp+var_18]
0x18005c643  lea     rax, aNotNullCheckFa_53; "Not-null check failed: pUpdateCookie"
0x18005c64a  mov     [rbp+var_28], rax
0x18005c64e  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005c653  jmp     short loc_18005C683
0x18005c655  lea     rdx, [rbp+var_20]; struct CChildNode **
0x18005c659  mov     rcx, rbx; this
0x18005c65c  call    ?CreateVirtualTextual@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::CreateVirtualTextual(CChildNode * &)
0x18005c661  test    eax, eax
0x18005c663  js      short loc_18005C683
0x18005c665  mov     rbx, [rbp+var_20]
0x18005c669  test    rbx, rbx
0x18005c66c  jz      short loc_18005C6A0
0x18005c66e  mov     rcx, [rbx+38h]; this
0x18005c672  mov     rdx, rsi; struct _LUTF8_STRING *
0x18005c675  call    ?ForceValue@CBasicNodeType@@QEAAJPEBU_LUTF8_STRING@@@Z; CBasicNodeType::ForceValue(_LUTF8_STRING const *)
0x18005c67a  test    eax, eax
0x18005c67c  js      short loc_18005C683
0x18005c67e  mov     [rdi], rbx
0x18005c681  xor     eax, eax
0x18005c683  mov     rcx, [rbp+var_10]
0x18005c687  xor     rcx, rsp; StackCookie
0x18005c68a  call    __security_check_cookie
0x18005c68f  mov     rbx, [rsp+60h+arg_18]
0x18005c697  add     rsp, 60h
0x18005c69b  pop     rdi
0x18005c69c  pop     rsi
0x18005c69d  pop     rbp
0x18005c69e  retn
0x18005c6a0  mov     ecx, 0C00000E5h; int
0x18005c6a5  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
