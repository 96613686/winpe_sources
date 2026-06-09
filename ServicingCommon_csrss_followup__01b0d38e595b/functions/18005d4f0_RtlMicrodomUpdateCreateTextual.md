# RtlMicrodomUpdateCreateTextual

- ea: `0x18005d4f0`
- end: `0x18005d642`
- name: `RtlMicrodomUpdateCreateTextual`
- size: `338`
- prototype: `__int64 __fastcall(CMicrodomUpdateContext *this, struct _LUTF8_STRING *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002630`
- `0x18001f1d8`
- `0x18002d2b0`
- `0x18005b2bc`
- `0x18005b87c`
- `0x18005d4f0`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18005d603`
- `ntdll!RtlRaiseStatus` at `0x18005d603`

## string_xrefs

- `0x18005d536`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d581`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d5ad`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d554`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x18005d5d3`: `Not-null check failed: pUpdateCookie`
- `0x18005d549`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateTextual`
- `0x18005d594`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateTextual`
- `0x18005d5c4`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateTextual`

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
        RtlRaiseStatus(-1073741595);
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
0x18005d4f0  mov     [rsp-18h+arg_18], rbx
0x18005d4f5  push    rbp
0x18005d4f6  push    rsi
0x18005d4f7  push    rdi
0x18005d4f8  mov     rbp, rsp
0x18005d4fb  sub     rsp, 60h
0x18005d4ff  mov     rax, cs:__security_cookie
0x18005d506  xor     rax, rsp
0x18005d509  mov     [rbp+var_10], rax
0x18005d50d  mov     [rbp+var_18], 0
0x18005d514  mov     rdi, r8
0x18005d517  mov     [rbp+var_20], 0
0x18005d51f  mov     rsi, rdx
0x18005d522  mov     rbx, rcx
0x18005d525  test    r8, r8
0x18005d528  jz      short loc_18005D531
0x18005d52a  mov     qword ptr [r8], 0
0x18005d531  test    rbx, rbx
0x18005d534  jnz     short loc_18005D571
0x18005d536  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d53d  mov     [rbp+var_30], 5FEh
0x18005d545  mov     [rbp+var_40], rax
0x18005d549  lea     rax, aWindowsUdomRtl_8; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005d550  mov     [rbp+var_38], rax
0x18005d554  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18005d55b  lea     rdx, [rbp+var_40]
0x18005d55f  mov     [rbp+var_28], rax
0x18005d563  lea     rcx, [rbp+var_18]
0x18005d567  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005d56c  jmp     loc_18005D625
0x18005d571  test    rsi, rsi
0x18005d574  jnz     short loc_18005D5A8
0x18005d576  xor     ecx, ecx
0x18005d578  call    RtlIsLUtf8StringValid
0x18005d57d  test    al, al
0x18005d57f  jnz     short loc_18005D5A8
0x18005d581  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d588  mov     [rbp+var_30], 5FFh
0x18005d590  mov     [rbp+var_40], rax
0x18005d594  lea     rax, aWindowsUdomRtl_8; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005d59b  mov     [rbp+var_38], rax
0x18005d59f  lea     rax, aValue0Rtlislut_0; "(Value != 0) || RtlIsLUtf8StringValid(V"...
0x18005d5a6  jmp     short loc_18005D55B
0x18005d5a8  test    rdi, rdi
0x18005d5ab  jnz     short loc_18005D5E5
0x18005d5ad  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d5b4  mov     [rbp+var_30], 600h
0x18005d5bc  mov     [rbp+var_40], rax
0x18005d5c0  lea     rdx, [rbp+var_40]
0x18005d5c4  lea     rax, aWindowsUdomRtl_8; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005d5cb  mov     [rbp+var_38], rax
0x18005d5cf  lea     rcx, [rbp+var_18]
0x18005d5d3  lea     rax, aNotNullCheckFa_53; "Not-null check failed: pUpdateCookie"
0x18005d5da  mov     [rbp+var_28], rax
0x18005d5de  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005d5e3  jmp     short loc_18005D625
0x18005d5e5  lea     rdx, [rbp+var_20]; struct CChildNode **
0x18005d5e9  mov     rcx, rbx; this
0x18005d5ec  call    ?CreateVirtualTextual@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::CreateVirtualTextual(CChildNode * &)
0x18005d5f1  test    eax, eax
0x18005d5f3  js      short loc_18005D625
0x18005d5f5  mov     rbx, [rbp+var_20]
0x18005d5f9  test    rbx, rbx
0x18005d5fc  jnz     short loc_18005D610
0x18005d5fe  mov     ecx, 0C00000E5h; Status
0x18005d603  call    cs:__imp_RtlRaiseStatus
0x18005d60a  nop     dword ptr [rax+rax+00h]
0x18005d60f  int     3; Trap to Debugger
0x18005d610  mov     rcx, [rbx+38h]; this
0x18005d614  mov     rdx, rsi; struct _LUTF8_STRING *
0x18005d617  call    ?ForceValue@CBasicNodeType@@QEAAJPEBU_LUTF8_STRING@@@Z; CBasicNodeType::ForceValue(_LUTF8_STRING const *)
0x18005d61c  test    eax, eax
0x18005d61e  js      short loc_18005D625
0x18005d620  mov     [rdi], rbx
0x18005d623  xor     eax, eax
0x18005d625  mov     rcx, [rbp+var_10]
0x18005d629  xor     rcx, rsp; StackCookie
0x18005d62c  call    __security_check_cookie
0x18005d631  mov     rbx, [rsp+60h+arg_18]
0x18005d639  add     rsp, 60h
0x18005d63d  pop     rdi
0x18005d63e  pop     rsi
0x18005d63f  pop     rbp
0x18005d640  retn
```
