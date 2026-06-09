# XpathAddTermToExpression

- ea: `0x18005ed50`
- end: `0x18005efa7`
- name: `XpathAddTermToExpression`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005f4ac`

## callees

- `0x18001e820`
- `0x18001f840`
- `0x1800217cc`
- `0x18002d2b0`
- `0x18005dea0`
- `0x18005def0`
- `0x18005df88`
- `0x18005e164`
- `0x18005ed50`
- `0x18005f718`

## string_xrefs

- `0x18005ed9a`: `onecore\base\xml\udom_xpath.cpp`
- `0x18005edfc`: `onecore\base\xml\udom_xpath.cpp`
- `0x18005ef1e`: `onecore\base\xml\udom_xpath.cpp`
- `0x18005edb1`: `XpathAddTermToExpression`
- `0x18005ee13`: `XpathAddTermToExpression`
- `0x18005ef35`: `XpathAddTermToExpression`

## pseudocode

```c
__int64 __fastcall XpathAddTermToExpression(__int64 a1, _OWORD *a2, _DWORD *a3, __int64 a4)
{
  int v8; // eax
  struct Node *v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rbx
  int v12; // ebx
  __int128 v13; // kr00_16
  __int64 v14; // rax
  const char *v15; // rcx
  __int64 v16; // rax
  const char *v17; // rax
  __int64 v19; // [rsp+20h] [rbp-49h] BYREF
  const char *v20; // [rsp+28h] [rbp-41h] BYREF
  __int128 v21; // [rsp+30h] [rbp-39h] BYREF
  __int64 v22; // [rsp+40h] [rbp-29h]
  const char *v23; // [rsp+48h] [rbp-21h] BYREF
  __int128 v24; // [rsp+50h] [rbp-19h] BYREF
  const char *v25; // [rsp+60h] [rbp-9h]
  struct Node v26[2]; // [rsp+70h] [rbp+7h] BYREF
  __int64 v27; // [rsp+80h] [rbp+17h]
  __int64 v28; // [rsp+88h] [rbp+1Fh]
  int v29; // [rsp+90h] [rbp+27h] BYREF

  v29 = 0;
  v19 = 0;
  if ( !Windows::AutoNewPtr<XpathExpressionTerm>::Allocate<>(&v19) )
  {
    *((_QWORD *)&v24 + 1) = 234;
    v23 = "onecore\\base\\xml\\udom_xpath.cpp";
    *(_QWORD *)&v24 = "XpathAddTermToExpression";
    v25 = "Term.Allocate()";
    v8 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
           &v29,
           &v23);
LABEL_18:
    v12 = v8;
    goto LABEL_21;
  }
  switch ( *a3 )
  {
    case 1:
      v11 = v19;
      *(_DWORD *)(v19 + 24) = 3;
      *(_DWORD *)(v11 + 32) = a3[2];
      goto LABEL_20;
    case 2:
      v27 = 273;
      v26[0].lpVtbl = (struct NodeVtbl *)"onecore\\base\\xml\\udom_xpath.cpp";
      v9 = v26;
      v28 = 0;
      v26[1].lpVtbl = (struct NodeVtbl *)"XpathAddTermToExpression";
      v10 = 3221225474LL;
      goto LABEL_17;
    case 3:
      v11 = v19;
      *(_DWORD *)(v19 + 24) = 4;
LABEL_15:
      *(_QWORD *)(v11 + 32) = *((_QWORD *)a3 + 1);
      goto LABEL_20;
  }
  if ( *a3 != 4 )
  {
    if ( *a3 != 5 )
    {
      *((_QWORD *)&v21 + 1) = 276;
      v20 = "onecore\\base\\xml\\udom_xpath.cpp";
      v9 = (struct Node *)&v20;
      v22 = 0;
      *(_QWORD *)&v21 = "XpathAddTermToExpression";
      v10 = 3221225485LL;
LABEL_17:
      v8 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v29,
             v9,
             v10);
      goto LABEL_18;
    }
    v11 = v19;
    *(_DWORD *)(v19 + 24) = 1;
    goto LABEL_15;
  }
  v23 = 0;
  v24 = 0;
  v20 = 0;
  *(_OWORD *)&v26[0].lpVtbl = *a2;
  v21 = 0;
  v12 = CXpathEvaluationContext::Add((CXpathEvaluationContext *)&v23, (struct Node)v26);
  if ( v12 >= 0 )
  {
    v12 = XpathEvaluateFilter(a1, *((_QWORD *)a3 + 1), &v23, &v20);
    if ( v12 >= 0 )
    {
      v11 = v19;
      v13 = v21;
      *(_DWORD *)(v19 + 24) = 5;
      v14 = *(_QWORD *)(v11 + 48);
      *(_QWORD *)(v11 + 48) = v13;
      v15 = v20;
      *(_QWORD *)&v21 = v14;
      v16 = *(_QWORD *)(v11 + 56);
      *(_QWORD *)(v11 + 56) = *((_QWORD *)&v13 + 1);
      *((_QWORD *)&v21 + 1) = v16;
      v17 = *(const char **)(v11 + 40);
      *(_QWORD *)(v11 + 40) = v15;
      v20 = v17;
      *(_QWORD *)(v11 + 32) = v11 + 40;
      *(_DWORD *)(v11 + 24) = 5;
      Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(&v21);
      Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(&v24);
LABEL_20:
      v19 = 0;
      BUCL::CDequeIterator<XpathExpressionTerm,0>::InsertAfterCurrent(a4, v11);
      v12 = 0;
      goto LABEL_21;
    }
  }
  Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(&v21);
  Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(&v24);
