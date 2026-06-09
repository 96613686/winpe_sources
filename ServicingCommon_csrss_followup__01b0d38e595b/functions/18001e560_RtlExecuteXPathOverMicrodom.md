# RtlExecuteXPathOverMicrodom

- ea: `0x18001e560`
- end: `0x18001e81a`
- name: `RtlExecuteXPathOverMicrodom`
- size: `698`
- prototype: `__int64 __usercall@<rax>(struct Windows::Microdom::Rtl::IRtlMicrodom *@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001e560`
- `0x18001e820`
- `0x18001f1d8`
- `0x1800217cc`
- `0x18002d2b0`
- `0x180056658`
- `0x18005df88`
- `0x18005e064`
- `0x18005e1dc`
- `0x18005f820`

## string_xrefs

- `0x18001e5da`: `RtlExecuteXPathOverMicrodom`
- `0x18001e616`: `RtlExecuteXPathOverMicrodom`
- `0x18001e657`: `RtlExecuteXPathOverMicrodom`
- `0x18001e71f`: `RtlExecuteXPathOverMicrodom`
- `0x18001e7c0`: `RtlExecuteXPathOverMicrodom`
- `0x18001e5c1`: `onecore\base\xml\udom_xpath.cpp`
- `0x18001e5ff`: `onecore\base\xml\udom_xpath.cpp`
- `0x18001e640`: `onecore\base\xml\udom_xpath.cpp`
- `0x18001e708`: `onecore\base\xml\udom_xpath.cpp`
- `0x18001e7a9`: `onecore\base\xml\udom_xpath.cpp`
- `0x18001e621`: `(XpathExpression != 0) || (cXpathExpressionCount == 0)`

## pseudocode

