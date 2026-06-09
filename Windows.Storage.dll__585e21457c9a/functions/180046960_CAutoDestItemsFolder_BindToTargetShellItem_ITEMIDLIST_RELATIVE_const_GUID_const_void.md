# CAutoDestItemsFolder::_BindToTargetShellItem(_ITEMIDLIST_RELATIVE const *,_GUID const &,void * *)

- ea: `0x180046960`
- end: `0x180047083`
- name: `?_BindToTargetShellItem@CAutoDestItemsFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@PEAPEAX@Z`
- size: `1827`
- prototype: `__int64 __fastcall(CAutoDestItemsFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, const struct _GUID *, void **)`
- caller_count: `9`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011c10`
- `0x1800679b8`
- `0x1801adf18`
- `0x1801ae090`
- `0x1801ae260`
- `0x180331230`
- `0x180613990`
- `0x180614a30`
- `0x1806183b0`

## callees

- `0x180012840`
- `0x1800432f0`
- `0x180046200`
- `0x180046830`
- `0x180046960`
- `0x180047ec0`
- `0x180048030`
- `0x180049980`
- `0x1800c64f0`
- `0x1801471bc`
- `0x1803a4cb0`
- `0x1803a513c`
- `0x1803a518c`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180046d1b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180046d1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047011`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004702e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004704c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004706a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047011`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004702e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004704c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004706a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004701f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004703c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004705a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047078`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004701f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004703c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004705a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047078`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046a2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046a8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046b1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046b7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046a2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046a8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046b1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046b7e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800469b9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180046ac6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800469b9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180046ac6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046c2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046e71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046ede`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046c2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046e71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046ede`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180046be2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180046cb1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180046ff9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180046be2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180046cb1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180046ff9`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180046c77`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180046c77`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAutoDestItemsFolder::_BindToTargetShellItem(
        CAutoDestItemsFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v7; // rdi
  DWORD CurrentThreadId; // ebx
  unsigned __int64 v9; // r8
  __int64 v10; // rsi
  __int64 i; // rax
  __int64 *v12; // rcx
  __int64 v13; // rdi
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // r8
  __int64 v16; // rsi
  __int64 j; // rax
  __int64 *v18; // rcx
  unsigned int v19; // edi
  unsigned __int64 v20; // rax
  __int64 v21; // rdx
  void *v22; // rcx
  int v24; // eax
  LPVOID v25; // r14
  int inited; // esi
  CMarshalByValue *v27; // rax
  CMarshalByValue *v28; // rdi
  __int64 v29; // rcx
  void *v30; // rcx
  void *v31; // rcx
  char *v32; // rax
  signed __int64 v33; // rdx
  signed __int64 v34; // rax
  char *v35; // rax
  signed __int64 v36; // rdx
  signed __int64 v37; // rax
  void *v38; // rbx
  HANDLE v39; // rax
  void *v40; // rbx
  HANDLE ProcessHeap; // rax
  void *v42; // rbx
  HANDLE v43; // rax
  void *v44; // rbx
  HANDLE v45; // rax
  union _RTL_RUN_ONCE *v46; // [rsp+20h] [rbp-E0h] BYREF
  int v47; // [rsp+28h] [rbp-D8h]
  WINBOOL fPending[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v52; // [rsp+58h] [rbp-A8h]
  int v53; // [rsp+60h] [rbp-A0h] BYREF
  const char *v54; // [rsp+68h] [rbp-98h]
  LPVOID v55; // [rsp+70h] [rbp-90h]
  char v56; // [rsp+78h] [rbp-88h]
  _QWORD v57[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v58; // [rsp+90h] [rbp-70h]
  DWORD v59; // [rsp+98h] [rbp-68h]
  int *v60; // [rsp+A0h] [rbp-60h]
  char v61; // [rsp+A8h] [rbp-58h]
  int v62; // [rsp+B0h] [rbp-50h] BYREF
  const char *v63; // [rsp+B8h] [rbp-48h]
  LPVOID lpMem; // [rsp+C0h] [rbp-40h]
  char v65; // [rsp+C8h] [rbp-38h]
  _QWORD v66[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v67; // [rsp+E0h] [rbp-20h]
  DWORD v68; // [rsp+E8h] [rbp-18h]
  int *v69; // [rsp+F0h] [rbp-10h]
  char v70; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  *a4 = 0;
  Context = 0;
  fPending[0] = 0;
  if ( InitOnceBeginInitialize(&`FavoritesTelemetry::Instance'::`2'::wrapper, 0, fPending, &Context) && fPending[0] )
  {
    v46 = &`FavoritesTelemetry::Instance'::`2'::wrapper;
    Context = &qword_180808C68;
    qword_180808C70 = 0;
    byte_180808C78 = 0;
    dword_180808C7C = 0;
    qword_180808C68 = (__int64)&FileExplorerTelemetry::`vftable';
    atexit(_lambda_6d1781482f98053d9c23f1daeac3d9b0_::_lambda_invoker_cdecl_);
    v47 = 0;
    wil::details::static_lazy<FileExplorerTelemetry>::Completer::~Completer(&v46);
  }
  v56 = 0;
  v53 = 0;
  v54 = "CAutoDestItemsFolder::_BindToTargetShellItem";
  v55 = 0;
  v57[0] = 0;
  v57[1] = Context;
  v58 = 0;
  v59 = 0;
  v60 = &v53;
  v61 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
    v10 = 8 * v9;
    for ( i = *(_QWORD *)(8 * v9 + v7); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == CurrentThreadId )
      {
        v12 = (__int64 *)(i + 16);
        goto LABEL_10;
      }
    }
    v32 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, v9);
    v33 = (signed __int64)v32;
    if ( v32 )
    {
      *(_DWORD *)v32 = CurrentThreadId;
      *((_DWORD *)v32 + 1) = 0;
      *((_QWORD *)v32 + 1) = 0;
      v12 = (__int64 *)(v32 + 16);
      *((_QWORD *)v32 + 2) = 0;
      do
      {
        v34 = *(_QWORD *)(v10 + v7);
        *(_QWORD *)(v33 + 8) = v34;
      }
      while ( v34 != _InterlockedCompareExchange64((volatile signed __int64 *)(v10 + v7), v33, v34) );
    }
    else
    {
      v12 = 0;
    }
LABEL_10:
    v57[0] = v12;
    if ( v12 )
    {
      v58 = *v12;
      *v12 = (__int64)v57;
      v59 = GetCurrentThreadId();
    }
  }
  pv = 0;
  Context = 0;
  fPending[0] = 0;
  if ( InitOnceBeginInitialize(&`FavoritesTelemetry::Instance'::`2'::wrapper, 0, fPending, &Context) && fPending[0] )
  {
    v46 = &`FavoritesTelemetry::Instance'::`2'::wrapper;
    Context = &qword_180808C68;
    qword_180808C70 = 0;
    byte_180808C78 = 0;
    dword_180808C7C = 0;
    qword_180808C68 = (__int64)&FileExplorerTelemetry::`vftable';
    atexit(_lambda_6d1781482f98053d9c23f1daeac3d9b0_::_lambda_invoker_cdecl_);
    v47 = 0;
    wil::details::static_lazy<FileExplorerTelemetry>::Completer::~Completer(&v46);
  }
  v65 = 0;
  v62 = 0;
  v63 = "CAutoDestItemsFolder::_GetTargetAbsolutePIDL";
  lpMem = 0;
  v66[0] = 0;
  v66[1] = Context;
  v67 = 0;
  v68 = 0;
  v69 = &v62;
  v70 = 0;
  v13 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    v14 = GetCurrentThreadId();
    v15 = (v14 >> 2) % 0xA;
    v16 = 8 * v15;
    for ( j = *(_QWORD *)(v13 + 8 * v15); j; j = *(_QWORD *)(j + 8) )
    {
      if ( *(_DWORD *)j == (_DWORD)v14 )
      {
        v18 = (__int64 *)(j + 16);
        goto LABEL_21;
      }
    }
    v35 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, v15);
    v36 = (signed __int64)v35;
    if ( v35 )
    {
      *(_DWORD *)v35 = v14;
      *((_DWORD *)v35 + 1) = 0;
      *((_QWORD *)v35 + 1) = 0;
      v18 = (__int64 *)(v35 + 16);
      *((_QWORD *)v35 + 2) = 0;
      do
      {
        v37 = *(_QWORD *)(v16 + v13);
        *(_QWORD *)(v36 + 8) = v37;
      }
      while ( v37 != _InterlockedCompareExchange64((volatile signed __int64 *)(v13 + v16), v36, v37) );
    }
    else
    {
      v18 = 0;
    }
LABEL_21:
    v66[0] = v18;
    if ( v18 )
    {
      v67 = *v18;
      *v18 = (__int64)v66;
      v68 = GetCurrentThreadId();
    }
  }
  *(_OWORD *)pvar = 0;
  v52 = 0;
  v19 = -2147024809;
  if ( !a2 )
    goto LABEL_27;
  v20 = *(unsigned __int16 *)a2;
  if ( (unsigned int)v20 < 0xF )
    goto LABEL_27;
  if ( *(_DWORD *)((char *)a2 + 6) != 203342025 )
    goto LABEL_27;
  v21 = *((unsigned __int16 *)a2 + 5);
  if ( v20 < v21 + 15 )
    goto LABEL_27;
  if ( !(_WORD)v21 )
    goto LABEL_27;
  if ( a2 == (const struct _ITEMIDLIST_RELATIVE *)-15LL )
    goto LABEL_27;
  v19 = PSGetPropertyFromPropertyStorage(
          (const struct _ITEMIDLIST_RELATIVE *)((char *)a2 + 15),
          v21,
          &PKEY_DelegateIDList,
          pvar);
  if ( (v19 & 0x80000000) != 0 )
    goto LABEL_27;
  if ( !LOWORD(pvar[0]) )
  {
    v19 = -2147023288;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8DB,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
      (const char *)v19,
      (int)v46);
    PropVariantClear(pvar);
    if ( v68 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v66);
    if ( v65 )
    {
      v40 = lpMem;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v40);
    }
    goto LABEL_31;
  }
  v24 = PropVariantToIDList(pvar, &pv);
  v19 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8DC,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
      (const char *)(unsigned int)v24,
      (int)v46);
    PropVariantClear(pvar);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)&v62);
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E9,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
      (const char *)v19,
      (int)v46);
    v22 = pv;
    pv = 0;
    CoTaskMemFree(v22);
    if ( v59 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v57);
    wil::details::StoredCallContextInfo::ClearMessage((wil::details::StoredCallContextInfo *)&v53);
    return v19;
  }
  PropVariantClear(pvar);
  if ( v68 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v66);
  if ( v65 )
  {
    v38 = lpMem;
    v39 = GetProcessHeap();
    HeapFree(v39, 0, v38);
  }
  v25 = pv;
  *a4 = 0;
  *(_QWORD *)fPending = 0;
  inited = -2147024882;
  v27 = (CMarshalByValue *)operator new(0xD8u, (const struct std::nothrow_t *)&std::nothrow);
  v28 = v27;
  if ( !v27 )
    goto LABEL_55;
  CMarshalByValue::CMarshalByValue(v27);
  *(_DWORD *)(v29 + 120) = -2;
  *(_DWORD *)(v29 + 124) = 1;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v29 + 80));
  *(_QWORD *)v28 = &CShellItem::`vftable'{for `CMarshalByValue'};
  *((_QWORD *)v28 + 1) = &CShellItem::`vftable'{for `IShellItem2'};
  *((_QWORD *)v28 + 2) = &CShellItem::`vftable'{for `IShellItemImageFactoryPriv'};
  *((_QWORD *)v28 + 3) = &CShellItem::`vftable'{for `IPersistIDList'};
  *((_QWORD *)v28 + 4) = &CShellItem::`vftable'{for `IParentAndItem'};
  *((_QWORD *)v28 + 5) = &CShellItem::`vftable'{for `IPersistStream'};
  *((_QWORD *)v28 + 6) = &CShellItem::`vftable'{for `ICacheableObject'};
  *((_QWORD *)v28 + 7) = &CShellItem::`vftable'{for `IChildId'};
  *((_QWORD *)v28 + 8) = &CShellItem::`vftable'{for `IObjectWithBackReferences'};
  *((_QWORD *)v28 + 9) = &CShellItem::`vftable'{for `IInitializeWithFolder'};
  *((_DWORD *)v28 + 32) = 1;
  *((_QWORD *)v28 + 17) = 0;
  *((_QWORD *)v28 + 18) = 0;
  *((_QWORD *)v28 + 19) = 0;
  *((_QWORD *)v28 + 20) = 0;
  *((_QWORD *)v28 + 21) = 0;
  *((_QWORD *)v28 + 22) = 0;
  *((_QWORD *)v28 + 23) = 0;
  *((_QWORD *)v28 + 24) = 0;
  *((_QWORD *)v28 + 25) = 0;
  *((_DWORD *)v28 + 52) = 0;
  inited = CObjectWithThreadUseDetection::InitApartmentId((CMarshalByValue *)((char *)v28 + 80));
  if ( inited >= 0 )
    inited = (**(__int64 (__fastcall ***)(CMarshalByValue *, GUID *, WINBOOL *))v28)(
               v28,
               &GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5,
               fPending);
  (*(void (__fastcall **)(CMarshalByValue *))(*(_QWORD *)v28 + 16LL))(v28);
  if ( inited < 0 )
    goto LABEL_55;
  inited = (*(__int64 (__fastcall **)(_QWORD, LPVOID))(**(_QWORD **)fPending + 32LL))(*(_QWORD *)fPending, v25);
  if ( inited >= 0 )
    inited = (***(__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))fPending)(
               *(_QWORD *)fPending,
               a3,
               a4);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)fPending + 16LL))(*(_QWORD *)fPending);
  if ( inited >= 0 )
  {
    v30 = pv;
    pv = 0;
    CoTaskMemFree(v30);
    if ( v59 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v57);
    if ( v56 )
    {
      v42 = v55;
      v43 = GetProcessHeap();
      HeapFree(v43, 0, v42);
    }
    return 0;
  }
  else
  {
LABEL_55:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8EA,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
      (const char *)(unsigned int)inited,
      (int)v46);
    v31 = pv;
    pv = 0;
    CoTaskMemFree(v31);
    if ( v59 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v57);
    if ( v56 )
    {
      v44 = v55;
      v45 = GetProcessHeap();
      HeapFree(v45, 0, v44);
    }
    return (unsigned int)inited;
  }
}