LABEL_21:
  Windows::Auto<XpathExpressionTerm *>::~Auto<XpathExpressionTerm *>(&v19);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18005ed50  push    rbp
0x18005ed52  push    rbx
0x18005ed53  push    rsi
0x18005ed54  push    rdi
0x18005ed55  push    r14
0x18005ed57  lea     rbp, [rsp-37h]
0x18005ed5c  sub     rsp, 0A0h
0x18005ed63  mov     rax, cs:__security_cookie
0x18005ed6a  xor     rax, rsp
0x18005ed6d  mov     [rbp+57h+var_28], rax
0x18005ed71  mov     rsi, rcx
0x18005ed74  mov     [rbp+57h+var_30], 0
0x18005ed7b  lea     rcx, [rbp+57h+var_A0]
0x18005ed7f  mov     [rbp+57h+var_A0], 0
0x18005ed87  mov     r14, r9
0x18005ed8a  mov     rdi, r8
0x18005ed8d  mov     rbx, rdx
0x18005ed90  call    ??$Allocate@$$V@?$AutoNewPtr@UXpathExpressionTerm@@@Windows@@QEAAPEAUXpathExpressionTerm@@XZ; Windows::AutoNewPtr<XpathExpressionTerm>::Allocate<>(void)
0x18005ed95  test    rax, rax
0x18005ed98  jnz     short loc_18005EDD5
0x18005ed9a  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18005eda1  mov     qword ptr [rbp+57h+var_70+8], 0EAh
0x18005eda9  mov     [rbp+57h+var_78], rax
0x18005edad  lea     rdx, [rbp+57h+var_78]
0x18005edb1  lea     rax, aXpathaddtermto; "XpathAddTermToExpression"
0x18005edb8  mov     qword ptr [rbp+57h+var_70], rax
0x18005edbc  lea     rcx, [rbp+57h+var_30]
0x18005edc0  lea     rax, aTermAllocate; "Term.Allocate()"
0x18005edc7  mov     [rbp+57h+var_60], rax
0x18005edcb  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005edd0  jmp     loc_18005EF57
0x18005edd5  mov     ecx, [rdi]
0x18005edd7  sub     ecx, 1
0x18005edda  jz      loc_18005EF5B
0x18005ede0  sub     ecx, 1
0x18005ede3  jz      loc_18005EF1E
0x18005ede9  sub     ecx, 1
0x18005edec  jz      loc_18005EF09
0x18005edf2  sub     ecx, 1
0x18005edf5  jz      short loc_18005EE41
0x18005edf7  cmp     ecx, 1
0x18005edfa  jz      short loc_18005EE31
0x18005edfc  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18005ee03  mov     qword ptr [rbp+57h+var_90+8], 114h
0x18005ee0b  mov     [rbp+57h+var_98], rax
0x18005ee0f  lea     rdx, [rbp+57h+var_98]
0x18005ee13  lea     rax, aXpathaddtermto; "XpathAddTermToExpression"
0x18005ee1a  mov     [rbp+57h+var_80], 0
0x18005ee22  mov     qword ptr [rbp+57h+var_90], rax
0x18005ee26  mov     r8d, 0C000000Dh
0x18005ee2c  jmp     loc_18005EF4E
0x18005ee31  mov     rbx, [rbp+57h+var_A0]
0x18005ee35  mov     dword ptr [rbx+18h], 1
0x18005ee3c  jmp     loc_18005EF14
0x18005ee41  xorps   xmm0, xmm0
0x18005ee44  mov     [rbp+57h+var_78], 0
0x18005ee4c  movdqu  [rbp+57h+var_70], xmm0
0x18005ee51  lea     rdx, [rbp+57h+var_50]; struct Node
0x18005ee55  mov     [rbp+57h+var_98], 0
0x18005ee5d  movaps  xmm0, xmmword ptr [rbx]
0x18005ee60  lea     rcx, [rbp+57h+var_78]; this
0x18005ee64  xorps   xmm1, xmm1
0x18005ee67  movdqa  xmmword ptr [rbp+57h+var_50.lpVtbl], xmm0
0x18005ee6c  movdqu  [rbp+57h+var_90], xmm1
0x18005ee71  call    ?Add@CXpathEvaluationContext@@QEAAJUNode@Rtl@Microdom@Windows@@@Z; CXpathEvaluationContext::Add(Windows::Microdom::Rtl::Node)
0x18005ee76  mov     ebx, eax
0x18005ee78  test    eax, eax
0x18005ee7a  jns     short loc_18005EE93
0x18005ee7c  lea     rcx, [rbp+57h+var_90]
0x18005ee80  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18005ee85  lea     rcx, [rbp+57h+var_70]
0x18005ee89  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18005ee8e  jmp     loc_18005EF81
0x18005ee93  mov     rdx, [rdi+8]
0x18005ee97  lea     r9, [rbp+57h+var_98]
0x18005ee9b  lea     r8, [rbp+57h+var_78]
0x18005ee9f  mov     rcx, rsi
0x18005eea2  call    XpathEvaluateFilter
0x18005eea7  mov     ebx, eax
0x18005eea9  test    eax, eax
0x18005eeab  js      short loc_18005EE7C
0x18005eead  mov     rbx, [rbp+57h+var_A0]
0x18005eeb1  mov     r9d, 5
0x18005eeb7  mov     rcx, qword ptr [rbp+57h+var_90]
0x18005eebb  mov     rdx, qword ptr [rbp+57h+var_90+8]
0x18005eebf  mov     [rbx+18h], r9d
0x18005eec3  lea     r8, [rbx+28h]
0x18005eec7  mov     rax, [r8+8]
0x18005eecb  mov     [r8+8], rcx
0x18005eecf  mov     rcx, [rbp+57h+var_98]
0x18005eed3  mov     qword ptr [rbp+57h+var_90], rax
0x18005eed7  mov     rax, [r8+10h]
0x18005eedb  mov     [r8+10h], rdx
0x18005eedf  mov     qword ptr [rbp+57h+var_90+8], rax
0x18005eee3  mov     rax, [r8]
0x18005eee6  mov     [r8], rcx
0x18005eee9  lea     rcx, [rbp+57h+var_90]
0x18005eeed  mov     [rbp+57h+var_98], rax
0x18005eef1  mov     [rbx+20h], r8
0x18005eef5  mov     [rbx+18h], r9d
0x18005eef9  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18005eefe  lea     rcx, [rbp+57h+var_70]
0x18005ef02  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18005ef07  jmp     short loc_18005EF6C
0x18005ef09  mov     rbx, [rbp+57h+var_A0]
0x18005ef0d  mov     dword ptr [rbx+18h], 4
0x18005ef14  mov     rax, [rdi+8]
0x18005ef18  mov     [rbx+20h], rax
0x18005ef1c  jmp     short loc_18005EF6C
0x18005ef1e  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18005ef25  mov     [rbp+57h+var_40], 111h
0x18005ef2d  mov     [rbp+57h+var_50.lpVtbl], rax
0x18005ef31  lea     rdx, [rbp+57h+var_50]
0x18005ef35  lea     rax, aXpathaddtermto; "XpathAddTermToExpression"
0x18005ef3c  mov     [rbp+57h+var_38], 0
0x18005ef44  mov     [rbp+57h+var_50.lpVtbl+8], rax
0x18005ef48  mov     r8d, 0C0000002h
0x18005ef4e  lea     rcx, [rbp+57h+var_30]
0x18005ef52  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18005ef57  mov     ebx, eax
0x18005ef59  jmp     short loc_18005EF81
0x18005ef5b  mov     rbx, [rbp+57h+var_A0]
0x18005ef5f  mov     dword ptr [rbx+18h], 3
0x18005ef66  mov     eax, [rdi+8]
0x18005ef69  mov     [rbx+20h], eax
0x18005ef6c  mov     rdx, rbx
0x18005ef6f  mov     [rbp+57h+var_A0], 0
0x18005ef77  mov     rcx, r14
0x18005ef7a  call    ?InsertAfterCurrent@?$CDequeIterator@UXpathExpressionTerm@@$0A@@BUCL@@QEAAXPEAUXpathExpressionTerm@@@Z; BUCL::CDequeIterator<XpathExpressionTerm,0>::InsertAfterCurrent(XpathExpressionTerm *)
0x18005ef7f  xor     ebx, ebx
0x18005ef81  lea     rcx, [rbp+57h+var_A0]
0x18005ef85  call    ??1?$Auto@PEAUXpathExpressionTerm@@@Windows@@QEAA@XZ; Windows::Auto<XpathExpressionTerm *>::~Auto<XpathExpressionTerm *>(void)
0x18005ef8a  mov     eax, ebx
0x18005ef8c  mov     rcx, [rbp+57h+var_28]
0x18005ef90  xor     rcx, rsp; StackCookie
0x18005ef93  call    __security_check_cookie
0x18005ef98  add     rsp, 0A0h
0x18005ef9f  pop     r14
0x18005efa1  pop     rdi
0x18005efa2  pop     rsi
0x18005efa3  pop     rbx
0x18005efa4  pop     rbp
0x18005efa5  retn
```
