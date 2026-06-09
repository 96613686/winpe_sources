# RtlExecuteXPathOverMicrodom

- ea: `0x18005f1c0`
- end: `0x18005f478`
- name: `RtlExecuteXPathOverMicrodom`
- size: `696`
- prototype: `__int64 __usercall@<rax>(struct Windows::Microdom::Rtl::IRtlMicrodom *@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001f4ac`
- `0x18001f554`
- `0x1800293a0`
- `0x180053f74`
- `0x1800541f8`
- `0x18005d2e8`
- `0x18005d3c4`
- `0x18005d53c`
- `0x18005ec48`
- `0x18005f1c0`

## string_xrefs

- `0x18005f21a`: `onecore\base\xml\udom_xpath.cpp`
- `0x18005f25a`: `onecore\base\xml\udom_xpath.cpp`
- `0x18005f29b`: `onecore\base\xml\udom_xpath.cpp`
- `0x18005f365`: `onecore\base\xml\udom_xpath.cpp`
- `0x18005f408`: `onecore\base\xml\udom_xpath.cpp`
- `0x18005f234`: `RtlExecuteXPathOverMicrodom`
- `0x18005f271`: `RtlExecuteXPathOverMicrodom`
- `0x18005f2b2`: `RtlExecuteXPathOverMicrodom`
- `0x18005f37c`: `RtlExecuteXPathOverMicrodom`
- `0x18005f41f`: `RtlExecuteXPathOverMicrodom`
- `0x18005f27c`: `(XpathExpression != 0) || (cXpathExpressionCount == 0)`

## pseudocode

```c
__int64 __fastcall RtlExecuteXPathOverMicrodom(
        struct Windows::Microdom::Rtl::IRtlMicrodom *a1,
        __int64 a2,
        __int64 a3,
        const struct Windows::Microdom::Rtl::_XPATH_STEP_DESCRIPTION *a4,
        _OWORD *a5)
{
  __int64 v5; // rdi
  const struct Windows::Microdom::Rtl::_XPATH_STEP_DESCRIPTION *v6; // rsi
  __int64 v7; // rbx
  struct Node *v9; // rdx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rcx
  struct NodeVtbl *lpVtbl; // r8
  __int64 v15; // rax
  __int128 v16; // xmm1
  struct Node v18[2]; // [rsp+20h] [rbp-91h] BYREF
  __int64 v19; // [rsp+30h] [rbp-81h]
  const char *v20; // [rsp+38h] [rbp-79h]
  __int64 v21; // [rsp+40h] [rbp-71h] BYREF
  __int128 v22; // [rsp+48h] [rbp-69h] BYREF
  __int64 v23; // [rsp+58h] [rbp-59h] BYREF
  __int128 v24; // [rsp+60h] [rbp-51h] BYREF
  const char *v25; // [rsp+70h] [rbp-41h] BYREF
  const char *v26; // [rsp+78h] [rbp-39h]
  __int64 v27; // [rsp+80h] [rbp-31h]
  const char *v28; // [rsp+88h] [rbp-29h]
  _QWORD v29[4]; // [rsp+90h] [rbp-21h] BYREF
  _QWORD v30[4]; // [rsp+B0h] [rbp-1h] BYREF
  int v31; // [rsp+D0h] [rbp+1Fh] BYREF

  v5 = 0;
  v31 = 0;
  v23 = 0;
  v6 = a4;
  v21 = 0;
  v7 = a3;
  v24 = 0;
  v22 = 0;
  if ( !a1 )
  {
    v19 = 1328;
    v18[0].lpVtbl = (struct NodeVtbl *)"onecore\\base\\xml\\udom_xpath.cpp";
    v9 = v18;
    v18[1].lpVtbl = (struct NodeVtbl *)"RtlExecuteXPathOverMicrodom";
    v20 = "TheMicrodom != 0";
LABEL_22:
    v10 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
            &v31,
            v9);
    goto LABEL_23;
  }
  if ( !a4 && a3 )
  {
    v29[2] = 1329;
    v29[0] = "onecore\\base\\xml\\udom_xpath.cpp";
    v9 = (struct Node *)v29;
    v29[1] = "RtlExecuteXPathOverMicrodom";
    v29[3] = "(XpathExpression != 0) || (cXpathExpressionCount == 0)";
    goto LABEL_22;
  }
  if ( *(_DWORD *)(a2 + 8) == -1 )
  {
    v27 = 1330;
    v25 = "onecore\\base\\xml\\udom_xpath.cpp";
    v9 = (struct Node *)&v25;
    v26 = "RtlExecuteXPathOverMicrodom";
    v28 = "ContextElement != Windows::Microdom::Rtl::Element::InvalidValue()";
    goto LABEL_22;
  }
  if ( !a5 )
  {
    v30[2] = 1331;
    v30[0] = "onecore\\base\\xml\\udom_xpath.cpp";
    v30[1] = "RtlExecuteXPathOverMicrodom";
    v30[3] = "Not-null check failed: ResultSet";
    v10 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
            &v31,
            v30);
LABEL_23:
    v11 = v10;
    goto LABEL_24;
  }
  *(_OWORD *)&v18[0].lpVtbl = *(_OWORD *)a2;
  v10 = CXpathEvaluationContext::Add((CXpathEvaluationContext *)&v23, (struct Node)v18);
  if ( v10 < 0 )
    goto LABEL_23;
  if ( v7 )
  {
    while ( 1 )
    {
      v10 = XpathEvaluateStep(
              a1,
              v6,
              (const struct CXpathEvaluationContext *)&v23,
              (struct CXpathEvaluationContext *)&v21);
      if ( v10 < 0 )
        goto LABEL_23;
      CXpathEvaluationContext::Order((CXpathEvaluationContext *)&v21);
      v10 = CXpathEvaluationContext::CopyFrom(
              (CXpathEvaluationContext *)&v23,
              (const struct CXpathEvaluationContext *)&v21);
      if ( v10 < 0 )
        goto LABEL_23;
      v6 = (const struct Windows::Microdom::Rtl::_XPATH_STEP_DESCRIPTION *)((char *)v6 + 40);
      if ( !--v7 )
      {
        v5 = v21;
        break;
      }
    }
  }
  v18[0].lpVtbl = 0;
  v18[1].lpVtbl = 0;
  if ( !Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(
          v18,
          v5) )
  {
    v27 = 1373;
    v25 = "onecore\\base\\xml\\udom_xpath.cpp";
    v26 = "RtlExecuteXPathOverMicrodom";
    v28 = "NodeSetResult.Allocate(OutputResultSet.NodeCount())";
    v11 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
            &v31,
            &v25);
    Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(v18);
LABEL_24:
    Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(&v22);
    Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(&v24);
    return v11;
  }
  if ( v5 )
  {
    v12 = v24;
    v13 = 0;
    lpVtbl = v18[0].lpVtbl;
    do
    {
      v15 = v13++;
      *((_OWORD *)&lpVtbl->QueryInterface + v15) = *(_OWORD *)(v12 + 16 * v15);
    }
    while ( v13 != v5 );
  }
  v16 = *(_OWORD *)&v18[0].lpVtbl;
  *(_OWORD *)&v18[0].lpVtbl = *a5;
  *a5 = v16;
  Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(v18);
  Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(&v22);
  Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(&v24);
  return 0;
}

```

