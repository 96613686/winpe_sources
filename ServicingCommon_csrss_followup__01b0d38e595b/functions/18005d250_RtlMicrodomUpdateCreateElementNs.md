# RtlMicrodomUpdateCreateElementNs

- ea: `0x18005d250`
- end: `0x18005d4e6`
- name: `RtlMicrodomUpdateCreateElementNs`
- size: `662`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002630`
- `0x18001f1d8`
- `0x18002d2b0`
- `0x18005aea0`
- `0x18005b178`
- `0x18005b70c`
- `0x18005c360`
- `0x18005d250`
- `0x18009e020`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18005d419`
- `ntdll!RtlRaiseStatus` at `0x18005d419`

## string_xrefs

- `0x18005d29f`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d2eb`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d323`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d357`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d38d`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d3bc`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d2b2`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs`
- `0x18005d2fe`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs`
- `0x18005d336`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs`
- `0x18005d36a`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs`
- `0x18005d3a0`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs`
- `0x18005d3d3`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs`
- `0x18005d2bd`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x18005d3e2`: `Not-null check failed: pUpdateCookie`

## pseudocode

```c
__int64 __fastcall RtlMicrodomUpdateCreateElementNs(
        char a1,
        CMicrodomUpdateContext *a2,
        const struct _LUTF8_STRING *a3,
        const struct _LUTF8_STRING *a4,
        struct _LUTF8_STRING *a5,
        struct CChildNode **a6)
{
  const char *v10; // rax
  __int64 result; // rax
  struct CChildNode *v12; // rsi
  struct CChildNode *v13; // rbx
  const struct _LUTF8_STRING *v14; // r9
  const char *v15; // [rsp+20h] [rbp-40h] BYREF
  const char *v16; // [rsp+28h] [rbp-38h]
  __int64 v17; // [rsp+30h] [rbp-30h]
  const char *v18; // [rsp+38h] [rbp-28h]
  struct CChildNode *v19; // [rsp+40h] [rbp-20h] BYREF
  int v20; // [rsp+48h] [rbp-18h] BYREF