```c
__int64 __fastcall RtlExecuteXPathOverMicrodom(
        struct Windows::Microdom::Rtl::IRtlMicrodom *a1,
        __int64 a2,
        __int64 a3,
        const struct Windows::Microdom::Rtl::_XPATH_STEP_DESCRIPTION *a4,
        _OWORD *a5)
{
  const struct Windows::Microdom::Rtl::_XPATH_STEP_DESCRIPTION *v5; // rdi
  __int64 v6; // rbx
  Node *v8; // rdx
  int v9; // eax
  __int64 v10; // rbx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rcx
  struct NodeVtbl *lpVtbl; // r8
  __int64 v15; // rax
  __int128 v16; // xmm1
  Node v18[2]; // [rsp+20h] [rbp-81h] BYREF
  __int64 v19; // [rsp+30h] [rbp-71h]
  const char *v20; // [rsp+38h] [rbp-69h]
  __int64 v21; // [rsp+40h] [rbp-61h] BYREF
  __int128 v22; // [rsp+48h] [rbp-59h] BYREF
  __int64 v23; // [rsp+58h] [rbp-49h] BYREF
  __int128 v24; // [rsp+60h] [rbp-41h] BYREF
  const char *v25; // [rsp+70h] [rbp-31h] BYREF
  const char *v26; // [rsp+78h] [rbp-29h]
  __int64 v27; // [rsp+80h] [rbp-21h]
  const char *v28; // [rsp+88h] [rbp-19h]
  _QWORD v29[4]; // [rsp+90h] [rbp-11h] BYREF
  _QWORD v30[4]; // [rsp+B0h] [rbp+Fh] BYREF
  int v31; // [rsp+D0h] [rbp+2Fh] BYREF

  v31 = 0;
  v23 = 0;
  v5 = a4;
  v21 = 0;
  v6 = a3;
  v24 = 0;
  v22 = 0;
  if ( !a1 )
  {
    v19 = 1328;
    v18[0].lpVtbl = (struct NodeVtbl *)"onecore\\base\\xml\\udom_xpath.cpp";
    v8 = v18;
    v18[1].lpVtbl = (struct NodeVtbl *)"RtlExecuteXPathOverMicrodom";
    v20 = "TheMicrodom != 0";
LABEL_21:
    v9 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
           &v31,
           v8);
    goto LABEL_22;
  }
  if ( !a4 && a3 )
  {
    v29[2] = 1329;
    v29[0] = "onecore\\base\\xml\\udom_xpath.cpp";
    v8 = (Node *)v29;
    v29[1] = "RtlExecuteXPathOverMicrodom";
    v29[3] = "(XpathExpression != 0) || (cXpathExpressionCount == 0)";
    goto LABEL_21;
  }
  if ( *(_DWORD *)(a2 + 8) == -1 )
  {
    v27 = 1330;
    v25 = "onecore\\base\\xml\\udom_xpath.cpp";
    v8 = (Node *)&v25;
    v26 = "RtlExecuteXPathOverMicrodom";
    v28 = "ContextElement != Windows::Microdom::Rtl::Element::InvalidValue()";
    goto LABEL_21;
  }
  if ( !a5 )
  {
    v30[2] = 1331;
    v30[0] = "onecore\\base\\xml\\udom_xpath.cpp";
    v30[1] = "RtlExecuteXPathOverMicrodom";
    v30[3] = "Not-null check failed: ResultSet";
    v9 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
           &v31,
           v30);
LABEL_22:
    v11 = v9;
    goto LABEL_23;
  }
  *(_OWORD *)&v18[0].lpVtbl = *(_OWORD *)a2;
  v9 = CXpathEvaluationContext::Add((CXpathEvaluationContext *)&v23, (struct Node)v18);
  if ( v9 < 0 )
    goto LABEL_22;
  while ( v6 )
  {
    v9 = XpathEvaluateStep(a1, v5, (const struct CXpathEvaluationContext *)&v23, (struct CXpathEvaluationContext *)&v21);
    if ( v9 < 0 )
      goto LABEL_22;
    CXpathEvaluationContext::Order((CXpathEvaluationContext *)&v21);
    v9 = CXpathEvaluationContext::CopyFrom(
           (CXpathEvaluationContext *)&v23,
           (const struct CXpathEvaluationContext *)&v21);
    if ( v9 < 0 )
      goto LABEL_22;
    --v6;
    v5 = (const struct Windows::Microdom::Rtl::_XPATH_STEP_DESCRIPTION *)((char *)v5 + 40);
  }
  v10 = v21;
  v18[0].lpVtbl = 0;
  v18[1].lpVtbl = 0;
  if ( !Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(
          v18,
          v21) )
  {
    v27 = 1373;
    v25 = "onecore\\base\\xml\\udom_xpath.cpp";
    v26 = "RtlExecuteXPathOverMicrodom";
    v28 = "NodeSetResult.Allocate(OutputResultSet.NodeCount())";
    v11 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
            &v31,
            &v25);
    Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(v18);
LABEL_23:
    Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(&v22);
    Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(&v24);
    return v11;
  }
  if ( v10 )
  {
    v12 = v24;
    v13 = 0;
    lpVtbl = v18[0].lpVtbl;
    do
    {
      v15 = v13++;
      *((_OWORD *)&lpVtbl->QueryInterface + v15) = *(_OWORD *)(v12 + 16 * v15);
    }
    while ( v13 != v10 );
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
0x18001e560  mov     [rsp-8+arg_8], rbx
0x18001e565  mov     [rsp-8+arg_10], rsi
0x18001e56a  push    rbp
0x18001e56b  push    rdi
0x18001e56c  push    r14
0x18001e56e  lea     rbp, [rsp-3Fh]
0x18001e573  sub     rsp, 0E0h
0x18001e57a  mov     rax, cs:__security_cookie
0x18001e581  xor     rax, rsp
0x18001e584  mov     [rbp+4Fh+var_18], rax
0x18001e588  mov     rsi, [rbp+4Fh+arg_20]
0x18001e58c  xorps   xmm0, xmm0
0x18001e58f  mov     [rbp+4Fh+var_20], 0
0x18001e596  xorps   xmm1, xmm1
0x18001e599  mov     [rbp+4Fh+var_98], 0
0x18001e5a1  mov     rdi, r9
0x18001e5a4  mov     [rbp+4Fh+var_B0], 0
0x18001e5ac  mov     rbx, r8
0x18001e5af  mov     r14, rcx
0x18001e5b2  movdqu  [rbp+4Fh+var_90], xmm0
0x18001e5b7  movdqu  [rbp+4Fh+var_A8], xmm1
0x18001e5bc  test    rcx, rcx
0x18001e5bf  jnz     short loc_18001E5F5
0x18001e5c1  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18001e5c8  mov     [rbp+4Fh+var_C0], 530h
0x18001e5d0  mov     [rsp+0F0h+var_D0.lpVtbl], rax
0x18001e5d5  lea     rdx, [rsp+0F0h+var_D0]
0x18001e5da  lea     rax, aRtlexecutexpat_0; "RtlExecuteXPathOverMicrodom"
0x18001e5e1  mov     [rbp+4Fh+var_D0.lpVtbl+8], rax
0x18001e5e5  lea     rax, aThemicrodom0; "TheMicrodom != 0"
0x18001e5ec  mov     [rbp+4Fh+var_B8], rax
0x18001e5f0  jmp     loc_18001E7D6
0x18001e5f5  test    r9, r9
0x18001e5f8  jnz     short loc_18001E631
0x18001e5fa  test    rbx, rbx
0x18001e5fd  jz      short loc_18001E631
0x18001e5ff  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18001e606  mov     [rbp+4Fh+var_50], 531h
0x18001e60e  mov     [rbp+4Fh+var_60], rax
0x18001e612  lea     rdx, [rbp+4Fh+var_60]
0x18001e616  lea     rax, aRtlexecutexpat_0; "RtlExecuteXPathOverMicrodom"
0x18001e61d  mov     [rbp+4Fh+var_58], rax
0x18001e621  lea     rax, aXpathexpressio; "(XpathExpression != 0) || (cXpathExpres"...
0x18001e628  mov     [rbp+4Fh+var_48], rax
0x18001e62c  jmp     loc_18001E7D6
0x18001e631  cmp     dword ptr [rdx+8], 0FFFFFFFFh
0x18001e635  jz      loc_18001E7A9
0x18001e63b  test    rsi, rsi
0x18001e63e  jnz     short loc_18001E67B
0x18001e640  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18001e647  mov     [rbp+4Fh+var_30], 533h
0x18001e64f  mov     [rbp+4Fh+var_40], rax
0x18001e653  lea     rdx, [rbp+4Fh+var_40]
0x18001e657  lea     rax, aRtlexecutexpat_0; "RtlExecuteXPathOverMicrodom"
0x18001e65e  mov     [rbp+4Fh+var_38], rax
0x18001e662  lea     rcx, [rbp+4Fh+var_20]
0x18001e666  lea     rax, aNotNullCheckFa_44; "Not-null check failed: ResultSet"
0x18001e66d  mov     [rbp+4Fh+var_28], rax
0x18001e671  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18001e676  jmp     loc_18001E7DF
0x18001e67b  movups  xmm0, xmmword ptr [rdx]
0x18001e67e  lea     rdx, [rsp+0F0h+var_D0]; struct Node
0x18001e683  lea     rcx, [rbp+4Fh+var_98]; this
0x18001e687  movdqu  xmmword ptr [rsp+0F0h+var_D0.lpVtbl], xmm0
0x18001e68d  call    ?Add@CXpathEvaluationContext@@QEAAJUNode@Rtl@Microdom@Windows@@@Z; CXpathEvaluationContext::Add(Windows::Microdom::Rtl::Node)
0x18001e692  test    eax, eax
0x18001e694  js      loc_18001E7DF
0x18001e69a  test    rbx, rbx
0x18001e69d  jz      short loc_18001E6E1
0x18001e69f  lea     r9, [rbp+4Fh+var_B0]; struct CXpathEvaluationContext *
0x18001e6a3  mov     rdx, rdi; struct Windows::Microdom::Rtl::_XPATH_STEP_DESCRIPTION *
0x18001e6a6  lea     r8, [rbp+4Fh+var_98]; struct CXpathEvaluationContext *
0x18001e6aa  mov     rcx, r14; struct Windows::Microdom::Rtl::IRtlMicrodom *
0x18001e6ad  call    ?XpathEvaluateStep@@YAJPEAUIRtlMicrodom@Rtl@Microdom@Windows@@AEBU_XPATH_STEP_DESCRIPTION@234@AEBVCXpathEvaluationContext@@AEAV6@@Z; XpathEvaluateStep(Windows::Microdom::Rtl::IRtlMicrodom *,Windows::Microdom::Rtl::_XPATH_STEP_DESCRIPTION const &,CXpathEvaluationContext const &,CXpathEvaluationContext &)
0x18001e6b2  test    eax, eax
0x18001e6b4  js      loc_18001E7DF
0x18001e6ba  lea     rcx, [rbp+4Fh+var_B0]; this
0x18001e6be  call    ?Order@CXpathEvaluationContext@@QEAAXXZ; CXpathEvaluationContext::Order(void)
0x18001e6c3  lea     rdx, [rbp+4Fh+var_B0]; struct CXpathEvaluationContext *
0x18001e6c7  lea     rcx, [rbp+4Fh+var_98]; this
0x18001e6cb  call    ?CopyFrom@CXpathEvaluationContext@@QEAAJAEBV1@@Z; CXpathEvaluationContext::CopyFrom(CXpathEvaluationContext const &)
0x18001e6d0  test    eax, eax
0x18001e6d2  js      loc_18001E7DF
0x18001e6d8  dec     rbx
0x18001e6db  add     rdi, 28h ; '('
0x18001e6df  jmp     short loc_18001E69A
0x18001e6e1  mov     rbx, [rbp+4Fh+var_B0]
0x18001e6e5  lea     rcx, [rsp+0F0h+var_D0]
0x18001e6ea  mov     rdx, rbx
0x18001e6ed  mov     [rsp+0F0h+var_D0.lpVtbl], 0
0x18001e6f6  mov     [rbp+4Fh+var_D0.lpVtbl+8], 0
0x18001e6fe  call    ?Allocate@?$AutoVectorBase@V?$MicrodomVectorTraits@UElement@Rtl@Microdom@Windows@@@Microdom@Windows@@V?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@3@@Windows@@QEAAPEAUElement@Rtl@Microdom@2@_K@Z; Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(unsigned __int64)
0x18001e703  test    rax, rax
0x18001e706  jnz     short loc_18001E74F
0x18001e708  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18001e70f  mov     [rbp+4Fh+var_70], 55Dh
0x18001e717  mov     [rbp+4Fh+var_80], rax
0x18001e71b  lea     rdx, [rbp+4Fh+var_80]
0x18001e71f  lea     rax, aRtlexecutexpat_0; "RtlExecuteXPathOverMicrodom"
0x18001e726  mov     [rbp+4Fh+var_78], rax
0x18001e72a  lea     rcx, [rbp+4Fh+var_20]
0x18001e72e  lea     rax, aNodesetresultA; "NodeSetResult.Allocate(OutputResultSet."...
0x18001e735  mov     [rbp+4Fh+var_68], rax
0x18001e739  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18001e73e  lea     rcx, [rsp+0F0h+var_D0]
0x18001e743  mov     ebx, eax
0x18001e745  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18001e74a  jmp     loc_18001E7E1
0x18001e74f  test    rbx, rbx
0x18001e752  jz      short loc_18001E777
0x18001e754  mov     rdx, qword ptr [rbp+4Fh+var_90]
0x18001e758  xor     ecx, ecx
0x18001e75a  mov     r8, [rsp+0F0h+var_D0.lpVtbl]
0x18001e75f  mov     rax, rcx
0x18001e762  inc     rcx
0x18001e765  add     rax, rax
0x18001e768  movups  xmm0, xmmword ptr [rdx+rax*8]
0x18001e76c  movdqu  xmmword ptr [r8+rax*8], xmm0
0x18001e772  cmp     rcx, rbx
0x18001e775  jnz     short loc_18001E75F
0x18001e777  movups  xmm0, xmmword ptr [rsi]
0x18001e77a  lea     rcx, [rsp+0F0h+var_D0]
0x18001e77f  movaps  xmm1, xmmword ptr [rsp+0F0h+var_D0.lpVtbl]
0x18001e784  movdqu  xmmword ptr [rsp+0F0h+var_D0.lpVtbl], xmm0
0x18001e78a  movdqu  xmmword ptr [rsi], xmm1
0x18001e78e  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18001e793  lea     rcx, [rbp+4Fh+var_A8]
0x18001e797  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18001e79c  lea     rcx, [rbp+4Fh+var_90]
0x18001e7a0  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18001e7a5  xor     eax, eax
0x18001e7a7  jmp     short loc_18001E7F5
0x18001e7a9  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18001e7b0  mov     [rbp+4Fh+var_70], 532h
0x18001e7b8  mov     [rbp+4Fh+var_80], rax
0x18001e7bc  lea     rdx, [rbp+4Fh+var_80]
0x18001e7c0  lea     rax, aRtlexecutexpat_0; "RtlExecuteXPathOverMicrodom"
0x18001e7c7  mov     [rbp+4Fh+var_78], rax
0x18001e7cb  lea     rax, aContextelement; "ContextElement != Windows::Microdom::Rt"...
0x18001e7d2  mov     [rbp+4Fh+var_68], rax
0x18001e7d6  lea     rcx, [rbp+4Fh+var_20]
0x18001e7da  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18001e7df  mov     ebx, eax
0x18001e7e1  lea     rcx, [rbp+4Fh+var_A8]
0x18001e7e5  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18001e7ea  lea     rcx, [rbp+4Fh+var_90]
0x18001e7ee  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18001e7f3  mov     eax, ebx
0x18001e7f5  mov     rcx, [rbp+4Fh+var_18]
0x18001e7f9  xor     rcx, rsp; StackCookie
0x18001e7fc  call    __security_check_cookie
0x18001e801  lea     r11, [rsp+0F0h+var_10]
0x18001e809  mov     rbx, [r11+28h]
0x18001e80d  mov     rsi, [r11+30h]
0x18001e811  mov     rsp, r11
0x18001e814  pop     r14
0x18001e816  pop     rdi
0x18001e817  pop     rbp
0x18001e818  retn
```