## disassembly

```asm
0x18005f1c0  mov     [rsp-8+arg_8], rbx
0x18005f1c5  push    rbp
0x18005f1c6  push    rsi
0x18005f1c7  push    rdi
0x18005f1c8  push    r14
0x18005f1ca  push    r15
0x18005f1cc  lea     rbp, [rsp-2Fh]
0x18005f1d1  sub     rsp, 0E0h
0x18005f1d8  mov     rax, cs:__security_cookie
0x18005f1df  xor     rax, rsp
0x18005f1e2  mov     [rbp+4Fh+var_28], rax
0x18005f1e6  mov     r14, [rbp+4Fh+arg_20]
0x18005f1ea  xor     edi, edi
0x18005f1ec  mov     [rbp+4Fh+var_30], 0
0x18005f1f3  xorps   xmm0, xmm0
0x18005f1f6  mov     [rbp+4Fh+var_A8], 0
0x18005f1fe  mov     rsi, r9
0x18005f201  mov     [rbp+4Fh+var_C0], rdi
0x18005f205  mov     rbx, r8
0x18005f208  mov     r15, rcx
0x18005f20b  movdqu  [rbp+4Fh+var_A0], xmm0
0x18005f210  movdqu  [rbp+4Fh+var_B8], xmm0
0x18005f215  test    rcx, rcx
0x18005f218  jnz     short loc_18005F250
0x18005f21a  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18005f221  mov     [rsp+100h+var_D0], 530h
0x18005f22a  mov     [rsp+100h+var_E0.lpVtbl], rax
0x18005f22f  lea     rdx, [rsp+100h+var_E0]
0x18005f234  lea     rax, aRtlexecutexpat_0; "RtlExecuteXPathOverMicrodom"
0x18005f23b  mov     [rsp+100h+var_E0.lpVtbl+8], rax
0x18005f240  lea     rax, aThemicrodom0; "TheMicrodom != 0"
0x18005f247  mov     [rbp+4Fh+var_C8], rax
0x18005f24b  jmp     loc_18005F435
0x18005f250  test    r9, r9
0x18005f253  jnz     short loc_18005F28C
0x18005f255  test    rbx, rbx
0x18005f258  jz      short loc_18005F28C
0x18005f25a  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18005f261  mov     [rbp+4Fh+var_60], 531h
0x18005f269  mov     [rbp+4Fh+var_70], rax
0x18005f26d  lea     rdx, [rbp+4Fh+var_70]
0x18005f271  lea     rax, aRtlexecutexpat_0; "RtlExecuteXPathOverMicrodom"
0x18005f278  mov     [rbp+4Fh+var_68], rax
0x18005f27c  lea     rax, aXpathexpressio; "(XpathExpression != 0) || (cXpathExpres"...
0x18005f283  mov     [rbp+4Fh+var_58], rax
0x18005f287  jmp     loc_18005F435
0x18005f28c  cmp     dword ptr [rdx+8], 0FFFFFFFFh
0x18005f290  jz      loc_18005F408
0x18005f296  test    r14, r14
0x18005f299  jnz     short loc_18005F2D6
0x18005f29b  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18005f2a2  mov     [rbp+4Fh+var_40], 533h
0x18005f2aa  mov     [rbp+4Fh+var_50], rax
0x18005f2ae  lea     rdx, [rbp+4Fh+var_50]
0x18005f2b2  lea     rax, aRtlexecutexpat_0; "RtlExecuteXPathOverMicrodom"
0x18005f2b9  mov     [rbp+4Fh+var_48], rax
0x18005f2bd  lea     rcx, [rbp+4Fh+var_30]
0x18005f2c1  lea     rax, aNotNullCheckFa_44; "Not-null check failed: ResultSet"
0x18005f2c8  mov     [rbp+4Fh+var_38], rax
0x18005f2cc  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005f2d1  jmp     loc_18005F43E
0x18005f2d6  movups  xmm0, xmmword ptr [rdx]
0x18005f2d9  lea     rdx, [rsp+100h+var_E0]; struct Node
0x18005f2de  lea     rcx, [rbp+4Fh+var_A8]; this
0x18005f2e2  movdqu  xmmword ptr [rsp+100h+var_E0.lpVtbl], xmm0
0x18005f2e8  call    ?Add@CXpathEvaluationContext@@QEAAJUNode@Rtl@Microdom@Windows@@@Z; CXpathEvaluationContext::Add(Windows::Microdom::Rtl::Node)
0x18005f2ed  test    eax, eax
0x18005f2ef  js      loc_18005F43E
0x18005f2f5  test    rbx, rbx
0x18005f2f8  jz      short loc_18005F341
0x18005f2fa  lea     r9, [rbp+4Fh+var_C0]; struct CXpathEvaluationContext *
0x18005f2fe  mov     rdx, rsi; struct Windows::Microdom::Rtl::_XPATH_STEP_DESCRIPTION *
0x18005f301  lea     r8, [rbp+4Fh+var_A8]; struct CXpathEvaluationContext *
0x18005f305  mov     rcx, r15; struct Windows::Microdom::Rtl::IRtlMicrodom *
0x18005f308  call    ?XpathEvaluateStep@@YAJPEAUIRtlMicrodom@Rtl@Microdom@Windows@@AEBU_XPATH_STEP_DESCRIPTION@234@AEBVCXpathEvaluationContext@@AEAV6@@Z; XpathEvaluateStep(Windows::Microdom::Rtl::IRtlMicrodom *,Windows::Microdom::Rtl::_XPATH_STEP_DESCRIPTION const &,CXpathEvaluationContext const &,CXpathEvaluationContext &)
0x18005f30d  test    eax, eax
0x18005f30f  js      loc_18005F43E
0x18005f315  lea     rcx, [rbp+4Fh+var_C0]; this
0x18005f319  call    ?Order@CXpathEvaluationContext@@QEAAXXZ; CXpathEvaluationContext::Order(void)
0x18005f31e  lea     rdx, [rbp+4Fh+var_C0]; struct CXpathEvaluationContext *
0x18005f322  lea     rcx, [rbp+4Fh+var_A8]; this
0x18005f326  call    ?CopyFrom@CXpathEvaluationContext@@QEAAJAEBV1@@Z; CXpathEvaluationContext::CopyFrom(CXpathEvaluationContext const &)
0x18005f32b  test    eax, eax
0x18005f32d  js      loc_18005F43E
0x18005f333  add     rsi, 28h ; '('
0x18005f337  sub     rbx, 1
0x18005f33b  jnz     short loc_18005F2FA
0x18005f33d  mov     rdi, [rbp+4Fh+var_C0]
0x18005f341  mov     rdx, rdi
0x18005f344  mov     [rsp+100h+var_E0.lpVtbl], 0
0x18005f34d  lea     rcx, [rsp+100h+var_E0]
0x18005f352  mov     [rsp+100h+var_E0.lpVtbl+8], 0
0x18005f35b  call    ?Allocate@?$AutoVectorBase@V?$MicrodomVectorTraits@UElement@Rtl@Microdom@Windows@@@Microdom@Windows@@V?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@3@@Windows@@QEAAPEAUElement@Rtl@Microdom@2@_K@Z; Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(unsigned __int64)
0x18005f360  test    rax, rax
0x18005f363  jnz     short loc_18005F3AC
0x18005f365  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18005f36c  mov     [rbp+4Fh+var_80], 55Dh
0x18005f374  mov     [rbp+4Fh+var_90], rax
0x18005f378  lea     rdx, [rbp+4Fh+var_90]
0x18005f37c  lea     rax, aRtlexecutexpat_0; "RtlExecuteXPathOverMicrodom"
0x18005f383  mov     [rbp+4Fh+var_88], rax
0x18005f387  lea     rcx, [rbp+4Fh+var_30]
0x18005f38b  lea     rax, aNodesetresultA; "NodeSetResult.Allocate(OutputResultSet."...
0x18005f392  mov     [rbp+4Fh+var_78], rax
0x18005f396  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005f39b  lea     rcx, [rsp+100h+var_E0]
0x18005f3a0  mov     ebx, eax
0x18005f3a2  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18005f3a7  jmp     loc_18005F440
0x18005f3ac  test    rdi, rdi
0x18005f3af  jz      short loc_18005F3D4
0x18005f3b1  mov     rdx, qword ptr [rbp+4Fh+var_A0]
0x18005f3b5  xor     ecx, ecx
0x18005f3b7  mov     r8, [rsp+100h+var_E0.lpVtbl]
0x18005f3bc  mov     rax, rcx
0x18005f3bf  inc     rcx
0x18005f3c2  add     rax, rax
0x18005f3c5  movups  xmm0, xmmword ptr [rdx+rax*8]
0x18005f3c9  movdqu  xmmword ptr [r8+rax*8], xmm0
0x18005f3cf  cmp     rcx, rdi
0x18005f3d2  jnz     short loc_18005F3BC
0x18005f3d4  movups  xmm0, xmmword ptr [r14]
0x18005f3d8  lea     rcx, [rsp+100h+var_E0]
0x18005f3dd  movaps  xmm1, xmmword ptr [rsp+100h+var_E0.lpVtbl]
0x18005f3e2  movdqu  xmmword ptr [rsp+100h+var_E0.lpVtbl], xmm0
0x18005f3e8  movdqu  xmmword ptr [r14], xmm1
0x18005f3ed  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18005f3f2  lea     rcx, [rbp+4Fh+var_B8]
0x18005f3f6  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18005f3fb  lea     rcx, [rbp+4Fh+var_A0]
0x18005f3ff  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18005f404  xor     eax, eax
0x18005f406  jmp     short loc_18005F454
0x18005f408  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18005f40f  mov     [rbp+4Fh+var_80], 532h
0x18005f417  mov     [rbp+4Fh+var_90], rax
0x18005f41b  lea     rdx, [rbp+4Fh+var_90]
0x18005f41f  lea     rax, aRtlexecutexpat_0; "RtlExecuteXPathOverMicrodom"
0x18005f426  mov     [rbp+4Fh+var_88], rax
0x18005f42a  lea     rax, aContextelement; "ContextElement != Windows::Microdom::Rt"...
0x18005f431  mov     [rbp+4Fh+var_78], rax
0x18005f435  lea     rcx, [rbp+4Fh+var_30]
0x18005f439  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005f43e  mov     ebx, eax
0x18005f440  lea     rcx, [rbp+4Fh+var_B8]
0x18005f444  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18005f449  lea     rcx, [rbp+4Fh+var_A0]
0x18005f44d  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18005f452  mov     eax, ebx
0x18005f454  mov     rcx, [rbp+4Fh+var_28]
0x18005f458  xor     rcx, rsp; StackCookie
0x18005f45b  call    __security_check_cookie
0x18005f460  mov     rbx, [rsp+100h+arg_8]
0x18005f468  add     rsp, 0E0h
0x18005f46f  pop     r15
0x18005f471  pop     r14
0x18005f473  pop     rdi
0x18005f474  pop     rsi
0x18005f475  pop     rbp
0x18005f476  retn
```
