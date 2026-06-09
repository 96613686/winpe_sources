# FindingVisitor::Enter(UiaNode *,TraverseAction *,ulong *,IConnectionBase *)

- ea: `0x180049220`
- end: `0x180049912`
- name: `?Enter@FindingVisitor@@UEAAJPEAVUiaNode@@PEAW4TraverseAction@@PEAKPEAVIConnectionBase@@@Z`
- size: `1778`
- prototype: `__int64 __fastcall(FindingVisitor *__hidden this, struct UiaNode *, enum TraverseAction *, unsigned int *, struct IConnectionBase *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002ed38`
- `0x18002f530`
- `0x18002f580`
- `0x180046690`
- `0x180048ab0`
- `0x180049220`
- `0x180049be8`
- `0x180049c30`
- `0x18004a618`
- `0x1800c5a64`
- `0x1801e8344`
- `0x1801e88a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049292`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004943e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800495ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049292`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004943e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800495ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800492eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004949a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004962a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800492eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004949a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004962a`
- `OLEAUT32!__imp_VariantInit` at `0x180049334`
- `OLEAUT32!__imp_VariantInit` at `0x1800494e3`
- `OLEAUT32!__imp_VariantInit` at `0x180049334`
- `OLEAUT32!__imp_VariantInit` at `0x1800494e3`
- `OLEAUT32!__imp_VariantClear` at `0x18004939d`
- `OLEAUT32!__imp_VariantClear` at `0x18004954a`
- `OLEAUT32!__imp_VariantClear` at `0x1800497b7`
- `OLEAUT32!__imp_VariantClear` at `0x18004980b`
- `OLEAUT32!__imp_VariantClear` at `0x18004939d`
- `OLEAUT32!__imp_VariantClear` at `0x18004954a`
- `OLEAUT32!__imp_VariantClear` at `0x1800497b7`
- `OLEAUT32!__imp_VariantClear` at `0x18004980b`

## string_xrefs