  v20 = 0;
  v19 = 0;
  if ( a6 )
    *a6 = 0;
  if ( !a2 )
  {
    v17 = 1477;
    v15 = "onecore\\base\\xml\\udom_modify.cpp";
    v16 = "Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs";
    v10 = "RtlIsMicrodomUpdateContextValid(HostUpdate)";
LABEL_5:
    v18 = v10;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v20,
             &v15);
  }
  if ( a3 && !(unsigned __int8)RtlIsLUtf8StringValid(a3) )
  {
    v17 = 1478;
    v15 = "onecore\\base\\xml\\udom_modify.cpp";
    v16 = "Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs";
    v10 = "(Namespace == 0) || RtlIsLUtf8StringValid(Namespace)";
    goto LABEL_5;
  }
  if ( a4 && !(unsigned __int8)RtlIsLUtf8StringValid(a4) )
  {
    v17 = 1479;
    v15 = "onecore\\base\\xml\\udom_modify.cpp";
    v16 = "Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs";
    v10 = "(Prefix == 0) || RtlIsLUtf8StringValid(Prefix)";
    goto LABEL_5;
  }
  if ( !a3 && a4 )
  {
    v17 = 1480;
    v15 = "onecore\\base\\xml\\udom_modify.cpp";
    v16 = "Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs";
    v10 = "(Namespace != 0) || (Namespace == 0 && Prefix == 0)";
    goto LABEL_5;
  }
  if ( !(unsigned __int8)RtlIsLUtf8StringValid(a5) )
  {
    v17 = 1481;
    v15 = "onecore\\base\\xml\\udom_modify.cpp";
    v16 = "Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs";
    v10 = "RtlIsLUtf8StringValid(LocalName)";
    goto LABEL_5;
  }
  if ( a6 )
  {
    result = CMicrodomUpdateContext::CreateVirtualElement(a2, &v19);
    if ( (int)result >= 0 )
    {
      v12 = v19;
      if ( !v19 )
        RtlRaiseStatus(-1073741595);
      result = CBasicNodeType::ForceNameSetting(*((CBasicNodeType **)v19 + 7), a4, a3, a5);
      if ( (int)result >= 0 )
      {
        *a6 = v12;
        if ( (a1 & 1) == 0 || !a3 )
          return 0;
        v19 = 0;
        result = CMicrodomUpdateContext::CreateVirtualAttribute(a2, &v19);
        if ( (int)result >= 0 )
        {
          v13 = v19;
          v14 = a4;
          if ( !a4 )
            v14 = (const struct _LUTF8_STRING *)qword_1800A2B88;
          result = CBasicNodeType::ForceNameSetting(
                     *((CBasicNodeType **)v19 + 7),
                     (const struct _LUTF8_STRING *)((unsigned __int64)qword_1800A2B88 & -(__int64)(a4 != 0)),
                     0,
                     v14);
          if ( (int)result >= 0 )
          {
            result = (*(__int64 (__fastcall **)(_QWORD, const struct _LUTF8_STRING *))(**((_QWORD **)v13 + 7) + 72LL))(
                       *((_QWORD *)v13 + 7),
                       a3);
            if ( (int)result >= 0 )
            {
              result = CElementModification::InsertChild(*((CElementModification **)v12 + 5), v13, 0xFFFFFFFF);
              if ( (int)result >= 0 )
                return 0;
            }
          }
        }
      }
    }
  }
  else
  {
    v17 = 1482;
    v15 = "onecore\\base\\xml\\udom_modify.cpp";
    v16 = "Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs";
    v18 = "Not-null check failed: pUpdateCookie";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v20,
             &v15);
  }
  return result;
}

