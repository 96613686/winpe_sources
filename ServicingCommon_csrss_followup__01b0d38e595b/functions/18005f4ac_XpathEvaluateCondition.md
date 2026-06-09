# XpathEvaluateCondition

- ea: `0x18005f4ac`
- end: `0x18005f712`
- name: `XpathEvaluateCondition`
- size: `614`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005f820`

## callees

- `0x18001ad6c`
- `0x18001f1d8`
- `0x1800217cc`
- `0x18002d2b0`
- `0x18005dea0`
- `0x18005def0`
- `0x18005df18`
- `0x18005e164`
- `0x18005ed50`
- `0x18005f2bc`
- `0x18005f4ac`
- `0x18005fc34`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18005f6c6`
- `ntdll!RtlRaiseStatus` at `0x18005f6c6`

## string_xrefs

- `0x18005f555`: `onecore\base\xml\udom_xpath.cpp`
- `0x18005f5a6`: `onecore\base\xml\udom_xpath.cpp`
- `0x18005f56c`: `XpathEvaluateCondition`
- `0x18005f5bd`: `XpathEvaluateCondition`

## pseudocode

```c
__int64 __fastcall XpathEvaluateCondition(__int64 a1, __int64 a2, __int128 *a3, _BYTE *a4)
{
  _DWORD *v8; // r8
  int v9; // ebx
  int v10; // eax
  __int64 v11; // rdx
  const char *v12; // rdx
  const char *i; // rcx
  const char *v14; // rbx
  __int64 v15; // r8
  __int64 v16; // r8
  __int64 v18; // rcx
  __int128 v19; // [rsp+20h] [rbp-49h] BYREF
  const char *v20; // [rsp+30h] [rbp-39h] BYREF
  const char *v21; // [rsp+38h] [rbp-31h]
  __int64 v22; // [rsp+40h] [rbp-29h]
  const char *v23; // [rsp+48h] [rbp-21h]
  _QWORD v24[4]; // [rsp+50h] [rbp-19h] BYREF
  int v25; // [rsp+70h] [rbp+7h] BYREF
  _QWORD v26[3]; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+90h] [rbp+27h]

  v25 = 0;
  v26[0] = v26;
  v27 = 0;
  v26[1] = v26;
  v21 = 0;
  v26[2] = v26;
  v20 = (const char *)v26;
  BUCL::CConstDequeIterator<BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::CBucket,0>::Reset(&v20);
  if ( *(_DWORD *)a2 == 10 )
  {
    v8 = *(_DWORD **)(a2 + 8);
    if ( !v8 || *(_QWORD *)(a2 + 16) )
    {
      v22 = 722;
      v20 = "onecore\\base\\xml\\udom_xpath.cpp";
      v21 = "XpathEvaluateCondition";
      v23 = "(Condition.Left != 0) && (Condition.Right == 0)";
      v10 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
              &v25,
              &v20);
LABEL_19:
      v9 = v10;
      goto LABEL_20;
    }
    v19 = *a3;
    v9 = XpathAddTermToExpression(a1, &v19, v8, (__int64)&v20);
    if ( v9 < 0 )
      goto LABEL_20;
  }
  else
  {
    *(_QWORD *)&v19 = 0;
    if ( !Windows::AutoNewPtr<XpathExpressionTerm>::Allocate<>(&v19) )
    {
      v24[2] = 737;
      v24[0] = "onecore\\base\\xml\\udom_xpath.cpp";
      v24[1] = "XpathEvaluateCondition";
      v24[3] = "RootTerm.Allocate()";
      v9 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
             &v25,
             v24);
      Windows::Auto<XpathExpressionTerm *>::~Auto<XpathExpressionTerm *>(&v19);
LABEL_20:
      CDequeWithAutoPointerCleanup<XpathExpressionTerm,0>::~CDequeWithAutoPointerCleanup<XpathExpressionTerm,0>((BUCL::CDequeBase *)v26);
      return (unsigned int)v9;
    }
    v11 = v19;
    *(_QWORD *)&v19 = 0;
    *(_DWORD *)(v11 + 24) = 1;
    *(_QWORD *)(v11 + 32) = a2;
    BUCL::CDequeIterator<XpathExpressionTerm,0>::InsertAfterCurrent(&v20, v11);
    Windows::Auto<XpathExpressionTerm *>::~Auto<XpathExpressionTerm *>(&v19);
  }
  BUCL::CConstDequeIterator<BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::CBucket,0>::Reset(&v20);
  v12 = v20;
  for ( i = v21; i && i != v12; v21 = i )
  {
    v14 = i;
    if ( *((_DWORD *)i + 6) == 1 )
    {
      v15 = *((_QWORD *)i + 4);
      v19 = *a3;
      v10 = XpathAddTermToExpression(a1, &v19, *(_DWORD **)(v15 + 16), (__int64)&v20);
      if ( v10 < 0 )
        goto LABEL_19;
      v16 = *((_QWORD *)v14 + 4);
      v19 = *a3;
      v10 = XpathAddTermToExpression(a1, &v19, *(_DWORD **)(v16 + 8), (__int64)&v20);
      if ( v10 < 0 )
        goto LABEL_19;
      i = v21;
      v12 = v20;
    }
    i = *(const char **)i;
  }
  v10 = XpathCollapseExpression(a1, &v20);
  if ( v10 < 0 )
    goto LABEL_19;
  if ( v27 != 1 )
    RtlRaiseStatus(-1073741595);
  v18 = v26[0];
  if ( (_QWORD *)v26[0] == v26 )
    v18 = 0;
  *a4 = XpathTermToBoolean(v18);
  CDequeWithAutoPointerCleanup<XpathExpressionTerm,0>::~CDequeWithAutoPointerCleanup<XpathExpressionTerm,0>((BUCL::CDequeBase *)v26);
  return 0;
}

```

