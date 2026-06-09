# XpathAddTermToExpression

- ea: `0x18005e0c8`
- end: `0x18005e31f`
- name: `XpathAddTermToExpression`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005e8d8`

## callees

- `0x18001f554`
- `0x18001f5d4`
- `0x1800293a0`
- `0x180053f74`
- `0x18005d200`
- `0x18005d250`
- `0x18005d2e8`
- `0x18005d4c4`
- `0x18005e0c8`
- `0x18005eb40`

## string_xrefs

- `0x18005e112`: `onecore\base\xml\udom_xpath.cpp`
- `0x18005e174`: `onecore\base\xml\udom_xpath.cpp`
- `0x18005e296`: `onecore\base\xml\udom_xpath.cpp`
- `0x18005e129`: `XpathAddTermToExpression`
- `0x18005e18b`: `XpathAddTermToExpression`
- `0x18005e2ad`: `XpathAddTermToExpression`

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
0x18005e0c8  push    rbp
0x18005e0ca  push    rbx
0x18005e0cb  push    rsi
0x18005e0cc  push    rdi
0x18005e0cd  push    r14
0x18005e0cf  lea     rbp, [rsp-37h]
0x18005e0d4  sub     rsp, 0A0h
0x18005e0db  mov     rax, cs:__security_cookie
0x18005e0e2  xor     rax, rsp
0x18005e0e5  mov     [rbp+57h+var_28], rax
0x18005e0e9  mov     rsi, rcx
0x18005e0ec  mov     [rbp+57h+var_30], 0
0x18005e0f3  lea     rcx, [rbp+57h+var_A0]
0x18005e0f7  mov     [rbp+57h+var_A0], 0
0x18005e0ff  mov     r14, r9
0x18005e102  mov     rdi, r8
0x18005e105  mov     rbx, rdx
0x18005e108  call    ??$Allocate@$$V@?$AutoNewPtr@UXpathExpressionTerm@@@Windows@@QEAAPEAUXpathExpressionTerm@@XZ; Windows::AutoNewPtr<XpathExpressionTerm>::Allocate<>(void)
0x18005e10d  test    rax, rax
0x18005e110  jnz     short loc_18005E14D
0x18005e112  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18005e119  mov     qword ptr [rbp+57h+var_70+8], 0EAh
0x18005e121  mov     [rbp+57h+var_78], rax
0x18005e125  lea     rdx, [rbp+57h+var_78]
0x18005e129  lea     rax, aXpathaddtermto; "XpathAddTermToExpression"
0x18005e130  mov     qword ptr [rbp+57h+var_70], rax
0x18005e134  lea     rcx, [rbp+57h+var_30]
0x18005e138  lea     rax, aTermAllocate; "Term.Allocate()"
0x18005e13f  mov     [rbp+57h+var_60], rax
0x18005e143  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005e148  jmp     loc_18005E2CF
0x18005e14d  mov     ecx, [rdi]
0x18005e14f  sub     ecx, 1
0x18005e152  jz      loc_18005E2D3
0x18005e158  sub     ecx, 1
0x18005e15b  jz      loc_18005E296
0x18005e161  sub     ecx, 1
0x18005e164  jz      loc_18005E281
0x18005e16a  sub     ecx, 1
0x18005e16d  jz      short loc_18005E1B9
0x18005e16f  cmp     ecx, 1
0x18005e172  jz      short loc_18005E1A9
0x18005e174  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18005e17b  mov     qword ptr [rbp+57h+var_90+8], 114h
0x18005e183  mov     [rbp+57h+var_98], rax
0x18005e187  lea     rdx, [rbp+57h+var_98]
0x18005e18b  lea     rax, aXpathaddtermto; "XpathAddTermToExpression"
0x18005e192  mov     [rbp+57h+var_80], 0
0x18005e19a  mov     qword ptr [rbp+57h+var_90], rax
0x18005e19e  mov     r8d, 0C000000Dh
0x18005e1a4  jmp     loc_18005E2C6
0x18005e1a9  mov     rbx, [rbp+57h+var_A0]
0x18005e1ad  mov     dword ptr [rbx+18h], 1
0x18005e1b4  jmp     loc_18005E28C
0x18005e1b9  xorps   xmm0, xmm0
0x18005e1bc  mov     [rbp+57h+var_78], 0
0x18005e1c4  movdqu  [rbp+57h+var_70], xmm0
0x18005e1c9  lea     rdx, [rbp+57h+var_50]; struct Node
0x18005e1cd  mov     [rbp+57h+var_98], 0
0x18005e1d5  movaps  xmm0, xmmword ptr [rbx]
0x18005e1d8  lea     rcx, [rbp+57h+var_78]; this
0x18005e1dc  xorps   xmm1, xmm1
0x18005e1df  movdqa  xmmword ptr [rbp+57h+var_50.lpVtbl], xmm0
0x18005e1e4  movdqu  [rbp+57h+var_90], xmm1
0x18005e1e9  call    ?Add@CXpathEvaluationContext@@QEAAJUNode@Rtl@Microdom@Windows@@@Z; CXpathEvaluationContext::Add(Windows::Microdom::Rtl::Node)
0x18005e1ee  mov     ebx, eax
0x18005e1f0  test    eax, eax
0x18005e1f2  jns     short loc_18005E20B
0x18005e1f4  lea     rcx, [rbp+57h+var_90]
0x18005e1f8  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18005e1fd  lea     rcx, [rbp+57h+var_70]
0x18005e201  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18005e206  jmp     loc_18005E2F9
0x18005e20b  mov     rdx, [rdi+8]
0x18005e20f  lea     r9, [rbp+57h+var_98]
0x18005e213  lea     r8, [rbp+57h+var_78]
0x18005e217  mov     rcx, rsi
0x18005e21a  call    XpathEvaluateFilter
0x18005e21f  mov     ebx, eax
0x18005e221  test    eax, eax
0x18005e223  js      short loc_18005E1F4
0x18005e225  mov     rbx, [rbp+57h+var_A0]
0x18005e229  mov     r9d, 5
0x18005e22f  mov     rcx, qword ptr [rbp+57h+var_90]
0x18005e233  mov     rdx, qword ptr [rbp+57h+var_90+8]
0x18005e237  mov     [rbx+18h], r9d
0x18005e23b  lea     r8, [rbx+28h]
0x18005e23f  mov     rax, [r8+8]
0x18005e243  mov     [r8+8], rcx
0x18005e247  mov     rcx, [rbp+57h+var_98]
0x18005e24b  mov     qword ptr [rbp+57h+var_90], rax
0x18005e24f  mov     rax, [r8+10h]
0x18005e253  mov     [r8+10h], rdx
0x18005e257  mov     qword ptr [rbp+57h+var_90+8], rax
0x18005e25b  mov     rax, [r8]
0x18005e25e  mov     [r8], rcx
0x18005e261  lea     rcx, [rbp+57h+var_90]
0x18005e265  mov     [rbp+57h+var_98], rax
0x18005e269  mov     [rbx+20h], r8
0x18005e26d  mov     [rbx+18h], r9d
0x18005e271  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18005e276  lea     rcx, [rbp+57h+var_70]
0x18005e27a  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18005e27f  jmp     short loc_18005E2E4
0x18005e281  mov     rbx, [rbp+57h+var_A0]
0x18005e285  mov     dword ptr [rbx+18h], 4
0x18005e28c  mov     rax, [rdi+8]
0x18005e290  mov     [rbx+20h], rax
0x18005e294  jmp     short loc_18005E2E4
0x18005e296  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18005e29d  mov     [rbp+57h+var_40], 111h
0x18005e2a5  mov     [rbp+57h+var_50.lpVtbl], rax
0x18005e2a9  lea     rdx, [rbp+57h+var_50]
0x18005e2ad  lea     rax, aXpathaddtermto; "XpathAddTermToExpression"
0x18005e2b4  mov     [rbp+57h+var_38], 0
0x18005e2bc  mov     [rbp+57h+var_50.lpVtbl+8], rax
0x18005e2c0  mov     r8d, 0C0000002h
0x18005e2c6  lea     rcx, [rbp+57h+var_30]
0x18005e2ca  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18005e2cf  mov     ebx, eax
0x18005e2d1  jmp     short loc_18005E2F9
0x18005e2d3  mov     rbx, [rbp+57h+var_A0]
0x18005e2d7  mov     dword ptr [rbx+18h], 3
0x18005e2de  mov     eax, [rdi+8]
0x18005e2e1  mov     [rbx+20h], eax
0x18005e2e4  mov     rdx, rbx
0x18005e2e7  mov     [rbp+57h+var_A0], 0
0x18005e2ef  mov     rcx, r14
0x18005e2f2  call    ?InsertAfterCurrent@?$CDequeIterator@UXpathExpressionTerm@@$0A@@BUCL@@QEAAXPEAUXpathExpressionTerm@@@Z; BUCL::CDequeIterator<XpathExpressionTerm,0>::InsertAfterCurrent(XpathExpressionTerm *)
0x18005e2f7  xor     ebx, ebx
0x18005e2f9  lea     rcx, [rbp+57h+var_A0]
0x18005e2fd  call    ??1?$Auto@PEAUXpathExpressionTerm@@@Windows@@QEAA@XZ; Windows::Auto<XpathExpressionTerm *>::~Auto<XpathExpressionTerm *>(void)
0x18005e302  mov     eax, ebx
0x18005e304  mov     rcx, [rbp+57h+var_28]
0x18005e308  xor     rcx, rsp; StackCookie
0x18005e30b  call    __security_check_cookie
0x18005e310  add     rsp, 0A0h
0x18005e317  pop     r14
0x18005e319  pop     rdi
0x18005e31a  pop     rsi
0x18005e31b  pop     rbx
0x18005e31c  pop     rbp
0x18005e31d  retn
```