```

## disassembly

```asm
0x180046960  mov     [rsp-8+arg_0], rbx
0x180046965  push    rbp
0x180046966  push    rsi
0x180046967  push    rdi
0x180046968  push    r12
0x18004696a  push    r13
0x18004696c  push    r14
0x18004696e  push    r15
0x180046970  lea     rbp, [rsp-10h]
0x180046975  sub     rsp, 110h
0x18004697c  mov     rax, cs:__security_cookie
0x180046983  xor     rax, rsp
0x180046986  mov     [rbp+40h+var_40], rax
0x18004698a  mov     r15, r9
0x18004698d  mov     r12, r8
0x180046990  mov     r14, rdx
0x180046993  xor     r13d, r13d
0x180046996  mov     [r9], r13
0x180046999  mov     [rsp+140h+Context], r13
0x18004699e  mov     [rsp+140h+fPending], r13d
0x1800469a3  lea     r9, [rsp+140h+Context]; lpContext
0x1800469a8  lea     r8, [rsp+140h+fPending]; fPending
0x1800469ad  xor     edx, edx; dwFlags
0x1800469af  lea     rdi, ?wrapper@?1??Instance@FavoritesTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VFavoritesTelemetry@@@details@wil@@A; wil::details::static_lazy<FavoritesTelemetry> `FavoritesTelemetry::Instance(void)'::`2'::wrapper
0x1800469b6  mov     rcx, rdi; lpInitOnce
0x1800469b9  call    cs:__imp_InitOnceBeginInitialize
0x1800469bf  lea     rcx, qword_180808C68
0x1800469c6  lea     rdx, ??_7FileExplorerTelemetry@@6B@; const FileExplorerTelemetry::`vftable'
0x1800469cd  test    eax, eax
0x1800469cf  jz      short loc_1800469DC
0x1800469d1  cmp     [rsp+140h+fPending], r13d
0x1800469d6  jnz     loc_180046F8C
0x1800469dc  mov     rax, [rsp+140h+Context]
0x1800469e1  mov     [rsp+140h+var_C8], r13b
0x1800469e6  mov     [rsp+140h+var_E0], r13d
0x1800469eb  lea     rcx, aCautodestitems_1; "CAutoDestItemsFolder::_BindToTargetShel"...
0x1800469f2  mov     [rsp+140h+var_D8], rcx
0x1800469f7  mov     [rsp+140h+var_D0], r13
0x1800469fc  mov     [rbp+40h+var_C0], r13
0x180046a00  mov     [rbp+40h+var_B8], rax
0x180046a04  mov     [rbp+40h+var_B0], r13
0x180046a08  mov     [rbp+40h+var_A8], r13d
0x180046a0c  lea     rax, [rsp+140h+var_E0]
0x180046a11  mov     [rbp+40h+var_A0], rax
0x180046a15  mov     [rbp+40h+var_98], 0
0x180046a19  mov     rsi, 0CCCCCCCCCCCCCCCDh
0x180046a23  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180046a2a  test    rdi, rdi
0x180046a2d  jz      short loc_180046AA1
0x180046a2f  call    cs:__imp_GetCurrentThreadId
0x180046a35  mov     ebx, eax
0x180046a37  mov     r8d, eax
0x180046a3a  shr     r8, 2
0x180046a3e  mov     rax, rsi
0x180046a41  mul     r8
0x180046a44  shr     rdx, 3
0x180046a48  lea     rcx, [rdx+rdx*4]
0x180046a4c  add     rcx, rcx
0x180046a4f  sub     r8, rcx; unsigned __int64
0x180046a52  lea     rsi, ds:0[r8*8]
0x180046a5a  mov     rax, [rsi+rdi]
0x180046a5e  xchg    ax, ax
0x180046a60  test    rax, rax
0x180046a63  jz      loc_180046F04
0x180046a69  cmp     [rax], ebx
0x180046a6b  jz      short loc_180046A73
0x180046a6d  mov     rax, [rax+8]
0x180046a71  jmp     short loc_180046A60
0x180046a73  lea     rcx, [rax+10h]
0x180046a77  mov     [rbp+40h+var_C0], rcx
0x180046a7b  test    rcx, rcx
0x180046a7e  jz      short loc_180046A97
0x180046a80  mov     rax, [rcx]
0x180046a83  mov     [rbp+40h+var_B0], rax
0x180046a87  lea     rax, [rbp+40h+var_C0]
0x180046a8b  mov     [rcx], rax
0x180046a8e  call    cs:__imp_GetCurrentThreadId
0x180046a94  mov     [rbp+40h+var_A8], eax
0x180046a97  mov     rsi, 0CCCCCCCCCCCCCCCDh
0x180046aa1  mov     [rsp+140h+pv], r13
0x180046aa6  mov     [rsp+140h+Context], r13
0x180046aab  mov     [rsp+140h+fPending], r13d
0x180046ab0  lea     r9, [rsp+140h+Context]; lpContext
0x180046ab5  lea     r8, [rsp+140h+fPending]; fPending
0x180046aba  xor     edx, edx; dwFlags
0x180046abc  lea     rbx, ?wrapper@?1??Instance@FavoritesTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VFavoritesTelemetry@@@details@wil@@A; wil::details::static_lazy<FavoritesTelemetry> `FavoritesTelemetry::Instance(void)'::`2'::wrapper
0x180046ac3  mov     rcx, rbx; lpInitOnce
0x180046ac6  call    cs:__imp_InitOnceBeginInitialize
0x180046acc  test    eax, eax
0x180046ace  jz      short loc_180046ADB
0x180046ad0  cmp     [rsp+140h+fPending], 0
0x180046ad5  jnz     loc_18063F7C4
0x180046adb  mov     rax, [rsp+140h+Context]
0x180046ae0  mov     [rbp+40h+var_78], 0
0x180046ae4  mov     [rbp+40h+var_90], r13d
0x180046ae8  lea     rcx, aCautodestitems_4; "CAutoDestItemsFolder::_GetTargetAbsolut"...
0x180046aef  mov     [rbp+40h+var_88], rcx
0x180046af3  mov     [rbp+40h+lpMem], r13
0x180046af7  mov     [rbp+40h+var_70], r13
0x180046afb  mov     [rbp+40h+var_68], rax
0x180046aff  mov     [rbp+40h+var_60], r13
0x180046b03  mov     [rbp+40h+var_58], r13d
0x180046b07  lea     rcx, [rbp+40h+var_90]
0x180046b0b  mov     [rbp+40h+var_50], rcx
0x180046b0f  mov     [rbp+40h+var_48], 0
0x180046b13  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180046b1a  test    rdi, rdi
0x180046b1d  jz      short loc_180046B87
0x180046b1f  call    cs:__imp_GetCurrentThreadId
0x180046b25  mov     ebx, eax
0x180046b27  mov     r8d, eax
0x180046b2a  shr     r8, 2
0x180046b2e  mov     rax, rsi
0x180046b31  mul     r8
0x180046b34  shr     rdx, 3
0x180046b38  lea     rcx, [rdx+rdx*4]
0x180046b3c  add     rcx, rcx
0x180046b3f  sub     r8, rcx; unsigned __int64
0x180046b42  lea     rsi, ds:0[r8*8]
0x180046b4a  mov     rax, [rdi+rsi]
0x180046b4e  xchg    ax, ax
0x180046b50  test    rax, rax
0x180046b53  jz      loc_180046F40
0x180046b59  cmp     [rax], ebx
0x180046b5b  jz      short loc_180046B63
0x180046b5d  mov     rax, [rax+8]
0x180046b61  jmp     short loc_180046B50
0x180046b63  lea     rcx, [rax+10h]
0x180046b67  mov     [rbp+40h+var_70], rcx
0x180046b6b  test    rcx, rcx
0x180046b6e  jz      short loc_180046B87
0x180046b70  mov     rax, [rcx]
0x180046b73  mov     [rbp+40h+var_60], rax
0x180046b77  lea     rax, [rbp+40h+var_70]
0x180046b7b  mov     [rcx], rax
0x180046b7e  call    cs:__imp_GetCurrentThreadId
0x180046b84  mov     [rbp+40h+var_58], eax
0x180046b87  xorps   xmm0, xmm0
0x180046b8a  xor     eax, eax
0x180046b8c  movups  xmmword ptr [rsp+140h+pvar], xmm0
0x180046b91  mov     [rsp+140h+var_E8], rax
0x180046b96  mov     edi, 80070057h
0x180046b9b  test    r14, r14
0x180046b9e  jz      short loc_180046BC5
0x180046ba0  movzx   eax, word ptr [r14]
0x180046ba4  cmp     eax, 0Fh
0x180046ba7  jb      short loc_180046BC5
0x180046ba9  cmp     dword ptr [r14+6], 0C1EC0C9h
0x180046bb1  jnz     short loc_180046BC5
0x180046bb3  movzx   edx, word ptr [r14+0Ah]; cb
0x180046bb8  lea     rcx, [rdx+0Fh]
0x180046bbc  cmp     rax, rcx
0x180046bbf  jnb     loc_180046C55
0x180046bc5  mov     rcx, [rbp+48h]; this
0x180046bc9  mov     r9d, edi; char *
0x180046bcc  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\windows.storage\\fre"...
0x180046bd3  mov     edx, 8DBh; void *
0x180046bd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046bdd  lea     rcx, [rsp+140h+pvar]; pvar
0x180046be2  call    cs:__imp_PropVariantClear
0x180046be8  nop
0x180046be9  cmp     [rbp+40h+var_58], 0
0x180046bed  jz      short loc_180046BF9
0x180046bef  lea     rcx, [rbp+40h+var_70]; this
0x180046bf3  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180046bf8  nop
0x180046bf9  cmp     [rbp+40h+var_78], 0
0x180046bfd  jnz     loc_18004702A
0x180046c03  test    edi, edi
0x180046c05  jns     loc_180046CD2
0x180046c0b  mov     rcx, [rbp+48h]; this
0x180046c0f  mov     r9d, edi; char *
0x180046c12  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\windows.storage\\fre"...
0x180046c19  mov     edx, 8E9h; void *
0x180046c1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046c23  mov     rcx, [rsp+140h+pv]; pv
0x180046c28  mov     [rsp+140h+pv], r13
0x180046c2d  call    cs:__imp_CoTaskMemFree
0x180046c33  nop
0x180046c34  cmp     [rbp+40h+var_A8], 0
0x180046c38  jz      short loc_180046C44
0x180046c3a  lea     rcx, [rbp+40h+var_C0]; this
0x180046c3e  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180046c43  nop
0x180046c44  lea     rcx, [rsp+140h+var_E0]; this
0x180046c49  call    ?ClearMessage@StoredCallContextInfo@details@wil@@QEAAXXZ; wil::details::StoredCallContextInfo::ClearMessage(void)
0x180046c4e  mov     eax, edi
0x180046c50  jmp     loc_180046E95
0x180046c55  test    dx, dx
0x180046c58  jz      loc_180046BC5
0x180046c5e  lea     rcx, [r14+0Fh]; psps
0x180046c62  test    rcx, rcx
0x180046c65  jz      loc_180046BC5
0x180046c6b  lea     r9, [rsp+140h+pvar]; ppropvar
0x180046c70  lea     r8, PKEY_DelegateIDList; rpkey
0x180046c77  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180046c7d  mov     edi, eax
0x180046c7f  test    eax, eax
0x180046c81  js      loc_180046BC5
0x180046c87  cmp     word ptr [rsp+140h+pvar], 0
0x180046c8d  jz      loc_180046FD2
0x180046c93  lea     rdx, [rsp+140h+pv]
0x180046c98  lea     rcx, [rsp+140h+pvar]
0x180046c9d  call    PropVariantToIDList
0x180046ca2  mov     edi, eax
0x180046ca4  test    eax, eax
0x180046ca6  js      loc_180046FDC
0x180046cac  lea     rcx, [rsp+140h+pvar]; pvar
0x180046cb1  call    cs:__imp_PropVariantClear
0x180046cb7  nop
0x180046cb8  cmp     [rbp+40h+var_58], 0
0x180046cbc  jz      short loc_180046CC8
0x180046cbe  lea     rcx, [rbp+40h+var_70]; this
0x180046cc2  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180046cc7  nop
0x180046cc8  cmp     [rbp+40h+var_78], 0
0x180046ccc  jnz     loc_18004700D
0x180046cd2  mov     r14, [rsp+140h+pv]
0x180046cd7  mov     [r15], r13
0x180046cda  mov     qword ptr [rsp+140h+fPending], r13
0x180046cdf  mov     esi, 8007000Eh
0x180046ce4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180046ceb  mov     ecx, 0D8h; unsigned __int64
0x180046cf0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180046cf5  mov     rdi, rax
0x180046cf8  test    rax, rax
0x180046cfb  jz      loc_180046EBC
0x180046d01  mov     rcx, rax; this
0x180046d04  call    ??0CMarshalByValue@@QEAA@XZ; CMarshalByValue::CMarshalByValue(void)
0x180046d09  mov     dword ptr [rcx+78h], 0FFFFFFFEh
0x180046d10  mov     dword ptr [rcx+7Ch], 1
0x180046d17  lea     rcx, [rcx+50h]; lpCriticalSection
0x180046d1b  call    cs:__imp_InitializeCriticalSection
0x180046d21  lea     rax, ??_7CShellItem@@6BCMarshalByValue@@@; const CShellItem::`vftable'{for `CMarshalByValue'}
0x180046d28  mov     [rdi], rax
0x180046d2b  lea     rax, ??_7CShellItem@@6BIShellItem2@@@; const CShellItem::`vftable'{for `IShellItem2'}
0x180046d32  mov     [rdi+8], rax
0x180046d36  lea     rax, ??_7CShellItem@@6BIShellItemImageFactoryPriv@@@; const CShellItem::`vftable'{for `IShellItemImageFactoryPriv'}
0x180046d3d  mov     [rdi+10h], rax
0x180046d41  lea     rax, ??_7CShellItem@@6BIPersistIDList@@@; const CShellItem::`vftable'{for `IPersistIDList'}
0x180046d48  mov     [rdi+18h], rax
0x180046d4c  lea     rax, ??_7CShellItem@@6BIParentAndItem@@@; const CShellItem::`vftable'{for `IParentAndItem'}
0x180046d53  mov     [rdi+20h], rax
0x180046d57  lea     rax, ??_7CShellItem@@6BIPersistStream@@@; const CShellItem::`vftable'{for `IPersistStream'}
0x180046d5e  mov     [rdi+28h], rax
0x180046d62  lea     rax, ??_7CShellItem@@6BICacheableObject@@@; const CShellItem::`vftable'{for `ICacheableObject'}
0x180046d69  mov     [rdi+30h], rax
0x180046d6d  lea     rax, ??_7CShellItem@@6BIChildId@@@; const CShellItem::`vftable'{for `IChildId'}
0x180046d74  mov     [rdi+38h], rax
0x180046d78  lea     rax, ??_7CShellItem@@6BIObjectWithBackReferences@@@; const CShellItem::`vftable'{for `IObjectWithBackReferences'}
0x180046d7f  mov     [rdi+40h], rax
0x180046d83  lea     rax, ??_7CShellItem@@6BIInitializeWithFolder@@@; const CShellItem::`vftable'{for `IInitializeWithFolder'}
0x180046d8a  mov     [rdi+48h], rax
0x180046d8e  mov     dword ptr [rdi+80h], 1
0x180046d98  mov     [rdi+88h], r13
0x180046d9f  mov     [rdi+90h], r13
0x180046da6  mov     [rdi+98h], r13
0x180046dad  mov     [rdi+0A0h], r13
0x180046db4  mov     [rdi+0A8h], r13
0x180046dbb  mov     [rdi+0B0h], r13
0x180046dc2  mov     [rdi+0B8h], r13
0x180046dc9  mov     [rdi+0C0h], r13
0x180046dd0  mov     [rdi+0C8h], r13
0x180046dd7  mov     [rdi+0D0h], r13d
0x180046dde  lea     rcx, [rdi+50h]; this
0x180046de2  call    ?InitApartmentId@CObjectWithThreadUseDetection@@QEAAJXZ; CObjectWithThreadUseDetection::InitApartmentId(void)
0x180046de7  mov     esi, eax
0x180046de9  test    eax, eax
0x180046deb  js      short loc_180046E09
0x180046ded  mov     rax, [rdi]
0x180046df0  lea     r8, [rsp+140h+fPending]
0x180046df5  lea     rdx, _GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5
0x180046dfc  mov     rcx, rdi
0x180046dff  mov     rax, [rax]
0x180046e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e07  mov     esi, eax
0x180046e09  mov     rax, [rdi]
0x180046e0c  mov     rcx, rdi
0x180046e0f  mov     rax, [rax+10h]
0x180046e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e18  test    esi, esi
0x180046e1a  js      loc_180046EBC
0x180046e20  mov     rcx, qword ptr [rsp+140h+fPending]
0x180046e25  mov     rax, [rcx]
0x180046e28  mov     rdx, r14
0x180046e2b  mov     rax, [rax+20h]
0x180046e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e34  mov     esi, eax
0x180046e36  test    eax, eax
0x180046e38  js      short loc_180046E52
0x180046e3a  mov     rcx, qword ptr [rsp+140h+fPending]
0x180046e3f  mov     rax, [rcx]
0x180046e42  mov     r8, r15
0x180046e45  mov     rdx, r12
0x180046e48  mov     rax, [rax]
0x180046e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e50  mov     esi, eax
0x180046e52  mov     rcx, qword ptr [rsp+140h+fPending]
0x180046e57  mov     rax, [rcx]
0x180046e5a  mov     rax, [rax+10h]
  ... truncated ...
```