## disassembly

```asm
0x18005f4ac  push    rbp
0x18005f4ae  push    rbx
0x18005f4af  push    rsi
0x18005f4b0  push    rdi
0x18005f4b1  push    r14
0x18005f4b3  lea     rbp, [rsp-37h]
0x18005f4b8  sub     rsp, 0A0h
0x18005f4bf  mov     rax, cs:__security_cookie
0x18005f4c6  xor     rax, rsp
0x18005f4c9  mov     [rbp+57h+var_28], rax
0x18005f4cd  lea     rax, [rbp+57h+var_48]
0x18005f4d1  mov     [rbp+57h+var_50], 0
0x18005f4d8  mov     [rbp+57h+var_48], rax
0x18005f4dc  mov     rdi, rcx
0x18005f4df  lea     rax, [rbp+57h+var_48]
0x18005f4e3  mov     [rbp+57h+var_30], 0
0x18005f4eb  mov     [rbp+57h+var_40], rax
0x18005f4ef  lea     rcx, [rbp+57h+var_90]
0x18005f4f3  lea     rax, [rbp+57h+var_48]
0x18005f4f7  mov     [rbp+57h+var_88], 0
0x18005f4ff  mov     [rbp+57h+var_38], rax
0x18005f503  mov     r14, r9
0x18005f506  lea     rax, [rbp+57h+var_48]
0x18005f50a  mov     rsi, r8
0x18005f50d  mov     [rbp+57h+var_90], rax
0x18005f511  mov     rbx, rdx
0x18005f514  call    ?Reset@?$CConstDequeIterator@VCBucket@?$CTable@VCTableTraits@?$CFourStringIdTable@PEBU_MICRODOM_XML_ATTDEF@@@CMicrodomBuilder@@@HashTable@BUCL@@$0A@@BUCL@@QEAAXXZ; BUCL::CConstDequeIterator<BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::CBucket,0>::Reset(void)
0x18005f519  cmp     dword ptr [rbx], 0Ah
0x18005f51c  jnz     short loc_18005F590
0x18005f51e  mov     r8, [rbx+8]
0x18005f522  test    r8, r8
0x18005f525  jz      short loc_18005F555
0x18005f527  cmp     qword ptr [rbx+10h], 0
0x18005f52c  jnz     short loc_18005F555
0x18005f52e  movaps  xmm0, xmmword ptr [rsi]
0x18005f531  lea     r9, [rbp+57h+var_90]
0x18005f535  lea     rdx, [rbp+57h+var_A0]
0x18005f539  movdqa  [rbp+57h+var_A0], xmm0
0x18005f53e  mov     rcx, rdi
0x18005f541  call    XpathAddTermToExpression
0x18005f546  mov     ebx, eax
0x18005f548  test    eax, eax
0x18005f54a  jns     loc_18005F615
0x18005f550  jmp     loc_18005F6AD
0x18005f555  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18005f55c  mov     [rbp+57h+var_80], 2D2h
0x18005f564  mov     [rbp+57h+var_90], rax
0x18005f568  lea     rdx, [rbp+57h+var_90]
0x18005f56c  lea     rax, aXpathevaluatec; "XpathEvaluateCondition"
0x18005f573  mov     [rbp+57h+var_88], rax
0x18005f577  lea     rcx, [rbp+57h+var_50]
0x18005f57b  lea     rax, aConditionLeft0; "(Condition.Left != 0) && (Condition.Rig"...
0x18005f582  mov     [rbp+57h+var_78], rax
0x18005f586  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005f58b  jmp     loc_18005F6AB
0x18005f590  lea     rcx, [rbp+57h+var_A0]
0x18005f594  mov     qword ptr [rbp+57h+var_A0], 0
0x18005f59c  call    ??$Allocate@$$V@?$AutoNewPtr@UXpathExpressionTerm@@@Windows@@QEAAPEAUXpathExpressionTerm@@XZ; Windows::AutoNewPtr<XpathExpressionTerm>::Allocate<>(void)
0x18005f5a1  test    rax, rax
0x18005f5a4  jnz     short loc_18005F5EC
0x18005f5a6  lea     rax, aOnecoreBaseXml_6; "onecore\\base\\xml\\udom_xpath.cpp"
0x18005f5ad  mov     [rbp+57h+var_60], 2E1h
0x18005f5b5  mov     [rbp+57h+var_70], rax
0x18005f5b9  lea     rdx, [rbp+57h+var_70]
0x18005f5bd  lea     rax, aXpathevaluatec; "XpathEvaluateCondition"
0x18005f5c4  mov     [rbp+57h+var_68], rax
0x18005f5c8  lea     rcx, [rbp+57h+var_50]
0x18005f5cc  lea     rax, aRoottermAlloca; "RootTerm.Allocate()"
0x18005f5d3  mov     [rbp+57h+var_58], rax
0x18005f5d7  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005f5dc  lea     rcx, [rbp+57h+var_A0]
0x18005f5e0  mov     ebx, eax
0x18005f5e2  call    ??1?$Auto@PEAUXpathExpressionTerm@@@Windows@@QEAA@XZ; Windows::Auto<XpathExpressionTerm *>::~Auto<XpathExpressionTerm *>(void)
0x18005f5e7  jmp     loc_18005F6AD
0x18005f5ec  mov     rdx, qword ptr [rbp+57h+var_A0]
0x18005f5f0  lea     rcx, [rbp+57h+var_90]
0x18005f5f4  mov     qword ptr [rbp+57h+var_A0], 0
0x18005f5fc  mov     dword ptr [rdx+18h], 1
0x18005f603  mov     [rdx+20h], rbx
0x18005f607  call    ?InsertAfterCurrent@?$CDequeIterator@UXpathExpressionTerm@@$0A@@BUCL@@QEAAXPEAUXpathExpressionTerm@@@Z; BUCL::CDequeIterator<XpathExpressionTerm,0>::InsertAfterCurrent(XpathExpressionTerm *)
0x18005f60c  lea     rcx, [rbp+57h+var_A0]
0x18005f610  call    ??1?$Auto@PEAUXpathExpressionTerm@@@Windows@@QEAA@XZ; Windows::Auto<XpathExpressionTerm *>::~Auto<XpathExpressionTerm *>(void)
0x18005f615  lea     rcx, [rbp+57h+var_90]
0x18005f619  call    ?Reset@?$CConstDequeIterator@VCBucket@?$CTable@VCTableTraits@?$CFourStringIdTable@PEBU_MICRODOM_XML_ATTDEF@@@CMicrodomBuilder@@@HashTable@BUCL@@$0A@@BUCL@@QEAAXXZ; BUCL::CConstDequeIterator<BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::CBucket,0>::Reset(void)
0x18005f61e  mov     rdx, [rbp+57h+var_90]
0x18005f622  mov     rcx, [rbp+57h+var_88]
0x18005f626  test    rcx, rcx
0x18005f629  jz      short loc_18005F69B
0x18005f62b  cmp     rcx, rdx
0x18005f62e  jz      short loc_18005F69B
0x18005f630  xor     eax, eax
0x18005f632  mov     rbx, rcx
0x18005f635  cmp     rcx, rdx
0x18005f638  cmovz   rbx, rax
0x18005f63c  cmp     dword ptr [rbx+18h], 1
0x18005f640  jnz     short loc_18005F692
0x18005f642  mov     r8, [rbx+20h]
0x18005f646  lea     r9, [rbp+57h+var_90]
0x18005f64a  movaps  xmm0, xmmword ptr [rsi]
0x18005f64d  lea     rdx, [rbp+57h+var_A0]
0x18005f651  mov     rcx, rdi
0x18005f654  movdqa  [rbp+57h+var_A0], xmm0
0x18005f659  mov     r8, [r8+10h]
0x18005f65d  call    XpathAddTermToExpression
0x18005f662  test    eax, eax
0x18005f664  js      short loc_18005F6AB
0x18005f666  mov     r8, [rbx+20h]
0x18005f66a  lea     r9, [rbp+57h+var_90]
0x18005f66e  movaps  xmm0, xmmword ptr [rsi]
0x18005f671  lea     rdx, [rbp+57h+var_A0]
0x18005f675  mov     rcx, rdi
0x18005f678  movdqa  [rbp+57h+var_A0], xmm0
0x18005f67d  mov     r8, [r8+8]
0x18005f681  call    XpathAddTermToExpression
0x18005f686  test    eax, eax
0x18005f688  js      short loc_18005F6AB
0x18005f68a  mov     rcx, [rbp+57h+var_88]
0x18005f68e  mov     rdx, [rbp+57h+var_90]
0x18005f692  mov     rcx, [rcx]
0x18005f695  mov     [rbp+57h+var_88], rcx
0x18005f699  jmp     short loc_18005F626
0x18005f69b  lea     rdx, [rbp+57h+var_90]
0x18005f69f  mov     rcx, rdi
0x18005f6a2  call    XpathCollapseExpression
0x18005f6a7  test    eax, eax
0x18005f6a9  jns     short loc_18005F6BA
0x18005f6ab  mov     ebx, eax
0x18005f6ad  lea     rcx, [rbp+57h+var_48]; this
0x18005f6b1  call    ??1?$CDequeWithAutoPointerCleanup@UXpathExpressionTerm@@$0A@@@QEAA@XZ; CDequeWithAutoPointerCleanup<XpathExpressionTerm,0>::~CDequeWithAutoPointerCleanup<XpathExpressionTerm,0>(void)
0x18005f6b6  mov     eax, ebx
0x18005f6b8  jmp     short loc_18005F6F7
0x18005f6ba  cmp     [rbp+57h+var_30], 1
0x18005f6bf  jz      short loc_18005F6D3
0x18005f6c1  mov     ecx, 0C00000E5h; Status
0x18005f6c6  call    cs:__imp_RtlRaiseStatus
0x18005f6cd  nop     dword ptr [rax+rax+00h]
0x18005f6d2  int     3; Trap to Debugger
0x18005f6d3  mov     rcx, [rbp+57h+var_48]
0x18005f6d7  lea     rdx, [rbp+57h+var_48]
0x18005f6db  xor     eax, eax
0x18005f6dd  cmp     rcx, rdx
0x18005f6e0  cmovz   rcx, rax
0x18005f6e4  call    XpathTermToBoolean
0x18005f6e9  lea     rcx, [rbp+57h+var_48]; this
0x18005f6ed  mov     [r14], al
0x18005f6f0  call    ??1?$CDequeWithAutoPointerCleanup@UXpathExpressionTerm@@$0A@@@QEAA@XZ; CDequeWithAutoPointerCleanup<XpathExpressionTerm,0>::~CDequeWithAutoPointerCleanup<XpathExpressionTerm,0>(void)
0x18005f6f5  xor     eax, eax
0x18005f6f7  mov     rcx, [rbp+57h+var_28]
0x18005f6fb  xor     rcx, rsp; StackCookie
0x18005f6fe  call    __security_check_cookie
0x18005f703  add     rsp, 0A0h
0x18005f70a  pop     r14
0x18005f70c  pop     rdi
0x18005f70d  pop     rsi
0x18005f70e  pop     rbx
0x18005f70f  pop     rbp
0x18005f710  retn
```