- `0x180049675`: `onecore\windows\accessibletech\uiautomationcore\conditionhelper.cpp`
- `0x180049693`: `onecore\windows\accessibletech\uiautomationcore\conditionhelper.cpp`
- `0x18004970c`: `onecore\windows\accessibletech\uiautomationcore\conditionhelper.cpp`
- `0x18004975c`: `onecore\windows\accessibletech\uiautomationcore\conditionhelper.cpp`
- `0x180049796`: `onecore\windows\accessibletech\uiautomationcore\conditionhelper.cpp`
- `0x1800497e6`: `onecore\windows\accessibletech\uiautomationcore\conditionhelper.cpp`
- `0x1800496d2`: `onecore\windows\accessibletech\common\ArrayBuilder.h`
- `0x18004986c`: `onecore\windows\accessibletech\common\ArrayBuilder.h`
- `0x1800498e3`: `onecore\windows\accessibletech\common\ArrayBuilder.h`
- `0x18004963b`: `onecore\windows\accessibletech\uiautomationcore\elementfinder.cpp`
- `0x1800496f4`: `onecore\windows\accessibletech\uiautomationcore\SmartPointers.h`
- `0x180049744`: `onecore\windows\accessibletech\uiautomationcore\SmartPointers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall FindingVisitor::Enter(
        RTL_SRWLOCK *this,
        struct UiaNode *a2,
        enum TraverseAction *a3,
        unsigned int *a4)
{
  struct UiaCondition *Ptr; // r12
  unsigned int v6; // r15d
  int v7; // eax
  int v8; // edi
  unsigned int v9; // r14d
  int *v10; // rbx
  signed __int64 v11; // rsi
  void *v12; // rax
  void *v13; // rcx
  unsigned __int64 v14; // rax
  ICreateErrorInfo *v15; // r14
  int PropertyValues; // eax
  unsigned int i; // edi
  unsigned int *v18; // rdx
  int v19; // eax
  RTL_SRWLOCK *v20; // r12
  int v21; // eax
  int v22; // edi
  void *v23; // rbx
  signed __int64 v24; // rsi
  void *v25; // rcx
  void *v26; // rax
  unsigned __int64 v27; // rax
  ICreateErrorInfo *v28; // r14
  struct UiaNode *v29; // r15
  int v30; // eax
  __int64 k; // rdi
  volatile int *v32; // rdx
  int v33; // eax
  int v34; // ecx
  signed __int64 v36; // rax
  signed __int64 v37; // rtt
  int v38; // eax
  int v39; // ebx
  __int64 j; // r15
  unsigned __int64 v41; // rax
  int *v42; // rax
  __int64 v43; // rdx
  int v44; // eax
  unsigned __int64 v45; // rax
  void *v46; // rax
  int v47; // eax
  int v48; // [rsp+28h] [rbp-51h]
  int v49; // [rsp+28h] [rbp-51h]
  int v50; // [rsp+28h] [rbp-51h]
  int v51; // [rsp+28h] [rbp-51h]
  int v52; // [rsp+28h] [rbp-51h]
  struct UiaCondition *v53; // [rsp+38h] [rbp-41h]
  int v54; // [rsp+40h] [rbp-39h] BYREF
  ICreateErrorInfo *v55; // [rsp+48h] [rbp-31h]
  void *v56; // [rsp+50h] [rbp-29h] BYREF
  int v57; // [rsp+58h] [rbp-21h]
  void *Block; // [rsp+60h] [rbp-19h]
  int v59; // [rsp+68h] [rbp-11h]
  RTL_SRWLOCK SRWLock[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v61; // [rsp+80h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+57h]
  int v63; // [rsp+D8h] [rbp+5Fh]
  unsigned int *v66; // [rsp+F0h] [rbp+77h] BYREF

  v66 = a4;
  Ptr = (struct UiaCondition *)this[2].Ptr;
  v6 = 0;
  v63 = 0;
  v56 = 0;
  v57 = 0;
  Block = 0;
  v59 = 0;
  *(_OWORD *)&SRWLock[0].Ptr = 0;
  v61 = 0;
  v7 = ConditionHelper::ScrapeProperties(Ptr, &v56);
  v8 = v7;
  v9 = 162;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\conditionhelper.cpp",
      (const char *)(unsigned int)v7,
      v48);
    goto LABEL_19;
  }
  AcquireSRWLockExclusive(&SRWLock[1]);
  v10 = (int *)Block;
  v11 = ((char *)SRWLock[0].Ptr - (char *)Block) >> 2;
  v12 = v56;
  if ( !Block || Block != v56 )
  {
    v13 = 0;
    Block = 0;
    goto LABEL_5;
  }
  v41 = 4LL * (unsigned int)v11;
  if ( !is_mul_ok((unsigned int)v11, 4u) )
    v41 = -1;
  v42 = (int *)operator new[](v41, (const struct std::nothrow_t *)std::nothrow);
  v10 = v42;
  if ( v42 )
  {
    v44 = HrMemCopyItems<unsigned int>(v42, Block, (unsigned int)v11);
    if ( v44 >= 0 )
    {
      v13 = Block;
      v12 = v56;
LABEL_5:
      if ( v13 && v13 != v12 )
      {
        operator delete(v13);
        v12 = v56;
      }
      SRWLock[0].Ptr = v12;
      v59 = 0;
      Block = v12;
      goto LABEL_9;
    }
    v43 = 163;
  }
  else
  {
    v43 = 162;
    v44 = -2147024882;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v43,
    (unsigned int)"onecore\\windows\\accessibletech\\common\\ArrayBuilder.h",
    (const char *)(unsigned int)v44,
    v48);
  v10 = 0;
  LODWORD(v11) = 0;
LABEL_9:
  ReleaseSRWLockExclusive(&SRWLock[1]);
  v54 = 0;
  v14 = 24LL * (unsigned int)v11;
  if ( !is_mul_ok((unsigned int)v11, 0x18u) )
    v14 = -1;
  v15 = (ICreateErrorInfo *)operator new[](v14, (const struct std::nothrow_t *)std::nothrow);
  v55 = v15;
  if ( v15 )
  {
    if ( (_DWORD)v11 )
    {
      do
      {
        VariantInit((VARIANTARG *)&v15[3 * v6]);
        v15[3 * v6++ + 1].lpVtbl = 0;
      }
      while ( v6 < (unsigned int)v11 );
    }
    v54 = v11;
    v6 = 0;
    PropertyValues = UiaNode::CrossProcess_GetPropertyValues((struct UiaNode *)((char *)a2 + 48), 0, v11, v10, 0, v15);
    v8 = PropertyValues;
    if ( PropertyValues < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBA,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\conditionhelper.cpp",
        (const char *)(unsigned int)PropertyValues,
        v49);
      if ( (_DWORD)v11 )
      {
        do
          VariantClear((VARIANTARG *)&v15[3 * v6++]);
        while ( v6 < (unsigned int)v11 );
      }
      operator delete(v15);
      operator delete(v10);
      v6 = 0;
    }
    else
    {
      v63 = ConditionHelper::EvaluateCondition(Ptr, v11, v10, (struct tagVARIANT *)v15);
      for ( i = 0; i < (unsigned int)v11; ++i )
        VariantClear((VARIANTARG *)&v15[3 * i]);
      operator delete(v15);
      operator delete(v10);
      v8 = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x234,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\SmartPointers.h",
      (const char *)0x8007000ELL,
      v48);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\conditionhelper.cpp",
      (const char *)0x8007000ELL,
      v51);
    StructArrayPair<tagVARIANT>::SafeRelease(&v54);
    operator delete(v10);
    v8 = -2147024882;
  }
  v9 = 162;
LABEL_19:
  GrowableBuffer<int>::Reset(&v56);
  v18 = v66;
  *v66 |= 1u;
  v19 = 0;
  if ( v8 >= 0 )
    v19 = v63;
  if ( !v19 )
    return 0;
  *v18 |= 2u;
  v20 = this + 1;
  if ( LODWORD(this[3].Ptr) )
  {
    LODWORD(this[3].Ptr) = 0;
    goto LABEL_43;
  }
  v53 = (struct UiaCondition *)*((_QWORD *)v20->Ptr + 2);
  LODWORD(v66) = 0;
  v56 = 0;
  v57 = 0;
  Block = 0;
  v59 = 0;
  *(_OWORD *)&SRWLock[0].Ptr = 0;
  v61 = 0;
  v21 = ConditionHelper::ScrapeProperties(v53, &v56);
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\conditionhelper.cpp",
      (const char *)(unsigned int)v21,
      v49);
LABEL_62:
    v29 = a2;
    goto LABEL_40;
  }
  AcquireSRWLockExclusive(&SRWLock[1]);
  v23 = Block;
  v24 = ((char *)SRWLock[0].Ptr - (char *)Block) >> 2;
  v25 = v56;
  if ( !Block || Block != v56 )
  {
    v26 = 0;
    Block = 0;
    goto LABEL_27;
  }
  v45 = 4LL * (unsigned int)v24;
  if ( !is_mul_ok((unsigned int)v24, 4u) )
    v45 = -1;
  v46 = operator new[](v45, (const struct std::nothrow_t *)std::nothrow);
  v23 = v46;
  if ( !v46 )
  {
    v47 = -2147024882;
LABEL_90:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\ArrayBuilder.h",
      (const char *)(unsigned int)v47,
      v49);
    v23 = 0;
    LODWORD(v24) = 0;
    goto LABEL_31;
  }
  v47 = HrMemCopyItems<unsigned int>(v46, Block, (unsigned int)v24);
  if ( v47 < 0 )
  {
    v9 = 163;
    goto LABEL_90;
  }
  v26 = Block;
  v25 = v56;
LABEL_27:
  if ( v26 && v26 != v25 )
  {
    operator delete(v26);
    v25 = v56;
  }
  SRWLock[0].Ptr = v25;
  v59 = 0;
  Block = v25;
LABEL_31:
  ReleaseSRWLockExclusive(&SRWLock[1]);
  v54 = 0;
  v27 = 24LL * (unsigned int)v24;
  if ( !is_mul_ok((unsigned int)v24, 0x18u) )
    v27 = -1;
  v28 = (ICreateErrorInfo *)operator new[](v27, (const struct std::nothrow_t *)std::nothrow);
  v55 = v28;
  if ( !v28 )
  {
    v22 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x234,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\SmartPointers.h",
      (const char *)0x8007000ELL,
      v49);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\conditionhelper.cpp",
      (const char *)0x8007000ELL,
      v52);
    StructArrayPair<tagVARIANT>::SafeRelease(&v54);
LABEL_69:
    operator delete(v23);
    goto LABEL_62;
  }
  if ( (_DWORD)v24 )
  {
    do
    {
      VariantInit((VARIANTARG *)&v28[3 * v6]);
      v28[3 * v6++ + 1].lpVtbl = 0;
    }
    while ( v6 < (unsigned int)v24 );
  }
  v54 = v24;
  v29 = a2;
  v30 = UiaNode::CrossProcess_GetPropertyValues((struct UiaNode *)((char *)a2 + 48), 0, v24, (const int *)v23, 0, v28);
  v22 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\conditionhelper.cpp",
      (const char *)(unsigned int)v30,
      v50);
    for ( j = 0; (unsigned int)j < (unsigned int)v24; j = (unsigned int)(j + 1) )
      VariantClear((VARIANTARG *)&v28[3 * j]);
    operator delete(v28);
    goto LABEL_69;
  }
  LODWORD(v66) = ConditionHelper::EvaluateCondition(v53, v24, (int *)v23, (struct tagVARIANT *)v28);
  for ( k = 0; (unsigned int)k < (unsigned int)v24; k = (unsigned int)(k + 1) )
    VariantClear((VARIANTARG *)&v28[3 * k]);
  operator delete(v28);
  operator delete(v23);
  v22 = 0;
LABEL_40:
  GrowableBuffer<int>::Reset(&v56);
  v33 = 0;
  if ( v22 >= 0 )
    v33 = (int)v66;
  if ( !v33 )
    goto LABEL_43;
  v36 = *((_QWORD *)v29 + 9);
  while ( v36 >= 0 )
  {
    if ( (_DWORD)v36 != 0x7FFFFFFF )
    {
      v37 = v36;
      v36 = _InterlockedCompareExchange64((volatile signed __int64 *)v29 + 9, v36 + 1, v36);
      if ( v37 != v36 )
        continue;
    }
    goto LABEL_52;
  }
  Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(2 * v36 + 16), v32);
LABEL_52:
  AcquireSRWLockExclusive(this + 9);
  v66 = 0;
  v38 = GrowableBuffer<IUiaNode *>::Reserve(&this[4], 1, &v66);
  v39 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\ArrayBuilder.h",
      (const char *)(unsigned int)v38,
      v50);
  }
  else
  {
    *(_QWORD *)v66 = ((unsigned __int64)v29 + 48) & -(__int64)(v29 != 0);
    this[8].Ptr = (char *)this[8].Ptr + 8;
    v39 = 0;
  }
  if ( this != (RTL_SRWLOCK *)-72LL )
    ReleaseSRWLockExclusive(this + 9);
  if ( v39 >= 0 )
  {
    if ( *((_DWORD *)v20->Ptr + 1) )
    {
      *(_DWORD *)a3 = 2;
LABEL_44:
      ++HIDWORD(this[3].Ptr);
      return 0;
    }
LABEL_43:
    v34 = *(_DWORD *)v20->Ptr;
    if ( v34 != -1 && SHIDWORD(this[3].Ptr) >= v34 )
      *(_DWORD *)a3 = 1;
    goto LABEL_44;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5C,
    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\elementfinder.cpp",
    (const char *)(unsigned int)v39,
    v50);
  return (unsigned int)v39;
}

```

