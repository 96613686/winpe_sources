# ClipboardBrokerFactory::serverThreadStart(void *)

- ea: `0x1800054a0`
- end: `0x1800056b6`
- name: `?serverThreadStart@ClipboardBrokerFactory@@CAKPEAX@Z`
- size: `534`
- prototype: `unsigned int __fastcall(void *pvhr)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800053e0`
- `0x1800054a0`
- `0x18000703c`
- `0x180007180`
- `0x18000a0e8`
- `0x18001933c`
- `0x180036d4c`
- `0x18003fbbc`
- `0x180048024`
- `0x18008f0a0`
- `0x18008f12c`
- `0x18008f5a0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800054e3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800054e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000554c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000554c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800056ab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800056ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800056a1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800056a1`
- `USER32!GetClipboardOwner` at `0x180005572`
- `USER32!GetClipboardOwner` at `0x180005572`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x1800054f8`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x1800054f8`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000552a`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000552a`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180005656`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180005656`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000568a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000568a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000561b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000561b`

## pseudocode

```c
__int64 __fastcall ClipboardBrokerFactory::serverThreadStart(HRESULT *pvhr)
{
  HRESULT v2; // ebx
  HANDLE v3; // rcx
  unsigned int v4; // edx
  bool v5; // di
  HRESULT v6; // ebx
  unsigned __int64 v7; // rcx
  HWND ClipboardOwner; // rax
  Microsoft::WRL::ComPtr<CClipboardBroker> *v10; // rax
  IClipboardBroker *ptr; // rdi
  CBrokerInstanceHolder **v12; // rdx
  CClipboardBroker *v13; // rcx
  wchar_t *v14; // rbx
  ClipboardWatchdog watchdog; // [rsp+30h] [rbp-10h] BYREF
  Microsoft::WRL::ComPtr<CClipboardBroker> dwIndex; // [rsp+60h] [rbp+20h] BYREF
  const wchar_t *pszOwnerPackageFullName; // [rsp+68h] [rbp+28h] BYREF

  v2 = OleInitializeEx(0);
  if ( v2 >= 0 )
  {
    v10 = Microsoft::WRL::Details::Make<CClipboardBroker,>(&dwIndex);
    pszOwnerPackageFullName = 0;
    ptr = v10->ptr_;
    v10->ptr_ = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&pszOwnerPackageFullName);
    v13 = dwIndex.ptr_;
    if ( dwIndex.ptr_ )
    {
      dwIndex.ptr_ = 0;
      ((void (__fastcall *)(CClipboardBroker *))v13->lpVtbl->Release)(v13);
    }
    if ( ptr )
    {
      v2 = CBrokerInstanceHolder::Create(ptr, v12);
      ((void (__fastcall *)(IClipboardBroker *))ptr->lpVtbl->Release)(ptr);
    }
    else
    {
      v2 = -2147024882;
      RoOriginateError(2147942414LL, 0);
    }
  }
  watchdog.m_timer = 0;
  watchdog.m_monitoredThreadID = 0;
  if ( v2 >= 0 )
    v2 = ClipboardWatchdog::Initialize(&watchdog);
  v3 = ClipboardBrokerFactory::s_hServerThreadEvent;
  *pvhr = v2;
  SetEvent(v3);
  if ( v2 >= 0 )
  {
    v5 = CoEnableCallCancellation(0) >= 0;
    do
    {
      LODWORD(dwIndex.ptr_) = 0;
      v6 = CoWaitForMultipleHandles(
             0x18u,
             0x3A98u,
             1u,
             &ClipboardBrokerFactory::s_hServerThreadStopEvent,
             (LPDWORD)&dwIndex);
      pszOwnerPackageFullName = (const wchar_t *)wil::FileTime::FromInt64(v7);
      SetThreadpoolTimer(watchdog.m_timer, (PFILETIME)&pszOwnerPackageFullName, 0, 0x1388u);
    }
    while ( v6 == -2147417835 );
    if ( v5 )
      CoDisableCallCancellation(0);
    pszOwnerPackageFullName = 0;
    LODWORD(dwIndex.ptr_) = 0;
    ClipboardOwner = GetClipboardOwner();
    if ( GetClipboardOwnerWindowProperty(ClipboardOwner, &pszOwnerPackageFullName, (unsigned int *)&dwIndex) >= 0 )
    {
      v14 = (wchar_t *)pszOwnerPackageFullName;
      if ( pszOwnerPackageFullName )
      {
        OleClipboardTracing::ClipboardBroker_TryFlushClipboardOnShutdown(
          pszOwnerPackageFullName,
          (unsigned int)dwIndex.ptr_);
        OleFlushClipboardInternal(v14, 1, 0);
        CoTaskMemFree(v14);
      }
    }
  }
  if ( ClipboardBrokerFactory::s_pServerBroker )
    CBrokerInstanceHolder::`scalar deleting destructor'(ClipboardBrokerFactory::s_pServerBroker, v4);
  ClipboardBrokerFactory::s_pServerBroker = 0;
  OleUninitialize();
  if ( watchdog.m_timer )
  {
    WaitForThreadpoolTimerCallbacks(watchdog.m_timer, 1);
    CloseThreadpoolTimer(watchdog.m_timer);
  }
  return 0;
}

```

