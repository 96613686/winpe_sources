# RtlMicrodomUpdateCreateElementNs

- ea: `0x18005c2c0`
- end: `0x18005c553`
- name: `RtlMicrodomUpdateCreateElementNs`
- size: `659`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000f860`
- `0x18001f4ac`
- `0x18001fd10`
- `0x1800293a0`
- `0x180059f50`
- `0x18005a228`
- `0x18005a774`
- `0x18005b3f0`
- `0x18005c2c0`
- `0x1800a0020`

## string_xrefs

- `0x18005c30f`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c35b`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c393`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c3c7`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c3fd`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c42c`: `onecore\base\xml\udom_modify.cpp`
- `0x18005c322`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs`
- `0x18005c36e`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs`
- `0x18005c3a6`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs`
- `0x18005c3da`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs`
- `0x18005c410`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs`
- `0x18005c443`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs`
- `0x18005c32d`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x18005c452`: `Not-null check failed: pUpdateCookie`

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
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x18005C552LL);
      }
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
            v14 = (const struct _LUTF8_STRING *)qword_1800A4A00;
          result = CBasicNodeType::ForceNameSetting(
                     *((CBasicNodeType **)v19 + 7),
                     (const struct _LUTF8_STRING *)((unsigned __int64)qword_1800A4A00 & -(__int64)(a4 != 0)),
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
0x18005c2c0  mov     [rsp-38h+arg_0], rbx
0x18005c2c5  push    rbp
0x18005c2c6  push    rsi
0x18005c2c7  push    rdi
0x18005c2c8  push    r12
0x18005c2ca  push    r13
0x18005c2cc  push    r14
0x18005c2ce  push    r15
0x18005c2d0  mov     rbp, rsp
0x18005c2d3  sub     rsp, 60h
0x18005c2d7  mov     rax, cs:__security_cookie
0x18005c2de  xor     rax, rsp
0x18005c2e1  mov     [rbp+var_10], rax
0x18005c2e5  mov     r15, [rbp+arg_28]
0x18005c2e9  xor     esi, esi
0x18005c2eb  mov     r12, [rbp+arg_20]
0x18005c2ef  mov     r14, r9
0x18005c2f2  mov     [rbp+var_18], esi
0x18005c2f5  mov     rdi, r8
0x18005c2f8  mov     [rbp+var_20], rsi
0x18005c2fc  mov     rbx, rdx
0x18005c2ff  mov     r13d, ecx
0x18005c302  test    r15, r15
0x18005c305  jz      short loc_18005C30A
0x18005c307  mov     [r15], rsi
0x18005c30a  test    rbx, rbx
0x18005c30d  jnz     short loc_18005C34A
0x18005c30f  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c316  mov     [rbp+var_30], 5C5h
0x18005c31e  mov     [rbp+var_40], rax
0x18005c322  lea     rax, aWindowsUdomRtl_12; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005c329  mov     [rbp+var_38], rax
0x18005c32d  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18005c334  lea     rdx, [rbp+var_40]
0x18005c338  mov     [rbp+var_28], rax
0x18005c33c  lea     rcx, [rbp+var_18]
0x18005c340  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005c345  jmp     loc_18005C523
0x18005c34a  test    rdi, rdi
0x18005c34d  jz      short loc_18005C382
0x18005c34f  mov     rcx, rdi
0x18005c352  call    RtlIsLUtf8StringValid
0x18005c357  test    al, al
0x18005c359  jnz     short loc_18005C382
0x18005c35b  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c362  mov     [rbp+var_30], 5C6h
0x18005c36a  mov     [rbp+var_40], rax
0x18005c36e  lea     rax, aWindowsUdomRtl_12; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005c375  mov     [rbp+var_38], rax
0x18005c379  lea     rax, aNamespace0Rtli; "(Namespace == 0) || RtlIsLUtf8StringVal"...
0x18005c380  jmp     short loc_18005C334
0x18005c382  test    r14, r14
0x18005c385  jz      short loc_18005C3BD
0x18005c387  mov     rcx, r14
0x18005c38a  call    RtlIsLUtf8StringValid
0x18005c38f  test    al, al
0x18005c391  jnz     short loc_18005C3BD
0x18005c393  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c39a  mov     [rbp+var_30], 5C7h
0x18005c3a2  mov     [rbp+var_40], rax
0x18005c3a6  lea     rax, aWindowsUdomRtl_12; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005c3ad  mov     [rbp+var_38], rax
0x18005c3b1  lea     rax, aPrefix0Rtlislu; "(Prefix == 0) || RtlIsLUtf8StringValid("...
0x18005c3b8  jmp     loc_18005C334
0x18005c3bd  test    rdi, rdi
0x18005c3c0  jnz     short loc_18005C3F1
0x18005c3c2  test    r14, r14
0x18005c3c5  jz      short loc_18005C3F1
0x18005c3c7  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c3ce  mov     [rbp+var_30], 5C8h
0x18005c3d6  mov     [rbp+var_40], rax
0x18005c3da  lea     rax, aWindowsUdomRtl_12; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005c3e1  mov     [rbp+var_38], rax
0x18005c3e5  lea     rax, aNamespace0Name; "(Namespace != 0) || (Namespace == 0 && "...
0x18005c3ec  jmp     loc_18005C334
0x18005c3f1  mov     rcx, r12
0x18005c3f4  call    RtlIsLUtf8StringValid
0x18005c3f9  test    al, al
0x18005c3fb  jnz     short loc_18005C427
0x18005c3fd  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c404  mov     [rbp+var_30], 5C9h
0x18005c40c  mov     [rbp+var_40], rax
0x18005c410  lea     rax, aWindowsUdomRtl_12; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005c417  mov     [rbp+var_38], rax
0x18005c41b  lea     rax, aRtlislutf8stri_0; "RtlIsLUtf8StringValid(LocalName)"
0x18005c422  jmp     loc_18005C334
0x18005c427  test    r15, r15
0x18005c42a  jnz     short loc_18005C467
0x18005c42c  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005c433  mov     [rbp+var_30], 5CAh
0x18005c43b  mov     [rbp+var_40], rax
0x18005c43f  lea     rdx, [rbp+var_40]
0x18005c443  lea     rax, aWindowsUdomRtl_12; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18005c44a  mov     [rbp+var_38], rax
0x18005c44e  lea     rcx, [rbp+var_18]
0x18005c452  lea     rax, aNotNullCheckFa_53; "Not-null check failed: pUpdateCookie"
0x18005c459  mov     [rbp+var_28], rax
0x18005c45d  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005c462  jmp     loc_18005C523
0x18005c467  lea     rdx, [rbp+var_20]; struct CChildNode **
0x18005c46b  mov     rcx, rbx; this
0x18005c46e  call    ?CreateVirtualElement@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::CreateVirtualElement(CChildNode * &)
0x18005c473  test    eax, eax
0x18005c475  js      loc_18005C523
0x18005c47b  mov     rsi, [rbp+var_20]
0x18005c47f  test    rsi, rsi
0x18005c482  jz      loc_18005C548
0x18005c488  mov     rcx, [rsi+38h]; this
0x18005c48c  mov     r9, r12; struct _LUTF8_STRING *
0x18005c48f  mov     r8, rdi; struct _LUTF8_STRING *
0x18005c492  mov     rdx, r14; struct _LUTF8_STRING *
0x18005c495  call    ?ForceNameSetting@CBasicNodeType@@QEAAJPEBU_LUTF8_STRING@@00@Z; CBasicNodeType::ForceNameSetting(_LUTF8_STRING const *,_LUTF8_STRING const *,_LUTF8_STRING const *)
0x18005c49a  test    eax, eax
0x18005c49c  js      loc_18005C523
0x18005c4a2  mov     [r15], rsi
0x18005c4a5  test    r13b, 1
0x18005c4a9  jz      short loc_18005C521
0x18005c4ab  test    rdi, rdi
0x18005c4ae  jz      short loc_18005C521
0x18005c4b0  lea     rdx, [rbp+var_20]; struct CChildNode **
0x18005c4b4  mov     [rbp+var_20], 0
0x18005c4bc  mov     rcx, rbx; this
0x18005c4bf  call    ?CreateVirtualAttribute@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::CreateVirtualAttribute(CChildNode * &)
0x18005c4c4  test    eax, eax
0x18005c4c6  js      short loc_18005C523
0x18005c4c8  mov     rbx, [rbp+var_20]
0x18005c4cc  lea     rax, qword_1800A4A00
0x18005c4d3  test    r14, r14
0x18005c4d6  mov     r9, r14
0x18005c4d9  cmovz   r9, rax; struct _LUTF8_STRING *
0x18005c4dd  neg     r14
0x18005c4e0  mov     rcx, [rbx+38h]; this
0x18005c4e4  sbb     rdx, rdx
0x18005c4e7  xor     r8d, r8d; struct _LUTF8_STRING *
0x18005c4ea  and     rdx, rax; struct _LUTF8_STRING *
0x18005c4ed  call    ?ForceNameSetting@CBasicNodeType@@QEAAJPEBU_LUTF8_STRING@@00@Z; CBasicNodeType::ForceNameSetting(_LUTF8_STRING const *,_LUTF8_STRING const *,_LUTF8_STRING const *)
0x18005c4f2  test    eax, eax
0x18005c4f4  js      short loc_18005C523
0x18005c4f6  mov     rcx, [rbx+38h]
0x18005c4fa  mov     rdx, rdi
0x18005c4fd  mov     rax, [rcx]
0x18005c500  mov     rax, [rax+48h]
0x18005c504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c509  test    eax, eax
0x18005c50b  js      short loc_18005C523
0x18005c50d  mov     rcx, [rsi+28h]; this
0x18005c511  or      r8d, 0FFFFFFFFh; unsigned int
0x18005c515  mov     rdx, rbx; struct CChildNode *
0x18005c518  call    ?InsertChild@CElementModification@@QEAAJPEAVCChildNode@@K@Z; CElementModification::InsertChild(CChildNode *,ulong)
0x18005c51d  test    eax, eax
0x18005c51f  js      short loc_18005C523
0x18005c521  xor     eax, eax
0x18005c523  mov     rcx, [rbp+var_10]
0x18005c527  xor     rcx, rsp; StackCookie
0x18005c52a  call    __security_check_cookie
0x18005c52f  mov     rbx, [rsp+60h+arg_0]
0x18005c537  add     rsp, 60h
0x18005c53b  pop     r15
0x18005c53d  pop     r14
0x18005c53f  pop     r13
0x18005c541  pop     r12
0x18005c543  pop     rdi
0x18005c544  pop     rsi
0x18005c545  pop     rbp
0x18005c546  retn
0x18005c548  mov     ecx, 0C00000E5h; int
0x18005c54d  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