## disassembly

```asm
0x180049220  mov     rax, rsp
0x180049223  mov     [rax+20h], r9
0x180049227  mov     [rax+18h], r8
0x18004922b  mov     [rax+10h], rdx
0x18004922f  push    rbp
0x180049230  push    rbx
0x180049231  push    rsi
0x180049232  push    rdi
0x180049233  push    r12
0x180049235  push    r13
0x180049237  push    r14
0x180049239  push    r15
0x18004923b  lea     rbp, [rax-57h]
0x18004923f  sub     rsp, 88h
0x180049246  mov     r13, rcx
0x180049249  mov     r12, [rcx+10h]
0x18004924d  xor     r15d, r15d
0x180049250  mov     dword ptr [rbp+4Fh+arg_0], r15d
0x180049254  mov     [rbp+4Fh+var_78], r15
0x180049258  mov     [rbp+4Fh+var_70], r15d
0x18004925c  mov     [rbp+4Fh+Block], r15
0x180049260  mov     [rbp+4Fh+var_60], r15d
0x180049264  xorps   xmm0, xmm0
0x180049267  movdqu  xmmword ptr [rbp+4Fh+SRWLock.Ptr], xmm0
0x18004926c  xor     eax, eax
0x18004926e  mov     [rbp+4Fh+var_48], rax
0x180049272  lea     rdx, [rbp+4Fh+var_78]
0x180049276  mov     rcx, r12
0x180049279  call    ?ScrapeProperties@ConditionHelper@@CAJPEAUUiaCondition@@AEAV?$BasicArrayBuilder@H@@@Z; ConditionHelper::ScrapeProperties(UiaCondition *,BasicArrayBuilder<int> &)
0x18004927e  mov     edi, eax
0x180049280  mov     r14d, 0A2h
0x180049286  test    eax, eax
0x180049288  js      loc_18004966E
0x18004928e  lea     rcx, [rbp+4Fh+SRWLock.Ptr+8]; SRWLock
0x180049292  call    cs:__imp_AcquireSRWLockExclusive
0x180049298  mov     rbx, [rbp+4Fh+Block]
0x18004929c  mov     rsi, [rbp+4Fh+SRWLock.Ptr]
0x1800492a0  sub     rsi, rbx
0x1800492a3  sar     rsi, 2
0x1800492a7  mov     rax, [rbp+4Fh+var_78]
0x1800492ab  test    rbx, rbx
0x1800492ae  jz      short loc_1800492B9
0x1800492b0  cmp     rbx, rax
0x1800492b3  jz      loc_18004981E
0x1800492b9  mov     rcx, r15; Block
0x1800492bc  mov     [rbp+4Fh+Block], rcx
0x1800492c0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800492c4  test    rcx, rcx
0x1800492c7  jz      short loc_1800492D7
0x1800492c9  cmp     rcx, rax
0x1800492cc  jz      short loc_1800492D7
0x1800492ce  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800492d3  mov     rax, [rbp+4Fh+var_78]
0x1800492d7  mov     [rbp+4Fh+SRWLock.Ptr], rax
0x1800492db  mov     [rbp+4Fh+var_60], r15d
0x1800492df  mov     [rbp+4Fh+Block], rax
0x1800492e3  mov     [rbp+4Fh+var_90], rbx
0x1800492e7  lea     rcx, [rbp+4Fh+SRWLock.Ptr+8]; SRWLock
0x1800492eb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800492f1  mov     [rbp+4Fh+var_88], r15d
0x1800492f5  mov     ecx, esi
0x1800492f7  mov     eax, 18h
0x1800492fc  mul     rcx
0x1800492ff  cmovb   rax, rdi
0x180049303  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004930a  mov     rcx, rax; unsigned __int64
0x18004930d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180049312  mov     r14, rax
0x180049315  mov     [rbp+4Fh+var_80], rax
0x180049319  test    rax, rax
0x18004931c  jz      loc_1800496E8
0x180049322  test    esi, esi
0x180049324  jz      short loc_18004934A
0x180049326  mov     eax, r15d
0x180049329  lea     rcx, [rax+rax*2]
0x18004932d  lea     rdi, [r14+rcx*8]
0x180049331  mov     rcx, rdi; pvarg
0x180049334  call    cs:__imp_VariantInit
0x18004933a  mov     qword ptr [rdi+8], 0
0x180049342  inc     r15d
0x180049345  cmp     r15d, esi
0x180049348  jb      short loc_180049326
0x18004934a  mov     [rbp+4Fh+var_88], esi
0x18004934d  mov     rcx, [rbp+4Fh+arg_8]
0x180049351  add     rcx, 30h ; '0'; this
0x180049355  mov     qword ptr [rsp+0C0h+var_A0+8], r14; pperrinfo
0x18004935a  xor     r15d, r15d
0x18004935d  mov     [rsp+0C0h+var_A0], r15d; int
0x180049362  mov     r9, rbx; int *
0x180049365  mov     r8d, esi; unsigned int
0x180049368  xor     edx, edx; int
0x18004936a  call    ?CrossProcess_GetPropertyValues@UiaNode@@UEAAJHIPEBHHPEAUtagVARIANT@@@Z; UiaNode::CrossProcess_GetPropertyValues(int,uint,int const *,int,tagVARIANT *)
0x18004936f  mov     edi, eax
0x180049371  test    eax, eax
0x180049373  js      loc_18004978F
0x180049379  mov     r9, r14; struct tagVARIANT *
0x18004937c  mov     r8, rbx; int *
0x18004937f  mov     edx, esi; int
0x180049381  mov     rcx, r12; struct UiaCondition *
0x180049384  call    ?EvaluateCondition@ConditionHelper@@CAHPEAUUiaCondition@@HPEAHPEAUtagVARIANT@@@Z; ConditionHelper::EvaluateCondition(UiaCondition *,int,int *,tagVARIANT *)
0x180049389  mov     dword ptr [rbp+4Fh+arg_0], eax
0x18004938c  mov     edi, r15d
0x18004938f  test    esi, esi
0x180049391  jz      short loc_1800493A9
0x180049393  mov     ecx, edi
0x180049395  lea     rdx, [rcx+rcx*2]
0x180049399  lea     rcx, [r14+rdx*8]; pvarg
0x18004939d  call    cs:__imp_VariantClear
0x1800493a3  inc     edi
0x1800493a5  cmp     edi, esi
0x1800493a7  jb      short loc_180049393
0x1800493a9  mov     rcx, r14; Block
0x1800493ac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800493b1  nop
0x1800493b2  mov     rcx, rbx; Block
0x1800493b5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800493ba  nop
0x1800493bb  mov     edi, r15d
0x1800493be  mov     r14d, 0A2h
0x1800493c4  lea     rcx, [rbp+4Fh+var_78]
0x1800493c8  call    ?Reset@?$GrowableBuffer@H@@QEAAXXZ; GrowableBuffer<int>::Reset(void)
0x1800493cd  mov     rdx, [rbp+4Fh+arg_18]
0x1800493d1  or      dword ptr [rdx], 1
0x1800493d4  mov     eax, r15d
0x1800493d7  test    edi, edi
0x1800493d9  cmovns  eax, dword ptr [rbp+4Fh+arg_0]
0x1800493dd  test    eax, eax
0x1800493df  jz      loc_18004958E
0x1800493e5  or      dword ptr [rdx], 2
0x1800493e8  lea     r12, [r13+8]
0x1800493ec  cmp     [r13+18h], r15d
0x1800493f0  jnz     loc_180049653
0x1800493f6  mov     rax, [r12]
0x1800493fa  mov     rax, [rax+10h]
0x1800493fe  mov     [rbp+4Fh+var_90], rax
0x180049402  mov     dword ptr [rbp+4Fh+arg_18], r15d
0x180049406  mov     [rbp+4Fh+var_78], r15
0x18004940a  mov     [rbp+4Fh+var_70], r15d
0x18004940e  mov     [rbp+4Fh+Block], r15
0x180049412  mov     [rbp+4Fh+var_60], r15d
0x180049416  xorps   xmm0, xmm0
0x180049419  movdqu  xmmword ptr [rbp+4Fh+SRWLock.Ptr], xmm0
0x18004941e  xor     ecx, ecx
0x180049420  mov     [rbp+4Fh+var_48], rcx
0x180049424  lea     rdx, [rbp+4Fh+var_78]
0x180049428  mov     rcx, rax
0x18004942b  call    ?ScrapeProperties@ConditionHelper@@CAJPEAUUiaCondition@@AEAV?$BasicArrayBuilder@H@@@Z; ConditionHelper::ScrapeProperties(UiaCondition *,BasicArrayBuilder<int> &)
0x180049430  mov     edi, eax
0x180049432  test    eax, eax
0x180049434  js      loc_18004968C
0x18004943a  lea     rcx, [rbp+4Fh+SRWLock.Ptr+8]; SRWLock
0x18004943e  call    cs:__imp_AcquireSRWLockExclusive
0x180049444  mov     rbx, [rbp+4Fh+Block]
0x180049448  mov     rsi, [rbp+4Fh+SRWLock.Ptr]
0x18004944c  sub     rsi, rbx
0x18004944f  sar     rsi, 2
0x180049453  mov     rcx, [rbp+4Fh+var_78]
0x180049457  test    rbx, rbx
0x18004945a  jz      short loc_180049465
0x18004945c  cmp     rbx, rcx
0x18004945f  jz      loc_180049897
0x180049465  mov     rax, r15
0x180049468  mov     [rbp+4Fh+Block], rax
0x18004946c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180049470  test    rax, rax
0x180049473  jz      short loc_180049486
0x180049475  cmp     rax, rcx
0x180049478  jz      short loc_180049486
0x18004947a  mov     rcx, rax; Block
0x18004947d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180049482  mov     rcx, [rbp+4Fh+var_78]
0x180049486  mov     [rbp+4Fh+SRWLock.Ptr], rcx
0x18004948a  mov     [rbp+4Fh+var_60], r15d
0x18004948e  mov     [rbp+4Fh+Block], rcx
0x180049492  mov     [rbp+4Fh+arg_0], rbx
0x180049496  lea     rcx, [rbp+4Fh+SRWLock.Ptr+8]; SRWLock
0x18004949a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800494a0  mov     [rbp+4Fh+var_88], r15d
0x1800494a4  mov     ecx, esi
0x1800494a6  mov     eax, 18h
0x1800494ab  mul     rcx
0x1800494ae  cmovb   rax, rdi
0x1800494b2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800494b9  mov     rcx, rax; unsigned __int64
0x1800494bc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800494c1  mov     r14, rax
0x1800494c4  mov     [rbp+4Fh+var_80], rax
0x1800494c8  test    rax, rax
0x1800494cb  jz      loc_180049738
0x1800494d1  test    esi, esi
0x1800494d3  jz      short loc_1800494F9
0x1800494d5  mov     eax, r15d
0x1800494d8  lea     rcx, [rax+rax*2]
0x1800494dc  lea     rdi, [r14+rcx*8]
0x1800494e0  mov     rcx, rdi; pvarg
0x1800494e3  call    cs:__imp_VariantInit
0x1800494e9  mov     qword ptr [rdi+8], 0
0x1800494f1  inc     r15d
0x1800494f4  cmp     r15d, esi
0x1800494f7  jb      short loc_1800494D5
0x1800494f9  mov     [rbp+4Fh+var_88], esi
0x1800494fc  mov     r15, [rbp+4Fh+arg_8]
0x180049500  lea     rcx, [r15+30h]; this
0x180049504  mov     qword ptr [rsp+0C0h+var_A0+8], r14; pperrinfo
0x180049509  mov     [rsp+0C0h+var_A0], 0; int
0x180049511  mov     r9, rbx; int *
0x180049514  mov     r8d, esi; unsigned int
0x180049517  xor     edx, edx; int
0x180049519  call    ?CrossProcess_GetPropertyValues@UiaNode@@UEAAJHIPEBHHPEAUtagVARIANT@@@Z; UiaNode::CrossProcess_GetPropertyValues(int,uint,int const *,int,tagVARIANT *)
0x18004951e  mov     edi, eax
0x180049520  test    eax, eax
0x180049522  js      loc_1800497DF
0x180049528  mov     r9, r14; struct tagVARIANT *
0x18004952b  mov     r8, rbx; int *
0x18004952e  mov     edx, esi; int
0x180049530  mov     rcx, [rbp+4Fh+var_90]; struct UiaCondition *
0x180049534  call    ?EvaluateCondition@ConditionHelper@@CAHPEAUUiaCondition@@HPEAHPEAUtagVARIANT@@@Z; ConditionHelper::EvaluateCondition(UiaCondition *,int,int *,tagVARIANT *)
0x180049539  mov     dword ptr [rbp+4Fh+arg_18], eax
0x18004953c  xor     edi, edi
0x18004953e  test    esi, esi
0x180049540  jz      short loc_180049556
0x180049542  lea     rdx, [rdi+rdi*2]
0x180049546  lea     rcx, [r14+rdx*8]; pvarg
0x18004954a  call    cs:__imp_VariantClear
0x180049550  inc     edi
0x180049552  cmp     edi, esi
0x180049554  jb      short loc_180049542
0x180049556  mov     rcx, r14; Block
0x180049559  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004955e  nop
0x18004955f  mov     rcx, rbx; Block
0x180049562  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180049567  nop
0x180049568  xor     edi, edi
0x18004956a  lea     rcx, [rbp+4Fh+var_78]
0x18004956e  call    ?Reset@?$GrowableBuffer@H@@QEAAXXZ; GrowableBuffer<int>::Reset(void)
0x180049573  xor     eax, eax
0x180049575  test    edi, edi
0x180049577  cmovns  eax, dword ptr [rbp+4Fh+arg_18]
0x18004957b  test    eax, eax
0x18004957d  jnz     short loc_1800495B6
0x18004957f  mov     rax, [r12]
0x180049583  mov     ecx, [rax]
0x180049585  cmp     ecx, 0FFFFFFFFh
0x180049588  jnz     short loc_1800495A4
0x18004958a  inc     dword ptr [r13+1Ch]
0x18004958e  xor     eax, eax
0x180049590  add     rsp, 88h
0x180049597  pop     r15
0x180049599  pop     r14
0x18004959b  pop     r13
0x18004959d  pop     r12
0x18004959f  pop     rdi
0x1800495a0  pop     rsi
0x1800495a1  pop     rbx
0x1800495a2  pop     rbp
0x1800495a3  retn
0x1800495a4  cmp     [r13+1Ch], ecx
0x1800495a8  jl      short loc_18004958A
0x1800495aa  mov     rax, [rbp+4Fh+arg_10]
0x1800495ae  mov     dword ptr [rax], 1
0x1800495b4  jmp     short loc_18004958A
0x1800495b6  mov     rax, [r15+48h]
0x1800495ba  test    rax, rax
0x1800495bd  js      loc_18004965C
0x1800495c3  cmp     eax, 7FFFFFFFh
0x1800495c8  jz      short loc_1800495D6
0x1800495ca  lea     rcx, [rax+1]
0x1800495ce  lock cmpxchg [r15+48h], rcx
0x1800495d4  jnz     short loc_1800495BA
0x1800495d6  lea     rax, [r15+30h]
0x1800495da  neg     r15
0x1800495dd  sbb     r14, r14
0x1800495e0  and     r14, rax
0x1800495e3  lea     rsi, [r13+48h]
0x1800495e7  mov     rcx, rsi; SRWLock
0x1800495ea  call    cs:__imp_AcquireSRWLockExclusive
0x1800495f0  mov     [rbp+4Fh+arg_18], 0
0x1800495f8  lea     r8, [rbp+4Fh+arg_18]
0x1800495fc  mov     edx, 1
0x180049601  lea     rcx, [r13+20h]
0x180049605  call    ?Reserve@?$GrowableBuffer@PEAVIUiaNode@@@@QEAAJIPEAPEAPEAVIUiaNode@@@Z; GrowableBuffer<IUiaNode *>::Reserve(uint,IUiaNode * * *)
0x18004960a  mov     ebx, eax
0x18004960c  test    eax, eax
0x18004960e  js      loc_1800496CB
0x180049614  mov     rax, [rbp+4Fh+arg_18]
0x180049618  mov     [rax], r14
0x18004961b  add     qword ptr [r13+40h], 8
0x180049620  xor     ebx, ebx
0x180049622  test    rsi, rsi
0x180049625  jz      short loc_180049630
0x180049627  mov     rcx, rsi; SRWLock
0x18004962a  call    cs:__imp_ReleaseSRWLockExclusive
0x180049630  test    ebx, ebx
0x180049632  jns     short loc_1800496AE
0x180049634  mov     rcx, [rbp+57h]; this
0x180049638  mov     r9d, ebx; char *
0x18004963b  lea     r8, aOnecoreWindows_176; "onecore\\windows\\accessibletech\\uiaut"...
0x180049642  mov     edx, 5Ch ; '\'; void *
0x180049647  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