## disassembly

```asm
0x1800054a0  mov     [rsp-18h+arg_10], rbx
0x1800054a5  push    rbp
0x1800054a6  push    rsi
0x1800054a7  push    rdi
0x1800054a8  mov     rbp, rsp
0x1800054ab  sub     rsp, 40h
0x1800054af  mov     rsi, pvhr
0x1800054b2  xor     ecx, ecx; pvReserved
0x1800054b4  call    OleInitializeEx
0x1800054b9  mov     ebx, eax
0x1800054bb  test    eax, eax
0x1800054bd  jns     loc_1800055CC
0x1800054c3  mov     [rbp+watchdog.m_timer], 0
0x1800054cb  mov     [rbp+watchdog.m_monitoredThreadID], 0
0x1800054d2  test    ebx, ebx
0x1800054d4  jns     loc_180005644
0x1800054da  mov     pvhr, cs:?s_hServerThreadEvent@ClipboardBrokerFactory@@0PEAXEA; hEvent
0x1800054e1  mov     [rsi], ebx
0x1800054e3  call    cs:__imp_SetEvent
0x1800054e9  mov     esi, 1
0x1800054ee  test    ebx, ebx
0x1800054f0  js      loc_180005590
0x1800054f6  xor     ecx, ecx; pReserved
0x1800054f8  call    cs:__imp_CoEnableCallCancellation
0x1800054fe  mov     edi, eax
0x180005500  shr     edi, 1Fh
0x180005503  xor     dil, sil
0x180005506  lea     rax, [rbp+dwIndex]
0x18000550a  mov     dword ptr [rbp+dwIndex], 0
0x180005511  lea     r9, ?s_hServerThreadStopEvent@ClipboardBrokerFactory@@0PEAXEA; pHandles
0x180005518  mov     [rsp+40h+lpdwindex], rax; lpdwindex
0x18000551d  mov     r8d, esi; cHandles
0x180005520  mov     edx, 3A98h; dwTimeout
0x180005525  mov     ecx, 18h; dwFlags
0x18000552a  call    cs:__imp_CoWaitForMultipleHandles
0x180005530  mov     ebx, eax
0x180005532  call    ?FromInt64@FileTime@wil@@YA?AU_FILETIME@@_K@Z; wil::FileTime::FromInt64(unsigned __int64)
0x180005537  mov     pvhr, [rbp+watchdog.m_timer]; pti
0x18000553b  lea     rdx, [rbp+pszOwnerPackageFullName]; pftDueTime
0x18000553f  mov     r9d, 1388h; msWindowLength
0x180005545  mov     [rbp+pszOwnerPackageFullName], rax
0x180005549  xor     r8d, r8d; msPeriod
0x18000554c  call    cs:__imp_SetThreadpoolTimer
0x180005552  cmp     ebx, 80010115h
0x180005558  jz      short loc_180005506
0x18000555a  test    dil, dil
0x18000555d  jnz     loc_180005654
0x180005563  mov     [rbp+pszOwnerPackageFullName], 0
0x18000556b  mov     dword ptr [rbp+dwIndex], 0
0x180005572  call    cs:__imp_GetClipboardOwner
0x180005578  mov     pvhr, rax; hWnd
0x18000557b  lea     r8, [rbp+dwIndex]; pdwProcessId
0x18000557f  lea     rdx, [rbp+pszOwnerPackageFullName]; pszPackageId
0x180005583  call    ?GetClipboardOwnerWindowProperty@@YAJPEAUHWND__@@PEAPEBGPEAK@Z; GetClipboardOwnerWindowProperty(HWND__ *,ushort const * *,ulong *)
0x180005588  test    eax, eax
0x18000558a  jns     loc_180005661
0x180005590  mov     pvhr, cs:?s_pServerBroker@ClipboardBrokerFactory@@0PEAVCBrokerInstanceHolder@@EA; this
0x180005597  test    pvhr, pvhr
0x18000559a  jnz     loc_180005695
0x1800055a0  mov     cs:?s_pServerBroker@ClipboardBrokerFactory@@0PEAVCBrokerInstanceHolder@@EA, 0; CBrokerInstanceHolder * ClipboardBrokerFactory::s_pServerBroker
0x1800055ab  call    OleUninitialize
0x1800055b0  mov     pvhr, [rbp+watchdog.m_timer]; pti
0x1800055b4  test    pvhr, pvhr
0x1800055b7  jnz     loc_18000569F
0x1800055bd  mov     rbx, [rsp+40h+arg_10]
0x1800055c2  xor     eax, eax
0x1800055c4  add     rsp, 40h
0x1800055c8  pop     rdi
0x1800055c9  pop     rsi
0x1800055ca  pop     rbp
0x1800055cb  retn
0x1800055cc  lea     pvhr, [rbp+dwIndex]; result
0x1800055d0  call    ??$Make@VCClipboardBroker@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCClipboardBroker@@@12@XZ; Microsoft::WRL::Details::Make<CClipboardBroker,>(void)
0x1800055d5  lea     pvhr, [rbp+pszOwnerPackageFullName]; this
0x1800055d9  mov     [rbp+pszOwnerPackageFullName], 0
0x1800055e1  mov     rdi, [rax]
0x1800055e4  mov     qword ptr [rax], 0
0x1800055eb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800055f0  mov     pvhr, [rbp+dwIndex]
0x1800055f4  test    pvhr, pvhr
0x1800055f7  jz      short loc_18000560D
0x1800055f9  mov     [rbp+dwIndex], 0
0x180005601  mov     rax, [pvhr]
0x180005604  mov     rax, [rax+10h]
0x180005608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000560d  test    rdi, rdi
0x180005610  jnz     short loc_180005626
0x180005612  mov     ebx, 8007000Eh
0x180005617  xor     edx, edx
0x180005619  mov     ecx, ebx
0x18000561b  call    cs:__imp_RoOriginateError
0x180005621  jmp     loc_1800054C3
0x180005626  mov     pvhr, rdi; broker
0x180005629  call    ?Create@CBrokerInstanceHolder@@SAJPEAUIClipboardBroker@@PEAPEAV1@@Z; CBrokerInstanceHolder::Create(IClipboardBroker *,CBrokerInstanceHolder * *)
0x18000562e  mov     ebx, eax
0x180005630  mov     pvhr, rdi
0x180005633  mov     rax, [rdi]
0x180005636  mov     rax, [rax+10h]
0x18000563a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000563f  jmp     loc_1800054C3
0x180005644  lea     pvhr, [rbp+watchdog]; this
0x180005648  call    ?Initialize@ClipboardWatchdog@@QEAAJXZ; ClipboardWatchdog::Initialize(void)
0x18000564d  mov     ebx, eax
0x18000564f  jmp     loc_1800054DA
0x180005654  xor     ecx, ecx; pReserved
0x180005656  call    cs:__imp_CoDisableCallCancellation
0x18000565c  jmp     loc_180005563
0x180005661  mov     rbx, [rbp+pszOwnerPackageFullName]
0x180005665  test    rbx, rbx
0x180005668  jz      loc_180005590
0x18000566e  mov     edx, dword ptr [rbp+dwIndex]; ownerPid
0x180005671  mov     pvhr, rbx; pszOwnerPackageFullName
0x180005674  call    ?ClipboardBroker_TryFlushClipboardOnShutdown@OleClipboardTracing@@SAXPEBGK@Z; OleClipboardTracing::ClipboardBroker_TryFlushClipboardOnShutdown(ushort const *,ulong)
0x180005679  xor     r8d, r8d; fTextOnly
0x18000567c  mov     dl, sil; fInBroker
0x18000567f  mov     pvhr, rbx; pszCallerPackgeFullName
0x180005682  call    ?OleFlushClipboardInternal@@YAJPEBG_N1@Z; OleFlushClipboardInternal(ushort const *,bool,bool)
0x180005687  mov     pvhr, rbx; pv
0x18000568a  call    cs:__imp_CoTaskMemFree
0x180005690  jmp     loc_180005590
0x180005695  call    ??_GCBrokerInstanceHolder@@QEAAPEAXI@Z; CBrokerInstanceHolder::`scalar deleting destructor'(uint)
0x18000569a  jmp     loc_1800055A0
0x18000569f  mov     edx, esi; fCancelPendingCallbacks
0x1800056a1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800056a7  mov     pvhr, [rbp+watchdog.m_timer]; pti
0x1800056ab  call    cs:__imp_CloseThreadpoolTimer
0x1800056b1  jmp     loc_1800055BD
```