```

## disassembly

```asm
0x18005d250  mov     [rsp-38h+arg_0], rbx
0x18005d255  push    rbp
0x18005d256  push    rsi
0x18005d257  push    rdi
0x18005d258  push    r12
0x18005d25a  push    r13
0x18005d25c  push    r14
0x18005d25e  push    r15
0x18005d260  mov     rbp, rsp
0x18005d263  sub     rsp, 60h
0x18005d267  mov     rax, cs:__security_cookie
0x18005d26e  xor     rax, rsp
0x18005d271  mov     [rbp+var_10], rax
0x18005d275  mov     r15, [rbp+arg_28]
0x18005d279  xor     esi, esi
0x18005d27b  mov     r12, [rbp+arg_20]
0x18005d27f  mov     r14, r9
0x18005d282  mov     [rbp+var_18], esi
0x18005d285  mov     rdi, r8
0x18005d288  mov     [rbp+var_20], rsi
0x18005d28c  mov     rbx, rdx
0x18005d28f  mov     r13d, ecx
0x18005d292  test    r15, r15
0x18005d295  jz      short loc_18005D29A
0x18005d297  mov     [r15], rsi
0x18005d29a  test    rbx, rbx
0x18005d29d  jnz     short loc_18005D2DA
0x18005d29f  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d2a6  mov     [rbp+var_30], 5C5h
0x18005d2ae  mov     [rbp+var_40], rax
0x18005d2b2  lea     rax, aWindowsUdomRtl_12; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005d2b9  mov     [rbp+var_38], rax
0x18005d2bd  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18005d2c4  lea     rdx, [rbp+var_40]
0x18005d2c8  mov     [rbp+var_28], rax
0x18005d2cc  lea     rcx, [rbp+var_18]
0x18005d2d0  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005d2d5  jmp     loc_18005D4C1
0x18005d2da  test    rdi, rdi
0x18005d2dd  jz      short loc_18005D312
0x18005d2df  mov     rcx, rdi
0x18005d2e2  call    RtlIsLUtf8StringValid
0x18005d2e7  test    al, al
0x18005d2e9  jnz     short loc_18005D312
0x18005d2eb  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d2f2  mov     [rbp+var_30], 5C6h
0x18005d2fa  mov     [rbp+var_40], rax
0x18005d2fe  lea     rax, aWindowsUdomRtl_12; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005d305  mov     [rbp+var_38], rax
0x18005d309  lea     rax, aNamespace0Rtli; "(Namespace == 0) || RtlIsLUtf8StringVal"...
0x18005d310  jmp     short loc_18005D2C4
0x18005d312  test    r14, r14
0x18005d315  jz      short loc_18005D34D
0x18005d317  mov     rcx, r14
0x18005d31a  call    RtlIsLUtf8StringValid
0x18005d31f  test    al, al
0x18005d321  jnz     short loc_18005D34D
0x18005d323  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d32a  mov     [rbp+var_30], 5C7h
0x18005d332  mov     [rbp+var_40], rax
0x18005d336  lea     rax, aWindowsUdomRtl_12; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005d33d  mov     [rbp+var_38], rax
0x18005d341  lea     rax, aPrefix0Rtlislu; "(Prefix == 0) || RtlIsLUtf8StringValid("...
0x18005d348  jmp     loc_18005D2C4
0x18005d34d  test    rdi, rdi
0x18005d350  jnz     short loc_18005D381
0x18005d352  test    r14, r14
0x18005d355  jz      short loc_18005D381
0x18005d357  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d35e  mov     [rbp+var_30], 5C8h
0x18005d366  mov     [rbp+var_40], rax
0x18005d36a  lea     rax, aWindowsUdomRtl_12; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005d371  mov     [rbp+var_38], rax
0x18005d375  lea     rax, aNamespace0Name; "(Namespace != 0) || (Namespace == 0 && "...
0x18005d37c  jmp     loc_18005D2C4
0x18005d381  mov     rcx, r12
0x18005d384  call    RtlIsLUtf8StringValid
0x18005d389  test    al, al
0x18005d38b  jnz     short loc_18005D3B7
0x18005d38d  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d394  mov     [rbp+var_30], 5C9h
0x18005d39c  mov     [rbp+var_40], rax
0x18005d3a0  lea     rax, aWindowsUdomRtl_12; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005d3a7  mov     [rbp+var_38], rax
0x18005d3ab  lea     rax, aRtlislutf8stri_0; "RtlIsLUtf8StringValid(LocalName)"
0x18005d3b2  jmp     loc_18005D2C4
0x18005d3b7  test    r15, r15
0x18005d3ba  jnz     short loc_18005D3F7
0x18005d3bc  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d3c3  mov     [rbp+var_30], 5CAh
0x18005d3cb  mov     [rbp+var_40], rax
0x18005d3cf  lea     rdx, [rbp+var_40]
0x18005d3d3  lea     rax, aWindowsUdomRtl_12; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005d3da  mov     [rbp+var_38], rax
0x18005d3de  lea     rcx, [rbp+var_18]
0x18005d3e2  lea     rax, aNotNullCheckFa_53; "Not-null check failed: pUpdateCookie"
0x18005d3e9  mov     [rbp+var_28], rax
0x18005d3ed  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005d3f2  jmp     loc_18005D4C1
0x18005d3f7  lea     rdx, [rbp+var_20]; struct CChildNode **
0x18005d3fb  mov     rcx, rbx; this
0x18005d3fe  call    ?CreateVirtualElement@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::CreateVirtualElement(CChildNode * &)
0x18005d403  test    eax, eax
0x18005d405  js      loc_18005D4C1
0x18005d40b  mov     rsi, [rbp+var_20]
0x18005d40f  test    rsi, rsi
0x18005d412  jnz     short loc_18005D426
0x18005d414  mov     ecx, 0C00000E5h; Status
0x18005d419  call    cs:__imp_RtlRaiseStatus
0x18005d420  nop     dword ptr [rax+rax+00h]
0x18005d425  int     3; Trap to Debugger
0x18005d426  mov     rcx, [rsi+38h]; this
0x18005d42a  mov     r9, r12; struct _LUTF8_STRING *
0x18005d42d  mov     r8, rdi; struct _LUTF8_STRING *
0x18005d430  mov     rdx, r14; struct _LUTF8_STRING *
0x18005d433  call    ?ForceNameSetting@CBasicNodeType@@QEAAJPEBU_LUTF8_STRING@@00@Z; CBasicNodeType::ForceNameSetting(_LUTF8_STRING const *,_LUTF8_STRING const *,_LUTF8_STRING const *)
0x18005d438  test    eax, eax
0x18005d43a  js      loc_18005D4C1
0x18005d440  mov     [r15], rsi
0x18005d443  test    r13b, 1
0x18005d447  jz      short loc_18005D4BF
0x18005d449  test    rdi, rdi
0x18005d44c  jz      short loc_18005D4BF
0x18005d44e  lea     rdx, [rbp+var_20]; struct CChildNode **
0x18005d452  mov     [rbp+var_20], 0
0x18005d45a  mov     rcx, rbx; this
0x18005d45d  call    ?CreateVirtualAttribute@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::CreateVirtualAttribute(CChildNode * &)
0x18005d462  test    eax, eax
0x18005d464  js      short loc_18005D4C1
0x18005d466  mov     rbx, [rbp+var_20]
0x18005d46a  lea     rax, qword_1800A2B88
0x18005d471  test    r14, r14
0x18005d474  mov     r9, r14
0x18005d477  cmovz   r9, rax; struct _LUTF8_STRING *
0x18005d47b  neg     r14
0x18005d47e  mov     rcx, [rbx+38h]; this
0x18005d482  sbb     rdx, rdx
0x18005d485  xor     r8d, r8d; struct _LUTF8_STRING *
0x18005d488  and     rdx, rax; struct _LUTF8_STRING *
0x18005d48b  call    ?ForceNameSetting@CBasicNodeType@@QEAAJPEBU_LUTF8_STRING@@00@Z; CBasicNodeType::ForceNameSetting(_LUTF8_STRING const *,_LUTF8_STRING const *,_LUTF8_STRING const *)
0x18005d490  test    eax, eax
0x18005d492  js      short loc_18005D4C1
0x18005d494  mov     rcx, [rbx+38h]
0x18005d498  mov     rdx, rdi
0x18005d49b  mov     rax, [rcx]
0x18005d49e  mov     rax, [rax+48h]
0x18005d4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d4a7  test    eax, eax
0x18005d4a9  js      short loc_18005D4C1
0x18005d4ab  mov     rcx, [rsi+28h]; this
0x18005d4af  or      r8d, 0FFFFFFFFh; unsigned int
0x18005d4b3  mov     rdx, rbx; struct CChildNode *
0x18005d4b6  call    ?InsertChild@CElementModification@@QEAAJPEAVCChildNode@@K@Z; CElementModification::InsertChild(CChildNode *,ulong)
0x18005d4bb  test    eax, eax
0x18005d4bd  js      short loc_18005D4C1
0x18005d4bf  xor     eax, eax
0x18005d4c1  mov     rcx, [rbp+var_10]
0x18005d4c5  xor     rcx, rsp; StackCookie
0x18005d4c8  call    __security_check_cookie
0x18005d4cd  mov     rbx, [rsp+60h+arg_0]
0x18005d4d5  add     rsp, 60h
0x18005d4d9  pop     r15
0x18005d4db  pop     r14
0x18005d4dd  pop     r13
0x18005d4df  pop     r12
0x18005d4e1  pop     rdi
0x18005d4e2  pop     rsi
0x18005d4e3  pop     rbp
0x18005d4e4  retn
```
